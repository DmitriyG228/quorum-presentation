# Jamara

- **Description:** 6-layer GRC (Governance, Risk, and Compliance) framework designed as an "OSI model for GRC systems"
- **Status:** Development, V1 release planned January 2026
- **Maintained by:** [[CNCF]] TAG Security (led by [[Jen]])

## Architecture

**Six-Layer Model:**
1. **Guidance** — Abstract high-level compliance frameworks (PCI-DSS, ISO 27001, SSDF, CRA)
2. **Controls** — Technology-specific controls with threat mappings (OPS baseline, Finnow common cloud controls, CIS benchmarks)
3. **Policy** — Organizational scope aggregation, policy definition (enforced via layer 5)
4. **Evaluation** — Assessment of actual posture via code/config/workload inspection (extends OPS validator/Privalizer)
5. **Enforcement** — Policy enforcement mechanisms (deployment gates, manual/automated remediation)
6. **Posture** — Holistic compliance and security posture snapshot against policy

## Implementation Status
- JSON schemas in YAML format for layers 1-6
- Layer 5 (enforcement) and layer 6 (posture) schemas still in development
- MCP (Model Context Protocol) server prototype built for schema authoring and control selection via natural language
- Cursor IDE integration demonstrated for practical usage

## Release Timeline
- **V1 Target:** January 2026
- **All schemas complete:** End Q4 2025
- **Release candidate:** End Q4 2025 for community/implementer feedback
- **Feedback collection:** Between RC and V1

## Problem It Solves
- GRC work and data fragmented across spreadsheets, Google Docs, PDFs
- Data incompatibility, untraceable provenance, data silos
- Duplicate work and compliance gaps
- Jamara standardizes GRC data as schemas enabling tooling, interoperability

## Key Tools
- Go library for schema instantiation and validation
- MCP server for LLM-assisted schema generation (control selection, policy definition)

## Meeting Mentions
- [[2025-12-10-tag-security-compliance]] — Full demo, release timeline, MCP server walkthrough

## Related Entities
- [[TAG Security]] — Maintaining organization
- [[Jen]] — Lead developer
- [[CNCF]] — Organizational home
