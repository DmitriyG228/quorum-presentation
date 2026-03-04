# ELDD

- **Full Name:** Electron Loan Data Dictionary
- **Description:** Modern mortgage data standard and mapping system from [[MISMO]]
- **Status:** Active, core to MISMO's data standardization strategy
- **Maintained by:** [[MISMO]]
- **Focus:** Standardizing and interoperating mortgage data across systems, blockchain, and AI applications

## Purpose
ELDD represents evolution from traditional MISMO monolithic XML schema (~200+ data fields) to:
- **Unique Identifiers:** Reduces data to essential identifiers
- **Relationship Mappings:** Establishes clear relationships between data elements
- **System Interoperability:** Enables transformation of data between different blockchain implementations, API systems, and technology platforms
- **Technology-Agnostic:** Designed to work with GraphQL, REST APIs, and other modern data interfaces

## Key Innovation
Rather than requiring each blockchain or system to maintain its own data standards, ELDD provides:
1. Canonical mapping of mortgage data
2. Ability to transform data between different schema representations
3. Foundation for MISMO API toolkit to bridge multiple blockchain implementations
4. Support for federated AI and shared learning across industry participants

## Use Cases
- **Blockchain Interoperability:** Convert data from one blockchain's schema to another's using MISMO API toolkit + ELDD mappings
- **AI Training:** Provides clean, standardized data for federated AI models
- **API Development:** Foundation for standardized RESTful and GraphQL APIs in mortgage services
- **Document Processing:** Improves AI document reading and data extraction accuracy

## Meeting Mentions
- [[2024-06-14-blockchain-ai-mortgage-mesmo]] — [[Devin Caster]] discussed ELDD as major advancement in moving away from monolithic XML toward flexible identifier and relationship-based model; emphasized as critical to blockchain and AI adoption

## Related Entities
- [[MISMO]] — Maintains and develops ELDD
- MISMO API Toolkit — Uses ELDD mappings for interoperability
