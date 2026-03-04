# Angelo

- **Title:** Hyperledger Fabric Security Reviewer
- **Organization:** [[Hyperledger]]
- **Role in Community:** Security domain expert, RFC reviewer focused on trust and maintenance impact

## Meeting Appearances
- [[2026-01-21-fabric-coap-gateway]] — Raised critical security and architectural concerns about trust domain assumptions

## Key Contributions
- **Security scrutiny:** Challenged trust domain assumptions in CoAP gateway proposal
- **Maintenance concerns:** Advocated for careful code complexity management in core Fabric codebase
- **Proxy debate:** Questioned whether direct peer connection meaningfully improves security over trusted middleware

## Key Perspectives
- Opposes embedding gateway services directly in Fabric peer (previous position from gateway service debate)
- Emphasizes that each code change requires long-term maintenance commitment from Fabric team
- Argues that if peer trust is assumed, equivalent trust can be placed in external proxy without core modifications

## Related Entities
- [[Hyperledger]] — Primary organization
- [[Bernardo]] — CoAP Gateway RFC author (security debate counterparty)
