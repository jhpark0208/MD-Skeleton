# ARCHITECTURE.md
Single Source of Truth: System Architecture

This document defines the system structure, component boundaries,
dependency rules, and architectural constraints.

All Workers and Manager MUST follow this architecture.

If implementation requires architectural changes:
- STOP
- request Manager and Tech Lead update to this document first

Do NOT silently introduce architectural divergence.

---

# 0) Purpose

This file ensures:

- consistent system structure
- safe parallel development
- prevention of architectural drift
- predictable integration

This document is language-agnostic and framework-agnostic.

Replace placeholders once system structure and tech stack are decided.

---

# 1) System Overview

System type:
- <web application / mobile application / service / library / hybrid>

Primary responsibilities:
- <RESPONSIBILITY_1>
- <RESPONSIBILITY_2>
- <RESPONSIBILITY_3>

Primary users:
- <USER_TYPE_1>
- <USER_TYPE_2>

System boundaries:

The system includes:
- <COMPONENT_GROUP_1>
- <COMPONENT_GROUP_2>

The system does NOT include:
- <EXTERNAL_SYSTEM_1>
- <EXTERNAL_SYSTEM_2>

---

# 2) Component Model

Define conceptual components.

Use logical components, NOT language-specific constructs.

---

## Component: UI Layer

Responsibilities:
- render user interface
- capture user input
- manage presentation state

Must NOT:
- directly access persistence layer
- implement persistence logic

May depend on:
- Application / API Layer

Owned scope:
- ui

---

## Component: Application Layer

Responsibilities:
- coordinate system behavior
- process requests
- enforce validation rules
- orchestrate data operations

Must NOT:
- directly implement persistence storage logic
- directly implement UI rendering

May depend on:
- Data Layer
- Infrastructure Layer

Owned scope:
- api

---

## Component: Data Layer

Responsibilities:
- manage persistent state
- enforce data integrity
- store and retrieve data

Must NOT:
- implement UI logic
- implement application coordination logic

Owned scope:
- data

---

## Component: Infrastructure Layer

Responsibilities:
- provide runtime environment
- provide configuration
- provide deployment support

Must NOT:
- implement business logic
- implement UI logic

Owned scope:
- infra

---

## Component: Documentation Layer

Responsibilities:
- describe system usage and behavior
- reflect system architecture and contracts

Owned scope:
- docs

---

## Component: QA / Validation Layer

Responsibilities:
- validate system behavior
- detect regressions
- ensure contract compliance

Owned scope:
- qa

---

# 3) Dependency Rules (MANDATORY)

Default dependency direction:

UI Layer → Application Layer → Data Layer

Infrastructure Layer supports all layers.

Documentation and QA may observe all layers.

---

## Allowed dependencies

UI Layer may depend on:
- Application Layer

Application Layer may depend on:
- Data Layer
- Infrastructure Layer

Data Layer may depend on:
- Infrastructure Layer

QA Layer may depend on:
- UI Layer
- Application Layer
- Data Layer

Documentation Layer may depend on:
- all layers (read-only)

---

## Forbidden dependencies

UI Layer MUST NOT depend on:
- Data Layer directly

Data Layer MUST NOT depend on:
- UI Layer
- Application Layer

Infrastructure Layer MUST NOT depend on:
- business logic

---

# 4) Communication Model

Interaction style:

- <request/response>
- <event-driven>
- <command/query>

Example conceptual flow:

User →
UI Layer →
Application Layer →
Data Layer →
Application Layer →
UI Layer →
User

Replace with actual flow later if needed.

---

# 5) State Ownership

Presentation state owned by:
- UI Layer

Application state owned by:
- Application Layer

Persistent state owned by:
- Data Layer

Configuration state owned by:
- Infrastructure Layer

---

# 6) Cross-Cutting Concerns

Define concerns affecting multiple layers.

Examples:

Concern: Error handling
Owner layer: Application Layer

Concern: Data validation
Owner layer: Application Layer

Concern: Persistence integrity
Owner layer: Data Layer

Concern: Configuration
Owner layer: Infrastructure Layer

Replace or extend as needed.

---

# 7) Architectural Constraints

Define system-wide constraints.

Performance constraints:
- <CONSTRAINT_PLACEHOLDER>

Security constraints:
- <CONSTRAINT_PLACEHOLDER>

Reliability constraints:
- <CONSTRAINT_PLACEHOLDER>

Compatibility constraints:
- <CONSTRAINT_PLACEHOLDER>

---

# 8) Scalability Model (Optional)

Expected scale:

- users: <ESTIMATE>
- requests: <ESTIMATE>
- data size: <ESTIMATE>

---

# 9) Extensibility Rules

Allowed extensions:

- new UI features
- new Application Layer features
- new Data entities

Extensions MUST NOT:

- violate dependency rules
- introduce circular dependencies
- bypass Application Layer coordination

---

# 10) Authority and Change Control

Manager owns architectural decisions with Tech Lead technical adjudication.

Workers MUST NOT modify architecture without approval.

Architectural changes MUST update:

- ARCHITECTURE.md
- CONTRACTS.md (if affected)
- SCOPE_MAP.md (if affected)
- DECISIONS.md (record decision)

---

# 11) Worker Compliance Checklist

Before implementing changes, Workers MUST verify:

- change respects layer boundaries
- change respects dependency rules
- change aligns with CONTRACTS.md
- change aligns with SPEC.md

If violation detected:

STOP

Request architectural clarification.

Do NOT implement speculative architecture.
