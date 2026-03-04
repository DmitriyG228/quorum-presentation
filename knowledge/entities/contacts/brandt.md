# Brandt

- **Title:** Zarf maintainer, software signing expert
- **Organization:** [[Zarf]] (maintainer)
- **Role in Community:** Security expert on cryptographic signatures and package security

## Meeting Appearances
- [[2025-12-10-tag-security-compliance]] — Presented comprehensive analysis of four software signing approaches, discussed Zarf's embedded-variant signature approach, planned improvements

## Key Contributions
- Expert analysis of four approaches to code signing: HTTPS transport (bad), embedded (generally bad), detached separate (compliance-only), detached combined (recommended)
- Deep knowledge of how major vendors (Google, Fedora, Debian) failed to implement embedded signatures correctly
- Leading Zarf development with focus on air-gapped software delivery and secure package handling

## Technical Expertise
- Cryptographic signatures and verification
- Package signing strategies and revocation mechanisms
- Air-gap deployment models and their security implications
- Threat model analysis of signature schemes

## Known Implementation Work
- Zarf currently uses embedded-variant signatures (signature inside tarball)
- Plans to add detached separate signatures alongside current approach
- Documentation improvements needed to clarify inner-content signing model

## Related Entities
- [[Zarf]] — Product maintained
- [[Marina]] — Collaborative discussions on notary/sigstore patterns
- [[TAG Security]] — Community involvement
