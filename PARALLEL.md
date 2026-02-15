# PARALLEL.md
Parallel Execution and Ownership Rules

This document defines how parallel execution is safely performed.

---

# 0) Purpose

This file ensures:

- safe parallel work
- prevention of file conflicts
- predictable integration

---

# 1) Scope-Based Parallelism

Parallel work is allowed only when scope ownership does not overlap.

Ownership is defined in:

SCOPE_MAP.md

Workers MUST operate only within owned scope.

---

# 2) Shared File Protection

Shared files include:

- ARCHITECTURE.md
- CONTRACTS.md
- SPEC.md
- DECISIONS.md
- SCOPE_MAP.md
- AGENTS.md
- PARALLEL.md
- HANDOFF_TEMPLATE.md

Also includes:

- global config files
- dependency lock files

Workers MUST NOT modify shared files without Manager approval.

---

# 3) Ownership Verification

Before modifying any file, Worker MUST verify:

- file belongs to owned scope
- file is not shared

If ownership unclear:

STOP

Request Manager ownership assignment.

---

# 4) Work Isolation Model

Each Worker operates in isolation.

Workers MUST NOT:

- modify files owned by another Worker
- assume ownership implicitly

Manager coordinates integration.

---

# 5) Integration Order

Manager integrates changes in this order:

1. SSOT files
2. Data layer
3. Application layer
4. UI layer
5. Documentation
6. QA

This order prevents dependency conflicts.

---

# 6) Conflict Resolution

If conflict occurs:

Priority:

1. ARCHITECTURE.md
2. CONTRACTS.md
3. SPEC.md
4. SCOPE_MAP.md
5. DECISIONS.md
6. Manager decision

Workers MUST NOT resolve conflicts independently.

---

# 7) Parallel Safety Rules

Workers MUST:

- respect ownership boundaries
- avoid modifying shared files
- produce handoff

Workers MUST NOT:

- bypass ownership rules
- introduce conflicting changes

---

# 8) Escalation Rules

Worker MUST escalate to Manager if:

- ownership unclear
- contract unclear
- architecture unclear
- repeated failures occur

Worker MUST NOT proceed blindly.
