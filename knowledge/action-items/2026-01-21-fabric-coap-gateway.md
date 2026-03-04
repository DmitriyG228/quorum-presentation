# Action Items: Hyperledger Fabric CoAP Gateway Proposal (2026-01-21)

| # | Action | Owner | Due Date | Priority | Status |
|---|--------|-------|----------|----------|--------|
| 1 | Clarify trust domain assumptions in RFC (address [[Angelo]]'s security concerns) | [[Bernardo]] | TBD | High | Open |
| 2 | Document IoT device transaction flow clearly with sequence diagrams | [[Bernardo]] | TBD | High | Open |
| 3 | Finalize RFC incorporating community feedback from call | [[Bernardo]] | TBD | High | Open |
| 4 | Implement CoAP gateway adapter and protoc plugin | [[Bernardo]] | TBD | High | Open |
| 5 | Prepare for final approval vote in community | [[Artam]] | TBD | Medium | Open |

## Notes

### Action #1 - Trust Domain Clarification
[[Angelo]] challenged the security model by asking: "If you trust the peer, why not trust external middleware instead?" [[Bernardo]] needs to articulate in RFC:
- Explicit trust domain assumptions
- Why direct peer connection provides security advantage beyond trust assumptions
- Maintenance burden implications
- Comparison to existing gateway service precedent

### Action #2 - Transaction Flow Documentation
Current discussion references existing flow but needs clear documentation for IoT case:
- How IoT device initiates CoAP request
- Translation to gRPC gateway call
- Endorsement collection, ordering submission
- Response delivery back to IoT device
- Potential for sequence diagrams in RFC

### Action #3 - RFC Finalization
RFC has evolved significantly from original proposal:
- Shifted from full gRPC gateway reimplementation to simple protobuf adapter
- Changed security model from single to dual certificate
- Focused on minimal core impact
- Need to capture these decisions formally

### Action #4 - Implementation (Not yet started)
Once RFC approved, implementation work includes:
- CoAP library integration (in build, not core)
- Protoc plugin development for CoAP code generation
- Adapter implementation on gateway
- Testing with real IoT devices
- Documentation for users

### Action #5 - Community Vote Preparation
Before final approval, coordinate:
- Ensure RFC incorporates feedback
- Address remaining concerns
- Schedule approval vote
- Document decision rationale

## Related Context
- **RFC Discussion:** Ongoing on Hyperledger working group channels
- **Previous Precedent:** Fabric gateway service integration (similar concerns)
- **IoT Use Cases:** Warehouse sensors, remote device tracking, field deployments
