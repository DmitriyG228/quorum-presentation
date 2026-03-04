# TAG Security & Compliance General Meeting

**Date:** 2025-12-10
**Recording:** https://www.youtube.com/watch?v=zHIYYkItDnE
**Phase:** Phase 2: Compliance & Security

## TL;DR
TAG Security reviewed Jamara, a GRC framework with 6-layer architecture to standardize compliance and security practices using schemas. Discussed sandbox project reviews, security assessments, and software signing best practices (detached combined signatures recommended over embedded). Several initiatives in progress with end-of-year milestones.

## Attendees
- [[Jen]] (CNCF TAG Security, Jamara lead) - Community demo
- [[Marina]] (TAG Security co-lead, security practices expertise)
- [[Evan]] (TAG Security coordinator/notes)
- [[Brandt]] (Zarf, software signing expertise)
- [[Andy Martin]] (Security review lead for Kyivero)
- [[Yoshiuki]] (Performance evaluation working on)
- [[John Shell]] (MCP white paper lead)
- [[Eddie Knight]] (Security Slam initiative)
- [[William Woodruff]] (Dependency adoption researcher)
- [[Justin]] (Dependency adoption researcher)

## Agenda
1. Jamara demo (GRC framework with 6-layer model)
2. APAC TAG Security meeting updates
3. TOC meeting updates and sandbox reviews
4. Project updates (supply chain, security assessments, controls, white papers)
5. General check-in: software signing deep dive

## Discussion

### Jamara: GRC Framework Demo

[[Jen]] demonstrated Jamara, a 6-layer framework designed as an "OSI model for GRC systems" to address fragmentation in compliance and security data that typically lives in spreadsheets, Google Docs, and PDFs.

**The Six Layers:**
1. **Layer 1: Guidance** - Abstract high-level guidance (PCI-DSS, ISO 27001, SSDF, CRA)
2. **Layer 2: Controls** - Technology-specific controls with threat mappings (OPS baseline, Finnow's common cloud controls, CIS benchmarks)
3. **Layer 3: Policy** - Aggregates layers 1-2, defines scope and organizational context; enforced in layer 5
4. **Layer 4: Evaluation** - Inspects code, configuration, behavior, workloads (like OPS baseline validator/Privalizer)
5. **Layer 5: Enforcement** - Where policy is actually enforced (deployment gates, manual/automated remediation)
6. **Layer 6: Posture** - Holistic security and compliance posture snapshot against policy

**Key Points:**
- V1 release targeted for January 2026 with all schemas built out
- Release candidate planned for end of Q4 with feedback loop before final V1
- MCP (Model Context Protocol) server prototype developed to use LLMs for schema authoring and control selection
- Demo used Cursor IDE to show practical schema generation via natural language prompts
- Goal: reduce labor-intensive YAML creation while maintaining schema compliance

**Action:** [[Jen]] to continue schema development toward January V1 release; implementers and practitioners to provide feedback on release candidate

### APAC TAG Security Meeting (Dec 4)

Meeting held with group not present today. Notable items:
- MCP security community demo
- IM white paper goals and next steps
- [[Yoshiuki]] performing evaluation work
- End-of-year schedule notifications

**Decision:** No action items identified from APAC meeting attendees not present

### TOC Meeting Updates

**Sandbox Project Reviews:**
- Sandbox project review happening end-of-year (within next 1-2 weeks) to clear backlog
- Fresh start for next year
- TAG Security members requested to help with due diligence
- Review due next week
- Multiple sandbox applications with unresolved discussion threads in GitHub issues

**Specific Projects Discussed:**
- **Gardon** (non-CNCF project that completed security review): Decision deferred, but preference to accept the work and revisit if project not in CNCF within one year. Proposed storage location: under tag security and compliance "other" or "non-CNCF" folder (not in main TOC projects structure to avoid implying CNCF status)

**Key Points:**
- Concern about clarity: non-CNCF projects in TOC repo could imply CNCF affiliation
- Alternative proposal: store self-assessment files in project repositories in standardized location (like how LICENSE files are scanned)
- Dex File project has confusing name (unrelated to "Dex"), name change requested but not yet done

**Action:** Review sandbox project board and identify which projects align with TAG Security scope; communicate findings at TOC meeting

### Project Updates

**Supply Chain Insights:**
- Switching to bi-weekly cadence
- Low activity last couple weeks
- Continuing tracking

**Security Assessments:**
- [[Andy Martin]] (lead reviewer) interacting with Kyivero team
- Naive questions phase expected completion soon
- Self-assessment merging happening
- TOC merge bottleneck for some pending assessments

**Security Controls Working Group:**
- First meeting Friday
- Goal: solidify scope, milestones, and timeline for initiative
- December expected to be planning-focused only
- README and scope documentation target for TOC repo

**NCP White Paper:**
- [[John Shell]] leading
- New meeting created: Mondays 9:00 AM Eastern
- Expected to accelerate after meeting cadence established

**Security Slam:**
- [[Eddie Knight]] initiative
- Outreach to CNCF for European event space pending response
- Follow-up needed

**Triaging & Issues:**
- Compliance use cases white paper recently assigned to TAG Security
- Other tracked initiatives: Security insights, Kerno, IM white paper, MCP security controls

### Software Signing Deep Dive

[[Brandt]] (Zarf maintainer) presented and discussed four approaches to code signing and emphasized the importance of meaningful verification beyond just cryptographic validity.

**Four Signing Approaches:**

1. **HTTPS Transport-Only Signatures** (BAD)
   - Relies solely on TLS/HTTPS for authenticity
   - Cannot prove signature to third parties
   - Community consensus: not acceptable for security

2. **Embedded Signatures** (GENERALLY BAD)
   - Signature embedded inside the package itself
   - Problem: Hash of original artifact changes, hard to implement correctly
   - No major system has done this right without security incidents (Google, Fedora, Debian all had issues)
   - Revocation and multi-signer delegation are problematic
   - Exception: Client software with app-store model works differently

3. **Detached Separate Signatures** (COMPLIANCE ONLY)
   - Separate signature files per signed artifact
   - Easy to deploy (100 signers = 100 signature files)
   - Problems: signatures don't expire unless keys revoked (rare), long expiration windows (often 1 year) mean old vulnerabilities can be installed
   - Fine for compliance, terrible for security

4. **Detached Combined Signatures** (RECOMMENDED FOR SECURITY)
   - Per-signer signature file listing all their signatures
   - Versioning allows efficient revocation: removing entry revokes signature
   - Supports delegation: "Trust Marina for X, but not Y"
   - Supports threshold signing: "Require 3-of-5 from group A"
   - Proper trust rooting and key revocation mechanisms
   - Scales better than separate files

**Zarf Approach:**
- Currently: signature inside package tarball (embedded variant)
- Nuance: Zarf signs inner contents, not the tarball structure itself
- Safer than typical embedded approach but should clarify in documentation
- Opportunity to add detached separate signatures alongside

**Key Points:**
- Verification tutorials often gloss over verification step ("run command, it says OK, move on")
- Should encourage: identity verification, capability mapping, who-signed-what semantics
- Supply chain complexity growing as projects must integrate: Are projects building BOM? How do they sign? What's the distribution mechanism?
- Projects using Zarf should consider detached combined signatures for better security posture

**Action:** [[Brandt]] to (1) document Zarf's signing approach clearly, (2) explore detached separate signatures alongside current approach; deep-dive with [[Marina]] on how notary/sigstore handle these scenarios

### Upcoming Presentation

Next week: [[Justin]] and [[William Woodruff]] debating early vs. delayed dependency adoption
- Some community interest expected
- Format TBD: live presentation vs. recorded
- Social media promotion planned for Slack and LinkedIn

**Action:** Promote in Slack channel and via LinkedIn post

## Key Decisions
- Detached combined signatures recommended for security-critical software signing (vs. embedded or detached separate)
- Non-CNCF project reviews to be stored under tag security "other"/"non-CNCF" folder (vs. implying CNCF status)
- Jamara V1 release scheduled for January 2026
- TAG Security to participate in sandbox project review due diligence

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Solidify security controls scope, milestones, timeline | Security Controls WG | Friday this week | Open |
| Complete naive questions phase for Kyivero review | [[Andy Martin]] | Soon | In Progress |
| Provide feedback on Jamara release candidate | Community/Implementers | Between RC and V1 | Pending |
| Finish Jamara V1 schemas | [[Jen]] | End Q4 2025 | In Progress |
| Review sandbox project board for TAG Security alignment | TAG Security members | Next week | Open |
| Document Zarf's signing approach (inner content signing) | [[Brandt]] | TBD | Open |
| Explore detached signatures for Zarf | [[Brandt]] | Short term | Open |
| Deep dive: notary/sigstore patterns with [[Marina]] | [[Brandt]] | TBD | Open |
| Promote Justin/William Woodruff presentation | [[Evan]] or volunteer | This week | Open |
| Follow up on CNCF European event space for Security Slam | [[Eddie Knight]] | ASAP | Open |
| Establish NCP white paper meeting cadence | [[John Shell]] | In progress | In Progress |
