# Steering Committee Meeting

**Date:** 2026-02-11
**Duration:** ~2 hours
**Recording:** https://www.youtube.com/watch?v=q7BemXqnCzs
**Phase:** Phase 4: Governance & Strategy

## TL;DR

The Trust Over IP Steering Committee discussed governance continuity with three co-chairs (speaker, [[Carly]], and [[Drummond Reed]]) willing to continue. Major focus was on the [[Kerry Suite]] working group's specification release, including adoption of DOI (Digital Object Identifier) from Zenoto for permanent preservation and citation. Strategic discussions centered on ISO/W3C affiliations and standardization pathways.

## Attendees

- **Co-Chair** (Speaker, unnamed) - Trust Over IP
- [[Carly]] (Co-Chair) - Trust Over IP
- [[Drummond Reed]] (Co-Chair) - Trust Over IP
- [[David Boswell]] (Program Manager) - [[Linux Foundation Decentralized Trust]]
- [[Nicholas]] - Kerry Working Group
- [[Sam Smith]] - Kerry Foundation, state digital identity work
- [[Carla]] - ISO/TC68 liaison experience
- [[Scott]] - Standards development, specification templates
- [[John Phillips]] - specupt editorial group
- [[Jory Buren]] (Standards Lead) - [[Linux Foundation]]
- [[Nico]] - Kerry Suite blog post author
- [[Daniela]] - [[Linux Foundation]] staff, member summit coordination
- [[Wenjing]] - Previous mentorship program mentor
- [[Mackie]] - Ecosystem & Governance Working Group
- [[Jim Zen]] - Head of [[Linux Foundation]]
- [[Martina]] - Questions on DOI implementation
- [[Min]] - LFDT Program Manager

## Agenda

1. Antitrust Policy & Community Standards
2. Discord Channel Access
3. Steering Committee Co-Chair Continuation
4. LFDT Mentorship Program Overview & Timeline
5. [[Kerry Suite]] Specification Release & DOI Implementation
6. Standards Development Strategy (ISO/W3C Affiliations)
7. Human Agency Summit (H2) & Linux Foundation Member Summit
8. Ecosystem & Governance Working Group Strategy

## Discussion

### Antitrust Policy & Community Standards

Reminder that all participants work under antitrust policy and are committed to a safe, welcoming community. No speaker noted (usually [[Drummond]]).

### Discord Channel Access

**Issue:** [[Carla]] unable to access Discord due to technical issues.

**Key points:**
- Discord is primary communication channel for LFDT projects
- [[David]] to follow up with [[Ry Jones]] to facilitate access
- [[Nicholas]] spinning up new Discord instance for clean dependency
- All members should have access; request coordination available

**Action:** [[David]] to facilitate Discord access for [[Carla]] via [[Ry Jones]]

### Steering Committee Co-Chair Continuation

**Current co-chairs:** Speaker, [[Carly]], and [[Drummond Reed]]

**Key points:**
- Three co-chairs willing to continue leadership
- Typically limit co-chairs to maximum of four
- Speaker likely to step down as co-chair after current year
- Seeking interest in future co-chair roles

**Decision:** Current co-chair structure continues; will monitor for transition in future years

### LFDT Mentorship Program Overview

**Presenter:** [[David Boswell]]

**Program Details:**
- Structured mentorship funded by [[Linux Foundation]]
- Can support ~15 mentorship proposals per year
- 5-6 month engagement period
- Mentees paid stipend to focus on project work
- Project proposals accepted until March 6th
- [[Technical Advisory Council]] reviews and scores proposals
- Mentors interview mentees to find right fit

**Eligible Project Types:**
- Development-related work (traditional focus)
- Documentation and training materials
- Research activities
- Not limited to coding

**Timeline:**
- **Proposal submission:** Now through March 6th
- **TAC review:** March 6th onwards
- **Mentee onboarding:** June 2026
- **Engagement period:** June-September (~4 months)

**Key points:**
- Successful program for attracting talent from academia and industry
- Creates pathway for new contributors and future leaders
- Past mentees often become maintainers and join member companies
- Available resources and example proposals linked in meeting materials

**Relevant question:** [[Nicholas]] asked if state digital identity work (e.g., [[Sam Smith]] with [[Kerry Foundation]] and Utah) would be appropriate mentorship project. [[David Boswell]] clarified that TAC scores proposals based on relevance to community.

**Recommendation:** [[David Boswell]] offered to educate TAC more about Trust Over IP to help them evaluate incoming proposals effectively

### Kerry Suite Specification Release & DOI Implementation

**Presenter:** [[Carly]]

**Major Initiative:** Use DOI ([[Digital Object Identifier]]) from Zenoto ([[CERN]] repository) for permanent preservation and citation of Kerry Suite specifications.

**What is DOI:**
- ISO standard for persistent identifier
- Globally unique and continually resolvable
- Used extensively in academic publishing and media
- [[Zenoto]] (CERN-run repository) can mint DOIs

**Why DOI for Kerry Suite:**
- Three specifications being finalized and released as v1.0
- Need permanent URL for URI/URN application (URN application requirement)
- Integrated into global infrastructure (tracks citation metrics)
- Metadata preserved even if project disappears
- Free via CERN (~$1 per DOI)
- Increases visibility in academic/standards searches

**Implementation Process:**
1. Pre-register with Zenoto to reserve DOI
2. Insert DOI into specifications before v1.0 release
3. Release specifications on GitHub
4. Back up repository to Zenoto with GitHub plugin
5. Zenoto provides permanent URL linking back to GitHub

**Zenoto Special Features:**
- Gives two DOIs: one for collection (umbrella), one per version
- GitHub integration: auto-sends public releases to Zenoto
- Pre-reserve DOI option (avoids version conflict)

**Related ISO Work:**
[[Carla]] noted this solves broken URL problem in ISO specifications (e.g., 17442 referencing earlier Kerry Suite versions). Can embed DOI in future ISO revisions.

**Connection to Content Authenticity:**
[[Carla]] (co-chair of [[Creator Assertions]] working group, joint [[Trust Over IP]]/[[DCIF]] venture) noted DOI registration agents (IDER, HandID) are exploring DOI metadata insertion in COG specs for persistent identity management.

**Action:** [[Carly]] to work with [[Sam Smith]] and others to mint DOIs via Zenoto; [[Nico]] to write blog post for simultaneous release with DOIs

### Standards Development Strategy & ISO/W3C Affiliations

**Presenter:** [[Scott]]

**Problem:** How do specifications get from Trust Over IP working groups to global recognition/endorsement?

**Key Partners Involved:**
- [[Jory Buren]] ([[Linux Foundation]] standards lead) - exploring options
- [[Drummond Reed]] - leading specupt template development
- [[Carla]] - ISO experience and liaison guidance

**Strategic Options:**
1. W3C affiliation/cooperation
2. ISO standards development
3. Other recognized standards bodies

**Example Use Case:** [[C2PA]] (Content Authenticity) - specification with recognition but not formal ISO standard. [[Leonard Rosenthal]] working to make C2PA an ISO standard (started last year) to gain governance structure and nation-state advocacy participation.

**Next Steps:**
- Internal conversations needed at steering committee and working group levels
- Assess which specifications should pursue which pathways
- Determine goals: defensive (protect), complementary, or amplifying existing work
- [[Carla]] to provide guidance on ISO liaison process
- [[Drummond]] to lead specupt template development with [[John Phillips]] and ad hoc editorial group
- Template should incorporate Kerry Suite lessons learned

**Connection to Ecosystem Strategy:** [[Mackie]] noted five-pillar ecosystem governance strategy includes positioning Kerry Suite for growth, which aligns with ISO liaison opportunities. Internal alignment on messaging and value proposition needed before external outreach.

**Decision:** To be continued; strategic discussion warranted for different vertical/horizontal approaches

### Human Agency Summit (H2) & Linux Foundation Member Summit

**H2 Summit (Feb 23, 2026):**
- Invitation-only one-day conference before LFDT member summit
- Capacity: ~300 people
- All sponsors secured; free registration available
- Drummond actively organizing and presenting
- Focus: human agency, decentralized trust, AI agents
- **First Person Project demo:** Using [[Linux kernel]] credentials via decentralized trust graph
- [[Jim Zen]] (Linux Foundation head) attending and presenting

**Linux Foundation Member Summit (Feb 24-25, 2026):**
- Sessions focused on:
  - Linux kernel maintainer verification project
  - Decentralized trust of the internet of agents
- Workshop Wednesday (date TBD by [[Daniela]])
- Registration: Requires ticket; LFDT members also LF members
- [[David Boswell]] can provide registration codes if needed

**Action:** Contact [[Drummond Reed]] for H2 invitations; check LF member email for summit registration details

### Ecosystem & Governance Working Group Strategy

**Presenter:** [[Mackie]]

**Five-Pillar Strategy Includes:**
1. Enhanced cooperation among internal working groups (e.g., Kerry Suite positioning for growth)
2. ISO liaison activities (to amplify activity)
3. Internal messaging alignment on value and change proposition
4. External discussion with liaisons (including ISO)

**Key Insight:** Internal alignment needed before external outreach to standards bodies.

## Key Decisions

- **Steering committee co-chair structure** continues (three co-chairs); speaker to step down after year
- **Kerry Suite DOI adoption** approved; pursue Zenoto for permanent preservation
- **Standards development strategy** requires internal discussion; [[Carla]] to guide ISO process
- **Blog post coordination:** [[Carly]] and [[Nico]] to write Kerry Suite release announcement
- **Next steering committee meeting:** Five weeks from Feb 11 (approximately March 18)

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Facilitate Discord access for [[Carla]] via [[Ry Jones]] contact | [[David Boswell]] | Asap | Open |
| Mint DOIs for Kerry Suite v1.0 specs via Zenoto community setup | [[Carly]] | Pre-v1.0 release | Open |
| Work with [[Carly]] and [[Sam Smith]] on DOI implementation | [[Nico]] | Pre-v1.0 release | Open |
| Write Kerry Suite specification release blog post | [[Carly]] + [[Nico]] | Pre-v1.0 release | Open |
| Lead specupt template development with editorial group | [[Drummond Reed]] + [[John Phillips]] | TBD | Open |
| Provide ISO liaison guidance and process documentation | [[Carla]] | TBD | Open |
| Disseminate mentorship program info to working group chairs | Steering Committee | By March 6th | Open |
| Facilitate [[Nicholas]]/Kerry Working Group mentorship proposal discussion | [[David Boswell]] | By March 6th | Open |
| Organize internal steering committee discussion on standards affiliations | [[Scott]]/[[Drummond Reed]] | Next meeting | Open |
