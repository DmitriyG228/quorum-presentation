# Minder

- **Description:** Open-source supply chain security platform for GitHub repositories combining policy detection and automated remediation
- **Status:** Active (2026 onwards)
- **Maintained by:** [[Evan]] / [[Open Source Security Foundation]]
- **Language/Technology:** Declarative configuration (Rego), GitHub API integration, Keycloak, OpenFGA
- **Repository:** Open Source Security Foundation project

## Overview

[[Minder]] is a supply chain security platform emphasizing both detection and remediation of security policy violations across software projects. It uses declarative configuration and continuous policy enforcement.

**Key Features:**
- **Entities:** Support for GitHub repositories, release artifacts, pull requests, and extensible types
- **Profiles:** Collections of rules/policies applied selectively to entities via selectors
- **Rules:** Rego-based (Open Policy Agent language) security checks with data sources and remediation actions
- **Remediation:** Automatic fixing of policy violations (can be disabled per profile for audit)
- **Continuous Enforcement:** Webhook-based policy reconciliation - policies reapplied if manually changed
- **History API:** Track evaluation results over time for compliance/audit
- **Multi-organization Support:** Manage multiple GitHub organizations within single Minder project

## Architecture & Implementation

**Core Components:**
- Declarative rule definitions in Rego (inspired by CNCF approach)
- Data sources via GitHub GraphQL API and V3 REST API
- PostgreSQL database backend
- Keycloak for authentication
- OpenFGA for authorization
- Helm chart for deployment (dependencies: PostgreSQL, Keycloak, OpenFGA)

**Deployment Options:**
- **Hosted Service:** Public Minder instance managed by [[Evan]]
- **Self-Hosted:** Helm chart deployment with full control (recommended if trust concerns)
- **Planned Read-Only Mode:** Separate read-only checker with results exported for manual remediation (architecture TBD)

## Demonstrated Rules & Capabilities

**Branch Protection Enforcement:**
- Checks via GraphQL API for GitHub rule sets
- Ensures PR requirements, branch protections, reviewer counts
- Automatic remediation via branch protection rule set updates
- Continuous re-enforcement if manually disabled

**Dependabot Enablement:**
- Scans repository structure for package ecosystem indicators
- Auto-generates pull requests to enable Dependabot for all detected ecosystems
- File-based detection (package.json, requirements.txt, etc.)
- **Limitation:** Cool-down parameter not yet implemented (creates PR spam risk)

**HTTPS Clone URL Validation:**
- Simple policy checking repository clone URL configuration
- Enforces secure channels for development

## Policy Structure & Parameters

**Profiles:**
- Collections of rule references with selective application
- Support parameters for rule customization (e.g., required reviewer count)
- Remediation toggle (enabled/disabled per profile)

**Rules:**
- Metadata: description, remediation guidance, data sources
- Rego query logic for evaluation
- Parameters for customization and policy reuse

**Design Decision:** Removed "reverse" parameters (e.g., allow force pushes) in favor of clearer, single-purpose policies - improved maintainability and understanding

## Known Limitations & Future Work

**Current Limitations:**
- Dependabot cool-down parameter not implemented
- Read-only mode not architected (would require two separate GitHub apps)
- History API query at specific point in time is "slightly more obnoxious" than ideal
- Manual policy execution tool not well documented

**GitHub App Constraints:**
- Static permissions model (unlike Android dynamic model)
- Cannot request permissions dynamically based on remediation needs
- Would require separate app for read-only evaluation vs. remediation

## Use Cases

**Ideal For:**
- Organizations lacking centralized control over repos/policies
- Teams "annealing towards good" security posture
- Environments with distributed permissions requiring continuous enforcement
- Multi-organization policy consistency

**Less Suitable For:**
- Organizations with declarative infrastructure-as-code management
- Highly restricted environments where only super-users can change policies

## Integration & Community

**Testing Framework:**
- Can run via Minder API: query current compliance status
- Manual evaluation tool available but underdocumented
- CI/CD integration possible (state-based compliance checking)

**Philosophy:**
- Emphasis on meaningful security practices, not just compliance checkboxes
- Remediation over pure monitoring
- Continuous vs. one-shot policy evaluation

## Meeting Appearances
- [[2026-01-07-tag-security-general]] — Major demo and discussion of capabilities, deployment, limitations
