# MISMO: Blockchain and AI in Mortgage

**Date:** 2024-06-14
**Duration:** ~1 hour
**Recording:** https://www.youtube.com/watch?v=UUjv0h0YxwE
**Meeting Series:** 30th Hyperledger Financial Markets Mortgage Subgroup Meeting

## TL;DR

This meeting explored the convergence of blockchain and AI technologies in the mortgage industry, with MISMO presenting their standards-based approach to enabling both. The key insight is that successful blockchain adoption in mortgages depends on data standardization and interoperability, while AI adoption focuses on augmenting human decision-making rather than automation. MISMO is positioning their data standards and new Electron Loan Data Dictionary (ELDD) as the foundation for both technologies.

## Attendees

- **Hyperledger Moderator:** [[James Marvin]] (Hyperledger Foundation)
- **Industry Analyst:** [[Mark D'Angelo]] (Reuters Institute Contributing Author, MBA Publisher)
- **MISMO Leadership:** [[David Coleman]] (President, MISMO, since April 2023)
- **MISMO Blockchain Expert:** [[Devin Caster]] (Senior Principal Product Manager at [[CoreLogic]], Co-chair of MISMO Blockchain Community of Practice)
- **GSE Representative:** [[Omar]] ([[Fannie Mae]], Blockchain Community of Practice Participant)
- **Other Attendees:** FM SIG members, mortgage industry professionals

## Agenda

1. Opening remarks and Hyperledger/MISMO appreciation
2. James Marvin: Mortgage industry blockchain updates
3. Mark D'Angelo: AI in the mortgage industry
4. David Coleman & Devin Caster: MISMO blockchain and AI initiatives
5. Q&A and discussion on interoperability, tokenization, and regulation
6. MISMO summit announcement

## Discussion

### Industry Updates: Project Guardian and Morgan Stanley AI

James Marvin presented major developments in blockchain and AI in finance:

- **[[Project Guardian]]** (JP Morgan): Collaborative effort started May 2022 involving [[JP Morgan]], [[DBS Bank]], [[SBI]], and [[Wisdom Tree]] exploring decentralized finance, asset tokenization, and wholesale funding markets. Focus on institutional-grade DeFi products and open, interoperable networks.
- **Morgan Stanley's AI Suite**: Wealth management launched AI-powered tools including "debrief" (open AI-powered note generation) and an AI Morgan Stanley assistant chatbot (98% adoption by financial advisor teams). This represents human-augmentation approach rather than replacement.

### AI in the Mortgage Industry

Mark D'Angelo's key framework: **AI represents a fundamental shift, not an incremental improvement**. Rather than traditional tech adoption patterns, the industry needs to understand baseline data, data standards, ethical sourcing, and interoperability. Key points:

- **Industry Evolution:** From Gen AI/LLMs toward industry ring-fencing. The mortgage industry has ~40% of its own proprietary data; it needs to control and train on that data rather than rely entirely on general LLMs
- **Data-First Approach:** The fundamental shift is understanding that success requires data governance before technology implementation
- **Major Use Cases:** Document reading/processing, developer assistance, chatbot enhancement — NOT autonomous underwriting decisions without human oversight
- **Future Focus:** Sector-specific models combining industry data with federated AI approaches to maintain data privacy

### MISMO's Role in Blockchain and AI

**MISMO Organization Overview:**
- Maintains mortgage industry data standards and models
- 2,000+ members with 580-600 active volunteers
- 39 work groups and communities of practice
- Foundational role for both blockchain and AI implementations

#### Blockchain Community of Practice

**Key Initiatives:**
- **Formation:** Established 2018 after years of discussion in emerging tech community
- **Current Charter:** Education focus, prototyping with open standards, moving toward conceptual work as prototypes require commercial infrastructure
- **Recent Work:** Lunch-and-learn sessions on decentralized identifiers, self-sovereign identities, and blockchain basics using non-technical analogies
- **Prototypes:** Servicing transfer prototype; interoperability-focused prototypes leveraging [[MISMO]] API toolkit to bridge multiple blockchains

**Blockchain-AI Convergence:** MISMO sees blockchain and AI as symbiotic technologies. Use case: Generative AI can convert data schemas between different blockchains, bridging interoperability gaps when data standards aren't yet aligned across systems.

**Major Challenge:** Education. Most misconceptions persist (crypto mortgages, solutions looking for problems). Even experienced architects sometimes dismiss blockchain without considering specific use cases.

#### Tokenization Discussion

Tokenization is the "shiny object" but requires:
1. Trusted data ecosystem first (via blockchain)
2. Complex regulatory navigation (SEC, CFPB, GSEs)
3. Understanding of asset complexity (mortgages more complex than commercial real estate)

**Active Players:** [[Figur]] (shifted focus from mortgages to HELOCs; working with non-conforming lending), [[LiquidFi]] (formerly Liquid Mortgage; partnered with [[Redwood Trust]] for portfolio lending), [[Hexil Blockchain]]

**Regulatory Arbitrage:** Tokenization companies currently focus on semi-federally regulated assets (HELOCs) or private mortgage markets (non-conforming) to avoid complex approvals. Conforming loan tokenization would require coordination with multiple federal agencies.

#### Data Standards Evolution

- **Traditional:** MISMO XML schema (~2000 data fields)
- **Modern:** **[[ELDD]]** (Electron Loan Data Dictionary) — boils down data to unique identifiers and relationship mappings
- **Future:** API-first approach using GraphQL and other technologies beyond monolithic XML

### GSE Involvement and Coordination

All three GSEs ([[Fannie Mae]], [[Freddie Mac]], Federal Home Loan Banks, and [[Ginnie Mae]]) are MISMO members with active participation:
- Fannie Mae & Freddie Mac maintain "UPB" (Universal Pricing Bulletin) — their own MISMO-based specifications
- 6-10 representatives from each GSE participate in MISMO summits across multiple work groups
- Omar (Fannie Mae) confirmed active blockchain community of practice involvement since MISMO's inception

### MISMO Summit Announcement

- **Date:** August 26-29, 2024
- **Location:** Reston Town Center, DC area
- **Note:** Non-members can participate in work groups without voting rights
- **Website:** mimo.it

## Key Decisions

- MISMO is shifting from prototype-heavy to education and conceptual work as infrastructure costs increase
- Focus remains on making blockchain accessible through non-technical education
- Data standardization (via ELDD and APIs) is prerequisite for successful blockchain/AI adoption

## Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Share MISMO Community of Practice sign-up information | [[Devin Caster]] | TBD | Open |
| Investigate federated AI and compartmentalized data standards | [[MISMO]] blockchain/AI COPs | TBD | Open |
| Consider blockchain community of practice involvement | Meeting attendees | TBD | Open |
| Register for MISMO Summit (Aug 26-29, Reston) | Interested parties | 2024-08-26 | Open |

## Key Insights

1. **Data Standards are the Foundation:** MISMO's work on standardizing mortgage data is critical infrastructure for both blockchain and AI success
2. **AI ≠ Automation:** The mortgage industry is using AI for augmentation and efficiency, not replacing human decision-making in underwriting
3. **Interoperability Requires Alignment:** Multiple blockchains will exist; standards-based APIs and ELDD mappings will determine whether they can work together
4. **Regulatory is a Blocker:** Tokenization of conforming mortgages is blocked by regulatory complexity across federal agencies — this must be solved in parallel with technology development
5. **Education Remains the Barrier:** Even in 2024, blockchain fundamentals are still misunderstood; MISMO's focus on non-technical storytelling is critical

## Related Meetings

- Previous MISMO blockchain discussions covered in Hyperledger mortgage subgroup sessions
- MISMO AI Forum: September 2023 (initial) and June 2024 (San Francisco)
