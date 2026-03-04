# TAG Security & Compliance General Meeting

**Date:** 2026-01-07
**Duration:** ~1 hour
**Recording:** https://www.youtube.com/watch?v=uncIyQLKKko

## TL;DR
TAG Security began the year with a demo of [[Minder]], an open-source supply chain security platform that automates policy enforcement across GitHub repositories through declarative configuration and continuous remediation. Reviewed organizational updates including initiatives in security assessments, controls, and supply chain insights, with emphasis on sandbox project reviews and documentation improvements.

## Attendees
- [[Evan]] (TAG Security coordinator, Minder presenter)
- [[Ron]] (attendee)
- [[Grant]] (attendee)
- [[Marina]] (TAG Security co-lead)
- [[Matt]] (question on self-hosting)
- [[John]] (attendee)
- [[Brandt]] (expertise on tooling)
- [[Jen]] (attendee)
- [[Justin]] (Security assessments lead)
- [[Eddie Knight]] (Security Slam initiative)

## Agenda
1. Welcome and ground rules (code of conduct reminder, recording notice)
2. Minder demo - supply chain security automation platform
3. APAC TAG Security meeting updates (IM white paper)
4. TOC meeting updates and project presentations
5. Project initiative updates
6. Q&A and future presentation scheduling

## Discussion

### Welcome & Logistics

[[Evan]] (coordinator) kicked off the meeting with Happy New Year greeting and confirmed recording/LFX posting. Established that meeting participation indicates agreement to abide by Cloud Native Foundation code of conduct.

**Key Points:**
- Meeting notes document created for 2026
- Scribes requested to help document
- New attendees invited to introduce themselves and share their working group involvement

### Minder Demo: Supply Chain Security Platform

[[Evan]] presented [[Minder]], a supply chain security platform with emphasis on detection AND remediation across software projects.

**Background:**
- Project started at [[Stacklock]] in 2023
- Stacklock mostly exited in 2025 except for individual contributors
- [[Evan]] left Stacklock and is now leading Minder full-time
- Open Source Security Foundation ([[SSF]]) project
- Declarative configuration approach (coming from CNCF perspective)

**Core Concepts:**
- **Entities:** GitHub repositories, release artifacts, pull requests, and other extensible types
- **Profiles:** Collections of rules/policies to enforce (reusable across repos)
- **Rules:** Configurable security checks defined in Rego (Open Policy Agent language)
- **Remediation:** Can automatically fix policy violations or just report

**Demonstrated Workflow:**
1. Define entities (repositories to manage)
2. Create profiles with multiple rule sets (Bootstrap, Top Five, OpenSSF baseline)
3. Profile selectors allow targeting specific repos
4. Remediation can be enabled/disabled per profile
5. GitHub webhooks enable continuous policy reconciliation

**Example Profiles Shown:**
- **Bootstrap:** Generates pull requests to set up GitHub workflows for policy sync
- **Top Five:** Security best practices (6 rules)
- **OpenSSF:** Project security baseline analysis

**Key Rules Demonstrated:**
- **Branch Protection Requirement:** Checks for PR requirements, branch protections, reviewer counts using GraphQL API
- **HTTPS Clone URL:** Ensures repositories use secure channels
- **Dependabot Enablement:** Automatically generates pull requests to enable dependency updates for detected package ecosystems

**Data Sources & Policy Structure:**
- Rules pull data via GitHub V3 API or GraphQL
- Rego-based policy language with metadata (description, remediation guidance)
- Parameters allow policy reuse with customization (e.g., required reviewer counts)

**Remediation Approach:**
- Continuous service (not one-shot) - automatically reconciles policy violations
- Can generate pull requests (e.g., enabling Dependabot) requiring human approval
- Webhook registration enables automatic re-enforcement if policies are manually disabled
- Supports both continuous and manual (CLI) policy evaluation

**Hosting & Deployment:**
- Minder instance publicly available (hosted by [[Evan]])
- Alternatively, self-hosted via Helm chart
- Dependencies: Keycloak, OpenFGA, PostgreSQL database
- Use hosted service recommended unless organization needs local control (trust concerns)
- Consideration for read-only access mode (separate fixer tool) - not yet architected but acknowledged as useful

**Auditability & History:**
- History API available to see evaluation results over time
- Slightly cumbersome to query historical state at specific point in time (requires forward/backward search)
- Can retrieve full evaluation history if needed

**CI/CD Integration & Dependency Cooling:**
- API allows checking current compliance status in CI
- Note: State can change without git commits (e.g., if branch protection manually disabled)
- Dependabot cool-down parameter not yet implemented - acknowledged as important to reduce PR spam
- Can run policies imperatively via manual tool (underdocumented)

### APAC TAG Security Meeting (Dec 18)

Updates on APAC region meeting held post-Americas meeting:
- IM white paper receiving additional reviews and feedback
- Reviewer requests sent out, more reviewers welcome
- Community demo material scheduled for new year
- SPIFFE/Spire implementation noted in discussions

**Action:** Urgent requests for reviews on IM white paper; thanks to ongoing participants

### TOC Meeting Updates & Project Presentations

[[Marina]] reported on TOC meeting noting:

**Key Points:**
- TOC will conduct check-in on initiatives beginning of next month
- Status verification to ensure initiatives are completing as planned
- Recommendations on project presentations:
  - High-level awareness presentations valuable for exposure
  - Technical deep dives recommended when possible
  - General Technical Review (GTR) pre-population before presentations provides context
  - Some projects maintaining GTR updates over time (good practice)

**Discussion on TAG Security Project Presentations:**
- Currently open for projects needing security and compliance related help
- Not limited to projects with security as sole purpose
- Technical deep dives encouraged when possible

### Supply Chain Security Insights Initiative

Update on supply chain insights project:
- [[Evan]] took unplanned hiatus from KubeCon through December (unplanned move, family medical)
- Back and re-engaged as of January
- Demo of tooling and findings scheduled for two weeks from previous Monday

**Technical Stack:**
- TypeScript for GraphQL endpoint queries
- DuckDB for data processing (SQL-based)
- MIT-based graph database prototyping (cipher query language instead of SQL)
- Arrow-backed edges and nodes for rapid graph materialization
- Zero-copy architecture enabling complex graph queries without CTEs/recursion overhead of SQL

**Next Steps:** Demo of current state and findings

### Security Assessments Initiative

[[Justin]] reported:
- Kyivero review has lost momentum (application went through, contributors have other priorities)
- Officially waiting for naive questions phase completion from [[Andy Martin]]
- Needs: more redundancy and additional people in assessment process
- Seeking volunteers to learn facilitator role (primarily follow-up and coordination)

### Security Controls Initiative

New initiative update:
- Met twice, outcomes focused on scoping and defining milestones
- README created in TOC repo outlining plans
- First meeting Friday (after this general meeting)
- Milestone one: transforming current spreadsheet into machine-readable format
- Work fork already in progress on CNCF contribute site

### MCP Initiative

Brief mention of ongoing MCP white paper work:
- Discussion ongoing about document writing
- More expertise and guidance welcome for steering
- Limited meeting attendance from reporter

### Security Slam Initiative

[[Eddie Knight]] reports need to send Slack message with updates next week

### Software Supply Chain Security Technical Community Group (SSCTCG)

New recurring meeting established:
- Mondays at 1 PM Eastern
- Open to anyone interested in software supply chain security
- Slack announcements planned

### New Issues & Compliance Use Cases White Paper

Compliance use cases white paper moved to TAG Security bucket:
- [[Hubert]] previously advocated for this initiative
- Seeking [[Hubert]] participation to discuss revival and next steps
- Issue link to be shared in agenda and chat

### Presentation Scheduling

Upcoming presentations:
- APAC: presentation scheduled (needs confirmation)
- Americas: [[Andrew Nesbit]] on Git packages next week (needs confirmation)

**Call for Presentations:**
- Longer-form presentations (full meeting time)
- Community demo format (5-10 minute presentations)
- Interested parties invited to raise hand, comment in chat, or post to Slack

## Key Decisions
- Minder available as both hosted service (recommended) or self-hosted via Helm chart
- Read-only mode with separate fixer tool acknowledged as useful but not yet architected
- Supply chain security insights demo scheduled for ~2 weeks
- SSCTCG meeting established with recurring Monday cadence
- Compliance use cases white paper to be revived with [[Hubert]] input

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Demo supply chain insights tooling and findings | [[Evan]] | 2 weeks from Jan 7 | Open |
| Complete naive questions phase for Kyivero review | [[Andy Martin]] | TBD | In Progress |
| Find volunteer for security assessments facilitator role | [[Justin]]/community | ASAP | Open |
| Hold first security controls working group meeting | Security Controls WG | Friday after Jan 7 | Open |
| Send MCP white paper status update to Slack | MCP lead | ASAP | Open |
| Send Security Slam updates to Slack | [[Eddie Knight]] | Next week | Open |
| Revive compliance use cases white paper with [[Hubert]] | [[Hubert]] or volunteer | TBD | Pending |
| Confirm and coordinate APAC presentation | Coordinator | Before next meeting | Open |
| Confirm Andrew Nesbit Git packages presentation | [[Andrew Nesbit]] | Before next meeting | Open |
| Implement Dependabot cool-down parameter | [[Evan]]/Minder team | TBD | Open |
| Explore read-only mode architecture for Minder | [[Evan]]/Minder team | TBD | Open |
| Document Minder setup and policy configuration | [[Evan]] | TBD | Open |
