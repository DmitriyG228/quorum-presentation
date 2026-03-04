# TAG Security & Compliance General Meeting

**Date:** 2026-01-14
**Duration:** ~1 hour
**Recording:** https://www.youtube.com/watch?v=ewJX0keE4RA

## TL;DR
TAG Security & Compliance held a working meeting centered on [[Andrew Nesbit]]'s presentation of the "git packages" tool for dependency analysis. Extended discussions covered supply chain security community initiatives, security controls catalog publication, security assessments, and event planning for upcoming conferences.

## Attendees
- Coordinator (meeting lead)
- [[Evan]] (scriber)
- [[Andrew Nesbit]] (presenter, ecosystems/git packages project)
- [[Brandt]] (mentioned regarding Defense Unicorns announcement)
- [[Marina]] (TAG Security co-lead)
- [[Justin]] (mentioned, security assessments)
- [[Eddie Knight]] (Security Slam coordinator)
- Multiple community members (names partially captured)

## Agenda
1. Welcome and ground rules (code of conduct reminder, recording notice)
2. New member introductions ([[Andrew Nesbit]] introduction)
3. "Git Packages" tool demo - dependency analysis for software supply chain
4. Supply chain security technical community group updates
5. Security assessments status
6. Security controls catalog publication planning
7. Security Slam event planning for upcoming conferences
8. Presentation scheduling and community engagement

## Discussion

### Welcome & Logistics

Meeting opened with Happy New Year greeting and standard CNCF code of conduct reminder. Recording posted to LFX and YouTube.

**Key Points:**
- [[Evan]] assigned as scriber
- Congratulations to [[Brandt]] on Defense Unicorns announcements
- Meeting participation indicates agreement to abide by Cloud Native Foundation code of conduct

### New Member Introduction: Andrew Nesbit

[[Andrew Nesbit]] introduced himself as maintainer of the "ecosystems" project, which indexes open source metadata across all major package managers and repositories globally, mining dependencies to enable SBOM enrichment and security research.

### "Git Packages" Tool Demo: Dependency Analysis

[[Andrew Nesbit]] presented "git packages," a Ruby gem/Homebrew-installable git subcommand for analyzing dependency evolution within software repositories over time.

**Background:**
- Started as research project ~9 years ago mining git history
- Evolved into practical tool for "spelunking" through dependency changes
- Uses SQLite database for fast local queries (created once, instant on subsequent runs)
- Supports ~30 different package ecosystems and manifest formats

**Core Features:**
- **Initialization:** One-time `git packages init` creates local SQLite database
- **Dependency Listing:** View current dependencies at repository HEAD or any historical point
- **Dependency Diffing:** Compare dependency changes between commits/tags
- **Database Schema Access:** Write custom SQL queries against extracted dependency data
- **CI Integration:** Export results as JSON/SARIF for GitHub Actions or pull request integration
- **Time-Series Analysis:** Track average times to resolve vulnerabilities (e.g., CRA compliance reporting)

**Supported Manifest Formats:**
- Gem files, package.json, requirements.txt, Docker files, YAML, TOML
- 30+ different software ecosystem configurations tracked

**Example Outputs:**
- Vulnerability resolution tracking (average time from discovery to fix)
- Dependency change summaries across repository history
- Integration with forge tools via JSON output
- SBOM-related metadata and provenance tracking

**Potential Use Cases:**
- Policy enforcement tool development (currently no standardized dependency policy framework exists)
- Integration with forge platforms to provide richer diff visualization for lock files
- Automated CRA compliance reporting based on historical vulnerability response data
- Supply chain risk assessment via dependency volatility analysis

### Supply Chain Security Technical Community Group Updates

First meeting of new supply chain security technical community group held this week.

**Background:**
- New recurring meeting series (Mondays at 1 PM Eastern based on Jan 7 notes)
- Aim to bridge gap between "timeless but generic" guidance and practical maintainer needs
- Participants: attendee, [[Marina]], OpenTelemetry representative, and others (4+ attendees noted)

**Key Themes Discussed:**
- Build "recipe books" with specific guidance on practical implementations
  - ESBOM publication procedures for CNCF projects
  - CVE vulnerability process setup
  - Documentation for maintainers lacking deep security expertise
- Gap identified: extensive guidance exists but maintainers need step-by-step implementation examples
- Blog post proposal: CNCF blog article highlighting practical supply chain security guidance

**Discussion Points:**
- Supply chain attacks trending in past 1-2 weeks to be reviewed and cataloged during meetings
- Maintenance concerns addressed: avoid static catalogs that become outdated (point-in-time problem)
- Expertise needed: volunteers for reviewing supply chain content and contributing guidance examples

**Next Steps:**
- CNCF blog post on practical implementation guidance
- Review of recent supply chain attacks and defensive best practices
- Integration with existing CNCF supply chain materials

### Security Assessments Update

[[Justin]] reported on security assessments initiative:

**Status:**
- Kyivero review stalled - awaiting [[Andy Martin]] to complete "naive questions" phase
- [[Andy Martin]] recently returned from holiday
- Additional follow-up needed to re-engage

**Challenges:**
- Lost momentum after initial application phase
- Contributors (including [[Andy Martin]]) shifted focus to other priorities
- Need to build redundancy in assessment process

**Next Steps:**
- Reach out to [[Andy Martin]] to resume naive questions phase completion

### Security Controls Working Group: Catalog Publication

[[Jen]] (implied, based on context) reported security controls initiative progress:

**Status:**
- Met twice focused on scoping and defining milestones
- README created in TOC repo outlining plans

**Milestone One Progress:**
- **Goal:** Transform spreadsheet data into machine-readable format
- **Current State:** Work fork in progress on CNCF contribute site
- **Tooling:** Lightweight tooling being developed on top of catalog

**Publication Approval Path - SOLVED:**
- Requires: Pull request + TAG review + TOC awareness
- Will stay as living TAG artifact
- Removes previous uncertainty about approval gates

**Timeline:**
- More details to be shared at Friday meeting (Jan 17, 2026)

### Supply Chain Insights Initiative

Referenced as separate initiative (previously updated Jan 7 as currently on hiatus).

### Security Slam Event Planning

[[Eddie Knight]] mentioned regarding CubeCon security slam event planning.

**Points Raised:**
- Plans for upcoming CubeCon event discussed
- Coordinator asked about upcoming plans and timeline

### Presentation Scheduling

Discussion on community demo schedule and presentation opportunities.

**Current Status:**
- Schedule noted as "looking empty" for upcoming presentations
- Call for community input on presentation ideas

**Potential Presentations:**
- [[Andrew Nesbit]] offered to present deeper demo of "ecosystems" project if community interest exists
- Full presentations (longer-form) and 5-10 minute community demo slots both available

**Next Steps:**
- Community members invited to raise hand, comment in chat, or post to Slack with presentation interests

## Key Decisions
- Security controls catalog can be published via PR with TAG review + TOC awareness (removes approval bottleneck)
- Supply chain technical community group continuing with regular Monday meetings
- Security Slam event planning for CubeCon moving forward
- Presentation schedule open for community input

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Resume Kyivero review - complete naive questions phase | [[Andy Martin]] | ASAP | In Progress |
| Share more details on security controls catalog progress | [[Jen]] or security controls WG | Friday after Jan 14 | Open |
| Follow up with [[Andy Martin]] on Kyivero assessment | [[Justin]] | This week | Open |
| Develop recipe books for supply chain guidance (ESBOM, CVE processes, etc.) | Supply chain community group | TBD | Open |
| Publish CNCF blog post on practical supply chain security guidance | Supply chain community group | TBD | Open |
| Review and catalog recent supply chain attacks | Supply chain community group | Next meetings | Open |
| Confirm CubeCon Security Slam event details and timeline | [[Eddie Knight]] | Before CubeCon | Open |
| Coordinate community presentations and demos | Coordinator | Ongoing | Open |
| Share ecosystems project deeper demo if community interest | [[Andrew Nesbit]] | TBD | Pending Interest |
