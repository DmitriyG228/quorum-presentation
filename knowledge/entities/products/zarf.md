# Zarf

- **Description:** Package and deployment tool for air-gapped software delivery with integrated security
- **Status:** Active development, focusing on signature verification improvements
- **Maintained by:** [[Brandt]] (lead maintainer)

## Use Cases
- Air-gapped environment software delivery
- Package bundling with security integration
- Supply chain security and package verification

## Current Signature Approach
- **Method:** Embedded-variant signatures (signature inside tarball)
- **Mechanism:** Signs inner contents/payload, not the tarball structure itself
- **Status:** Works but documentation needs clarity on security properties
- **Planned improvements:** Add detached separate signatures alongside current approach

## Security Considerations

**Current Approach (Embedded-Variant):**
- Safer than typical flat embedded signatures due to tarball-within-tarball structure
- Clear about what's being signed (inner content, not structure)
- Avoids some pitfalls of traditional embedded signatures
- Trade-off: less efficient than pure detached signatures

**Planned Evolution:**
- Support detached separate signatures for compliance verification
- Maintain embedded-variant for air-gap convenience
- Align with industry best practices from notary/sigstore ecosystem

## Signing Best Practices (Per Community Discussion)

**Recommended Signature Approach:**
- **Detached combined signatures** for security-critical software (not embedded)
- Enables revocation via versioning and delegation
- Supports threshold signing and role-based trust delegation
- Scales better than detached separate signatures

**Zarf's Challenge:**
- Air-gapped distribution makes some approaches harder
- Must balance security with offline/disconnected deployment scenarios
- Exploring how to maintain security properties in air-gapped context

## Meeting Mentions
- [[2025-12-10-tag-security-compliance]] — Deep-dive on signing approaches, current implementation discussed

## Related Entities
- [[Brandt]] — Maintainer
- [[Marina]] — Collaborating on notary/sigstore patterns
- [[TAG Security]] — Community involvement
