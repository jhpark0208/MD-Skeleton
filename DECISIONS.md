# DECISIONS.md
Single Source of Truth: Architectural and System Decisions Log

This document records important architectural, system, and design decisions.

Its purpose is to:

- preserve reasoning behind decisions
- prevent regression to rejected approaches
- ensure consistency across Workers
- provide context for future changes

All Workers MUST consult this document before making structural changes.

---

# 0) Purpose

This document ensures:

- decision traceability
- consistent system evolution
- prevention of conflicting implementation decisions

This document is language-agnostic and framework-agnostic.

---

# 1) Decision Record Format

Each decision MUST follow this format.

---

## Decision ID: DECISION-<NUMBER>

Date:
- <YYYY-MM-DD>

Status:
- proposed
- accepted
- rejected
- deprecated
- superseded

Decision summary:
- <SHORT_SUMMARY>

Context:
- <PROBLEM_DESCRIPTION>
- <CONSTRAINTS>
- <RELEVANT_REQUIREMENTS>

Options considered:

Option 1:
- description: <OPTION_DESCRIPTION>
- pros:
  - <PRO>
  - <PRO>
- cons:
  - <CON>
  - <CON>

Option 2:
- description: <OPTION_DESCRIPTION>
- pros:
  - <PRO>
- cons:
  - <CON>

Decision:

- <SELECTED_OPTION>
- explanation: <WHY_THIS_OPTION>

Consequences:

Positive:
- <POSITIVE_EFFECT>

Negative:
- <NEGATIVE_EFFECT>

Neutral:
- <NEUTRAL_EFFECT>

Affected components:

- <COMPONENT_1>
- <COMPONENT_2>

Related documents:

- ARCHITECTURE.md
- CONTRACTS.md
- SPEC.md
- <OTHER_DOCUMENT>

Supersedes:
- <DECISION_ID> (if applicable)

Superseded by:
- <DECISION_ID> (if applicable)

---

# 2) Decision Index

List all decisions here for quick reference.

Current decisions:

- DECISION-001: Introduce Tech Lead as technical governance authority above Workers and parallel to execution flow.

- Legacy examples (template placeholders):

  - DECISION-002: Initial system architecture
  - DECISION-003: Error handling strategy
  - DECISION-004: Data ownership model

Add entries as decisions are made.

---

# 3) Architectural Decisions

Record major structural decisions here.

## DECISION-001: Introduce Manager–Tech Lead–Worker governance model

Date:

- 2026-02-15

Status:

- accepted

Decision summary:

- Introduce `agents/tech_lead.md` and enforce a three-layer decision flow:
  - SSOT -> Tech Lead (for architecture/quality/security) -> Manager (for scope/integration)

Context:

- Problem: Existing pipeline only had Manager-worker model, which lacked a dedicated technical governance layer for architecture consistency and security.
- Constraints: Existing SSOT stack should remain authoritative.
- Requirements: Clarify responsibilities and maintain backward compatibility.

Options considered:

Option 1:

- Keep Manager only and add stricter SSOT checks in instructions.
- pros:
  - fewer roles
- cons:
  - limited review depth for design-sensitive changes
  - weaker technical governance in scaling teams

Option 2:

- Add Tech Lead role with escalation flow and explicit gate checkpoints.
- pros:
  - clearer architecture/security ownership
  - improves long-term consistency
- cons:
  - adds one additional routing step

Decision:

- Option 2: Add Tech Lead role and routing checks.
- explanation: Better controls for quality, consistency, and secure design decisions with minimal process overhead.

Consequences:

Positive:

- clearer accountability for cross-cutting technical risk
- cleaner decision record and escalation path

Negative:

- slight increase in process overhead for high-signal changes

Neutral:

- template-based handoff now includes Tech Lead gate fields

Affected components:

- AGENTS.md
- PARALLEL.md
- README.md
- HANDOFF_TEMPLATE.md
- agents/tech_lead.md
- DECISIONS.md

Related documents:

- ARCHITECTURE.md
- SPEC.md
- SCOPE_MAP.md
- PARALLEL.md
- AGENTS.md
- HANDOFF_TEMPLATE.md

Supersedes:

- None

Superseded by:

- None

---

Examples:

- layering model
- dependency rules
- state ownership

Add decisions using Decision Record Format.

---

# 4) Contract Decisions

Record decisions affecting CONTRACTS.md.

Examples:

- API structure
- error contract format
- entity ownership

---

# 5) Specification Decisions

Record decisions affecting SPEC.md.

Examples:

- feature behavior decisions
- UX expectations
- edge case handling decisions

---

# 6) Scope and Ownership Decisions

Record decisions affecting SCOPE_MAP.md.

Examples:

- scope boundaries
- ownership assignments
- shared file handling

---

# 7) Infrastructure Decisions

Record decisions affecting infrastructure.

Examples:

- configuration strategy
- deployment model
- environment handling

---

# 8) Change Control

Manager owns this document by default.

Workers MUST NOT modify decisions without approval.

Workers MAY propose decisions via handoff.

Manager MUST:

- review proposed decisions
- accept or reject decisions
- record accepted decisions here

---

# 9) Deprecation and Supersession Rules

When replacing a decision:

- mark old decision as superseded
- add new decision referencing old decision
- do NOT delete historical decisions

Maintain full history.

---

# 10) Worker Compliance Checklist

Before implementing structural or contract changes, Workers MUST verify:

- relevant decision exists
- implementation aligns with accepted decisions
- implementation does not contradict decisions

If contradiction detected:

STOP

Request decision clarification or update.

Do NOT override existing decisions.
