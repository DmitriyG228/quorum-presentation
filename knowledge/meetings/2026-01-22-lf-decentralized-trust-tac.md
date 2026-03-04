# LF Decentralized Trust Technical Advisory Council Meeting

**Date:** 2026-01-22
**Duration:** ~2 hours
**Recording:** https://www.youtube.com/watch?v=gZWpwtfvQjA
**Phase:** Phase 3: Blockchain Infrastructure

## TL;DR

LF Decentralized Trust TAC held quarterly planning meeting with focus on 2026 goal-setting and strategic priorities. Key discussion areas: quarterly project reports (including Trust Over IP feedback on reporting clarity), project health measurement, cross-project collaboration, knowledge sharing, community engagement in multiple geographies, and accelerating Gen AI adoption. Meeting paused for in-person LF member summit (Jan 29 - no meeting).

## Attendees

- [[Arun]] (Facilitator/TAC Chair)
- [[Diane]] (TAC member, deep expertise in metrics and standards)
- [[Kevin]] (TAC member, brought in new project proposal)
- [[David]] (TAC member, project coordination expertise)
- [[Marcus]] (TAC member, interested in cross-project collaboration)
- [[Ryan]] (TAC member, contributor ladder task force lead, Gen AI initiatives)
- [[Rama]] (TAC member, lifecycle evaluation expertise)
- [[Ray]] (TAC member, contributed project matrix link)
- [[Emmy]] (TAC member)
- [[Ruben]] (TAC member, project metrics)
- New TAC member (learning, minimal participation)

## Agenda

1. Announcements (maintainer days, summit pause, participation opportunities)
2. Quarterly Project Reports
3. Lab Space Summary
4. GitHub Asynchronous Voting Mechanism (notification)
5. 2026 Goal Setting and Strategic Planning
   - Project Growth & Health
   - Knowledge Sharing & Technical Leadership
   - Community Engagement & Collaboration
   - Governance & Transparency
   - Vision & Innovation

## Discussion

### Announcements

**Maintainer Days:** Coming next week. Encouraged all project teams to register early for in-person participation.

**Summit Pause:** TAC will pause meetings on January 29th during LF member summit. All quarterly reports will receive automatic extension until February 5th.

**Community Engagement:** Encouraged projects to submit announcements, RFCs, or design discussion requests through Google Docs/agenda link to reach large developer community.

### Quarterly Project Reports

#### Trust Over IP (ToIP) Report
[[Diane]] provided detailed feedback on Trust Over IP's Q4 quarterly report:

- **Momentum:** Report shows sustained momentum for ToIP despite busy transition year into LFDT
- **Concern:** Difficulty assessing overall progress from current report format
- **Issue:** Heavy reliance on links to external specifications/tools/videos without clear summary of what materially changed in the quarter or how close projects are to real-world adoption
- **Feedback for future reports:** Would benefit from brief framing (1-2 sentences) per major section explaining status and proximity to adoption
- **Specific expertise area:** Diane noted personal deep expertise with DIDK/SKID specs, which are active and moving toward adoption

**Recommendation:** [[Diane]] approved Q4 report with encouragement for ToIP team to implement suggested reporting improvements. Notes to be shared with ToIP team at summit. Staff tracking help requests from ToIP; [[Diane]] will attend their steering committee meetings.

#### Firefly Project Report
- Awaiting project team fix for indentation issue in pull request before merge

#### Credible Team Report
- Recently received, awaiting TAC review

### Lab Space Summary
No significant action items. Multiple proposals noted from one submitter related to Hyperledger Fabric Flutter client. Requester has action items to address before moving forward.

### GitHub Asynchronous Voting Mechanism (FYI)

[[Arun]] presented mechanism for asynchronous decision-making using GitHub issues/PRs:
- Vote via comments or emoji reactions on specific comment
- Voting period defined with clear closing date
- Final tally posted as summary comment
- Useful for TAC decisions and project decisions without waiting for synchronous meeting time
- **Recommendation:** Projects and TAC should adopt where possible

### 2026 Goal Setting and Strategic Planning

[[Arun]] synthesized TAC member nominations and retrospective outcomes into five strategic themes.

#### Theme 1: Project Growth & Health

**Gap identified by Diane:** Specification projects (like ToIP) lack meaningful health metrics and temporal signals to assess if healthy, stalled, or accelerating.

**Suggested best practices adoption:** [[Kevin]] noted seamless experience with project proposal process when given examples of well-written proposals. Recommendation: Document and share exemplary proposal formats.

**Cross-project collaboration:** TAC discussed need to identify collaboration opportunities and reduce redundancy.

**Action taken:**
- Will add quarterly review question asking about collaborations with other projects/labs
- Use project matrix (available on LFDT website) to visualize inter-project relationships and identify collaboration opportunities

#### Theme 2: Knowledge Sharing & Technical Leadership

**Suggestions in nomination statements:**
- Write white papers and knowledge articles
- Create cross-project learning program
- Share enterprise adoption experiences
- Provide guidance for technical decision-making (e.g., blockchain protocol evaluation framework, consensus mechanisms, privacy-preserving tech)

**Current initiatives:**
- Hyperledger (via [[Sophie]]) already creating training materials for onboarding
- Potential LFDT-level video explaining how all projects work together
- Projects could expose generic knowledge articles to broader community

**Discussion:** Identified gap in documentation when maintainers are lost. [[Marcus]] suggested pattern-matching approach: if multiple TAC members notice documentation gap across different projects, escalate for potential solution framework.

#### Theme 3: Community Engagement & Collaboration

**Proposed areas:**
- Revive regional engagement efforts
- Enable participation from multiple geographies
- Support multilingual documentation (with resource strategy)
- Onboard contributors at different experience levels
- Represent LFDT at broader ecosystem events/conferences

**Resource strategy for multilingual support:**
- Leverage mentorship programs (have small funding for such tasks)
- Use regional chapters (historical precedent from Hyperledger era)
- Brazilian and Japanese communities already active; translation work exists as historical example

**Discussion:** David highlighted history of community-driven translation efforts; proposed leveraging existing global community rather than creating new resources.

#### Theme 4: Governance & Transparency

**Key topic:** Contributor Ladder Task Force
- [[Ryan]] currently paused due to health/family situation
- Plan to reboot in February 2026
- Focus areas: good first issues, engagement and training for new contributors
- Additionally exploring Gen AI adoption clarity (addressing FUD) and best practices for AI tool use by maintainers/contributors

**Project Evaluation Criteria:**
- [[Rama]] noted recent revisions to lifecycle transition guidelines
- Removed LFX insights metrics that weren't useful
- Emphasis: All projects should enable OpenSSL scorecard badges as basic criterion
- If projects struggle with specific evaluation criteria, should escalate to TAC for reconsideration

**Challenge:** Easier to measure progress in code development projects; specification projects need better metrics.

#### Theme 5: Vision & Innovation

**Diane's top concern:** Need better reporting/metrics from LFX insights to understand project health, diversity, and adoption trends. This has been top-of-mind throughout 2025.

**Proposed:**
- Engage LFX insights team at maintainer summit to discuss metrics needs
- Possibly bring LFX team to subsequent TAC meeting to discuss solutions
- Better understanding of project diversity and connectivity

**Gen AI Adoption:**
- [[Ryan]] working on article about positive aspects of Gen AI tools and mitigation strategies for increased contributions
- [[Kin]] supporting exploration of how to leverage new AI tools available to community
- **New consideration (end of meeting):** [[Diane]] raised question of distinguishing human vs. AI contributions
  - Trust Over IP group working on this
  - Could be opportunity to engage with ToIP on tagging contributions, understanding tools used, and differentiating AI agents from humans

**Alternative consideration:** How to identify and prevent low-quality AI-generated code that infringes on licensing policies or lacks quality standards.

## Key Decisions

1. **Meeting pause approved** — January 29th off for summit; quarterly reports get extension to February 5th
2. **GitHub asynchronous voting endorsed** — TAC members encouraged to adopt for decisions
3. **2026 themes approved for development** — Five strategic areas identified for goal formulation
4. **ToIP Q4 report approved** — With feedback provided for future improvements
5. **Cross-project collaboration focus** — Matrix-based approach adopted with quarterly review questions

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Fix indentation issue in Firefly pull request | Firefly project team | ASAP | Open |
| Share detailed notes on Trust Over IP feedback with project team | [[Diane]] | During summit (Jan 25-26) | Open |
| Contribute to project matrix/correlation analysis | All TAC members | Ongoing | Open |
| Reboot contributor ladder task force | [[Ryan]] | February 2026 | Open |
| Develop Gen AI adoption best practices article | [[Ryan]] | Q1 2026 | Open |
| Request OpenSSL scorecard badge enablement from all projects | [[Arun]] | Next TAC meeting | Open |
| Engage LFX insights team on reporting needs | [[Arun]] | At maintainer summit | Open |
| Collect 2026 goal inputs from TAC members | All TAC members | Before next meeting | Open |
| Coordinate with Trust Over IP on human vs. AI contribution tagging | [[Diane]] | Q1 2026 | Open |

## Context & References

- **LF member summit:** January 25-26, 2026 (in-person)
- **LF Decentralized Trust website:** Contains project matrix and project metrics views
- **GitHub asynchronous voting:** Mechanism being promoted for TAC and project-level decisions
- **Historical precedent:** Regional chapters and translation efforts from Hyperledger era document successful community-driven multilingual initiatives

## Related Entities

- [[LF Decentralized Trust]]
- [[Trust Over IP]] (ToIP)
- [[Hyperledger Fabric]] (referenced for maintainer examples)
- [[OpenSSL]] (scorecard badges requirement)

## Notes for Future TAC Members

This meeting represents a comprehensive 2026 planning cycle. The five strategic themes (Growth & Health, Knowledge Sharing, Community Engagement, Governance, Vision & Innovation) form the framework for TAC goal-setting. Emphasis on measurable progress, cross-project synergy, and leveraging community strengths rather than creating new overhead.
