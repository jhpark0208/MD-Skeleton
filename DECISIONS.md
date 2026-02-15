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

Example:

- DECISION-001: Initial system architecture
- DECISION-002: Error handling strategy
- DECISION-003: Data ownership model

Add entries as decisions are made.

---

# 3) Architectural Decisions

Record major structural decisions here.

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
