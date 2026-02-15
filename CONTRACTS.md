# CONTRACTS.md
Single Source of Truth: System Contracts

This document defines authoritative contracts between system components.

Contracts include:

- data entities and structures
- component interfaces
- interaction patterns
- error structures
- validation expectations

All Workers MUST follow this document.

If implementation requires contract changes:

- STOP
- request Manager and Tech Lead update to this document first

Do NOT silently introduce contract divergence.

---

# 0) Purpose

This document ensures:

- consistent interfaces across components
- safe parallel implementation
- predictable integration
- prevention of implicit or conflicting contracts

This document is language-agnostic and framework-agnostic.

Replace placeholders once system design is defined.

---

# 1) Component Interaction Contracts

Define how system components interact.

Use conceptual definitions.

---

## Interaction: UI → Application Layer

Purpose:
- process user requests
- retrieve and update system state

Input contract:

- task_request
  - type: string
  - required: true
  - description: user-provided instruction that defines the desired outcome

- context_references
  - type: array[string]
  - required: false
  - description: optional file paths or document identifiers that constrain execution

Output contract:

- execution_plan
  - type: object
  - description: ordered actions with ownership, risk, and escalation notes

- handoff_or_result
  - type: object
  - description: structured completion summary, including changed files and compliance status

Error contract:
- MUST follow Error Structure (see section 4)

---

## Interaction: Application Layer → Data Layer

Purpose:
- retrieve persistent data
- update persistent data

Input contract:

- document_path
- proposed_content_or_patch

Output contract:

- write_status
- revision_reference

Constraints:

- Data Layer enforces data integrity
- Application Layer enforces validation rules

---

# 2) Data Entity Contracts

Define conceptual entities.

Use logical definitions, not language-specific syntax.

---

## Entity: WorkItem

Description:
- a single scoped unit of work executed through the orchestration flow

Fields:

- id
  - type: string
  - required: true
  - nullable: false
  - description: unique identifier for the work item

- status
  - type: enum(pending,in_progress,blocked,done)
  - required: true
  - nullable: false
  - description: lifecycle state of the work item

Invariants (MUST always hold):

- id is unique within a project context
- status transitions follow the WorkItemLifecycle state machine

Ownership:

- owned by scope: api

Lifecycle:

Created by:
- Application Layer

Read by:
- Application Layer
- QA Layer

Updated by:
- Application Layer

Deleted by:
- Application Layer

---

# 3) State Transition Contracts (Optional but Recommended)

Define allowed state transitions.

---

## State Machine: WorkItemLifecycle

States:

- pending
- in_progress
- done

Allowed transitions:

- pending → in_progress
- in_progress → done

Forbidden transitions:

- done → in_progress

State ownership:

- owned by scope: api

---

# 4) Error Contract (MANDATORY)

All system components MUST follow this error structure.

---

## Error Structure

Error MUST include:

- code
  - type: string
  - description: machine-readable identifier

- message
  - type: string
  - description: human-readable description

- category
  - type: string
  - description: error classification

Optional:

- details
  - type: object
  - description: structured additional context

---

## Error Categories

Allowed categories:

- validation
- authorization
- not_found
- conflict
- system

Additional categories MAY be defined here.

---

## Error Handling Rules

MUST:

- return structured error
- avoid exposing sensitive internal details
- provide safe user-facing message

MUST NOT:

- invent new error structure without updating CONTRACTS.md
- return inconsistent error formats

---

# 5) Validation Contract

Define validation expectations.

Application Layer MUST:

- validate inputs
- enforce business rules

Data Layer MUST:

- enforce integrity constraints

UI Layer MUST:

- validate presentation-level inputs when applicable

---

# 6) Cross-Scope Contract Ownership

Contract ownership by scope:

UI scope:
- presentation contracts

Application scope:
- interaction contracts
- validation contracts

Data scope:
- entity contracts
- persistence contracts

Manager scope:
- cross-scope contracts
- shared contracts
- Tech Lead review applies when contracts change across multiple scopes or introduce security-sensitive boundaries

---

# 7) Versioning and Compatibility

Contract changes MUST follow:

- backward compatibility preferred
- breaking changes MUST be documented here first

Version placeholder:

Contract version:
- v1.0.0

Last updated:
- 2026-02-15
