# SPEC.md
Single Source of Truth: Feature and System Specification

This document defines functional requirements, expected behavior,
and success criteria for the system or feature.

All Workers MUST follow this specification.

If implementation reveals ambiguity or missing requirements:

- STOP
- request Manager clarification (and Tech Lead clarification for architecture/quality/security implications), then update this document first

Do NOT implement speculative behavior.

---

# 0) Purpose

This document ensures:

- consistent feature implementation
- alignment between Workers
- prevention of misinterpretation
- predictable system behavior

This document is language-agnostic and framework-agnostic.

Replace placeholders once feature/system requirements are defined.

---

# 1) Feature Overview

Feature name:
- Claude Code Adaptation for MD-Skeleton

Description:
- migrate orchestration documentation to Claude Code terminology and provide executable SSOT defaults

Primary goal:
- enable teams to start scoped AI-assisted development immediately without unresolved template placeholders

Non-goals:
- building application runtime features beyond documentation and orchestration definitions

---

# 2) Actors / Users

Define who interacts with the system.

Example placeholders:

Actor: Manager

Description:
- orchestrates scope assignment, escalation routing, and integration sequencing

Capabilities:
- assign ownership using SCOPE_MAP.md
- approve or reject shared-file updates with Tech Lead alignment when required

Constraints:
- must enforce SSOT priority and stop work on unresolved architecture or contract ambiguity

Add more actors if needed.

---

# 3) User Stories (Agile)

Describe requirements from the user's perspective to ensure value delivery.

Format: "As a ROLE, I want FEATURE, so that BENEFIT."

## Story: Baseline Orchestration Initialization

**User Story:**
> As a **project maintainer**
> I want to **initialize SSOT and agent-role documents for Claude Code**
> So that **contributors can execute tasks safely with clear ownership and gates**

**Acceptance Criteria (Gherkin syntax preferred):**

Scenario 1: SSOT baseline is concrete
- Given the repository starts from template placeholders
- When initialization is completed
- Then ARCHITECTURE, CONTRACTS, SPEC, SCOPE_MAP, DECISIONS, and CONTEXT contain actionable defaults

Scenario 2: Governance rules are executable
- Given a worker starts an implementation task
- When the worker reads AGENTS and scope guidance
- Then the worker can identify escalation gates and handoff requirements without ambiguity

---

# 4) Functional Requirements

Define required system behavior.

---

## Requirement: FR-1

Description:
- repository documentation must use Claude Code terminology where agent runtime naming is explicit

Priority:
- HIGH

Source:
- SYSTEM

Acceptance criteria:

- AGENTS.md and onboarding prompts reference Claude Code instead of Codex where runtime-specific wording appears
- README.md accurately describes the repository as Claude Code-oriented

---

## Requirement: FR-2

Description:
- SSOT placeholders must be replaced with concrete baseline values suitable for immediate project kickoff

Acceptance criteria:

- no unresolved angle-bracket placeholders remain in core SSOT files targeted by initialization

---

Add additional requirements as needed.

---

# 5) Behavioral Expectations

Define expected system behavior.

---

## Success Behavior

System MUST:

- provide unambiguous ownership and escalation rules before implementation
- preserve consistency across architecture, contracts, scope map, and decisions

---

## Failure Behavior

System MUST:

- handle failure safely
- provide consistent error structure

System MUST NOT:

- expose sensitive information
- enter inconsistent state

---

# 6) State Expectations

Define expected states.

States:

- planning
- execution_ready
- active_execution

State transitions MUST follow CONTRACTS.md if defined.

---

# 7) Edge Cases

Define uncommon but valid scenarios.

Examples:

- branch naming conflicts with existing refs (e.g., cannot create main/child when main exists)
- cross-document rule conflicts (e.g., integration order mismatches across governance files)

System MUST handle edge cases safely.

---

# 8) Non-Functional Requirements

Define system qualities.

Performance requirements:

- documentation updates should remain concise enough for human review in a single pass

Reliability requirements:

- orchestration flow must stay executable even when one scope is blocked, through explicit escalation paths

Security requirements:

- no document may require exposing secrets, keys, or sensitive internal infrastructure details

Usability requirements:

- onboarding prompts must be understandable by both human maintainers and AI agents without external context

Compatibility requirements:

- process definitions should remain portable across terminal-first coding assistants

---

# 9) Constraints

Define implementation constraints.

Examples:

Technical constraints:

- repository is markdown-first and should avoid coupling to a single programming language stack

Business constraints:

- must support predictable collaboration among multiple contributors with minimal coordination overhead

Operational constraints:

- shared-file modifications require manager-controlled approval flow

---

# 10) Success Criteria (Definition of Done)

Feature/system considered complete when:

- functional requirements satisfied
- CONTRACTS.md followed
- ARCHITECTURE.md respected
- no critical failures observed
- expected behaviors verified

---

# 11) Out of Scope

Define explicitly excluded behavior.

Examples:

- implementing product-specific application features
- introducing runtime infrastructure provisioning beyond documentation scope

Workers MUST NOT implement out-of-scope behavior.

---

# 12) Validation Guidelines (Generic)

Workers SHOULD validate:

- expected success behavior
- failure behavior
- edge cases
- state consistency

Validation MUST follow CONTRACTS.md and ARCHITECTURE.md.

---

# 13) Authority and Change Control

Manager owns this document with Tech Lead review for technical quality and architecture-sensitive updates.

Workers MUST NOT modify this document without approval.

Specification changes MUST be documented before implementation changes.

---

# 14) Worker Compliance Checklist

Before implementing, Workers MUST verify:

- requirement exists in this document
- behavior aligns with CONTRACTS.md
- behavior aligns with ARCHITECTURE.md

If requirement unclear:

STOP

Request clarification.

Do NOT implement speculative behavior.
