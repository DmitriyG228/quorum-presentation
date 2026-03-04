# Hyperledger Fabric CoAP Gateway Proposal

**Date:** 2026-01-21
**Duration:** ~1 hour
**Recording:** https://www.youtube.com/watch?v=n9dMp38WsGA
**Phase:** Phase 3: Blockchain Infrastructure

## TL;DR
Hyperledger Fabric maintainer [[Bernardo]] presented RFC proposal for a CoAP (Constrained Application Protocol) gateway enabling resource-constrained IoT devices to connect directly to Fabric peers. The proposal adds a lightweight UDP-based protocol alongside existing gRPC for scenarios where hardware cannot support HTTP2 overhead. Community discussion raised security concerns about trust domain assumptions but showed general approval for moving forward.

## Attendees
- [[Bernardo]] (Hyperledger Fabric, RFC Author)
- [[Artam]] (Meeting Moderator/Maintainer)
- [[Angelo]] (Hyperledger Fabric, Security Reviewer)
- Multiple Hyperledger community members (names from auto-captions unclear)

## Agenda
1. CoAP Gateway RFC motivation and problem statement
2. Proposed technical solution and architecture
3. Security considerations and trust domains
4. Gateway implementation and code organization
5. Q&A and approval discussion

## Discussion

### Problem Statement: Resource-Constrained IoT Devices
Hyperledger Fabric currently requires clients to use gRPC/HTTP2 (via SDK or Gateway service), which is resource-intensive for IoT devices deployed in field environments.

**Real-world use cases:**
- Warehouse sensors (humidity, temperature monitoring) on OpenThread network communicating with Fabric
- Callers/devices in remote locations unable to communicate with Fabric network
- Devices cannot handle SDK or gateway overhead directly

**Technical constraints:**
- gRPC/HTTP2 creates excessive memory and CPU load
- Even using raw protobuf over HTTP/2 insufficient for most IoT hardware
- Devices need direct peer communication without middleware/proxy intervention
- Current workaround requires gateway or proxy (introduces single point of failure and security risks)

### Proposed Solution: CoAP Gateway Adapter
Use Constrained Application Protocol (CoAP), a lightweight protocol designed for IoT, as transport layer for Fabric communication.

**Key characteristics of CoAP:**
- Built on UDP (lightweight transport)
- Standard in IoT devices (most common use case)
- Secure by default (supports DTLS and TLS)
- Asynchronous communication
- Minimal resource requirements

**Architecture approach:**
- Thin adapter layer on Fabric peer (minimal core impact)
- Reuse existing gRPC gateway logic and proto definitions
- Protoc plugin to generate CoAP code alongside gRPC
- No new ways to communicate — leverage existing Fabric ACL model and proto endpoints
- CoAP server sits alongside gRPC server on gateway

**Implementation scope:**
- Dependency: CoAP library in build (not in core)
- New protoc plugin for CoAP code generation
- Forward communication from CoAP to gRPC gateway
- No changes to core Fabric, just thin translation layer with zero network overhead

**Security evolution:**
- **Original proposal:** Single X.509 certificate for device authentication
- **Current approach (RFC update):** Dual certificate system
  - First certificate: Device identity for IoT gateway transactions
  - Second certificate: Standard Fabric transaction certificate (same as normal clients)
  - Both issued by Fabric CA
  - Maintains same ACL model and security guarantees

### Transaction Flow
When IoT device connects via CoAP:
1. IoT device sends CoAP request to peer's CoAP server
2. CoAP adapter translates to gRPC call to gateway
3. Gateway handles full transaction coordination (same as regular client)
4. Gateway submits to ordering service, awaits endorsements, confirms completion
5. IoT device receives CoAP response

**Key point:** No changes to Fabric transaction processing — only transport protocol changes.

### Security Concerns (Angelo)
[[Angelo]] raised critical trust domain questions:

**Challenge:** If IoT device connects directly to one peer, it implicitly trusts that peer's security domain. If trust assumption holds, why not extend that trust to middleware/proxy instead of modifying Fabric?

**Proposed response:** Direct peer connection eliminates middleware as single point of failure:
- Can listen to gateway communication through middleware (security risk)
- Can intercept or modify messages
- Requires trust in both middleware AND peer
- Direct connection requires only peer trust (if same security domain assumed)

**Angelo's position:** Maintains that this is overloading Fabric codebase with features that could be handled by trusted external gateway. Concerned about maintenance burden on Fabric maintainers for any embedded changes.

**Discussion outcome:** No resolution recorded; [[Bernardo]] acknowledged trust domain question needs clearer specification in RFC.

### Gateway Architecture Questions
Discussion about whether IoT device talks directly to peer or through gateway:
- **Model:** IoT device connects to peer's CoAP endpoint (same as any client via gRPC gateway)
- **Clarification:** Gateway service (independent from visfabric) already handles peer-to-orderer submission
- **New capability:** Adding CoAP endpoint to gateway service to support constrained devices

## Key Decisions
- **Proposal moved toward approval** — Community generally supportive of approach
- **RFC scope refined** — Decided to focus on protobuf-to-CoAP adapter rather than full gRPC gateway reimplementation
- **Minimal core impact confirmed** — Changes localized to gateway, new protoc plugin only
- **Security model updated** — Shifted from single to dual certificate approach during RFC discussion

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Clarify trust domain assumptions in RFC | [[Bernardo]] | TBD | Open |
| Document IoT device transaction flow clearly | [[Bernardo]] | TBD | Open |
| Finalize RFC with community feedback | [[Bernardo]] | TBD | Open |
| Code implementation and integration | [[Bernardo]] | TBD | Open |

## Related Context
- **RFC discussion venue:** Ongoing conversation on working group channels
- **Historical precedent:** Fabric gateway service (gRPC-based) previously embedded in peer; similar maintenance considerations apply
- **Phase alignment:** Part of Phase 3 infrastructure evolution for Hyperledger Fabric

## Technical Terms (for reference)
- **CoAP:** Constrained Application Protocol (RFC 7252)
- **DTLS:** Datagram TLS (UDP-based encryption)
- **gRPC:** Google Remote Procedure Call (HTTP/2-based RPC framework)
- **Protobuf:** Protocol Buffers (language-neutral serialization)
- **Protoc plugin:** Code generator that extends protoc compiler
- **ACL:** Access Control List (Fabric's permission model)
