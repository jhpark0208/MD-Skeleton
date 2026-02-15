# AGENTS.md
Codex Orchestration Entry Point

This file defines the orchestration model, agent roles, and execution rules.

Codex MUST read this file first before performing any task.

Then Codex MUST read, in order:

1. ARCHITECTURE.md
2. CONTRACTS.md
3. SPEC.md
4. SCOPE_MAP.md
5. DECISIONS.md
6. PARALLEL.md
7. HANDOFF_TEMPLATE.md
8. agents/00-shared.md
9. agents/manager.md
10. agents/tech_lead.md
11. agents/planner.md
12. agents/implementer.md
13. agents/tester.md
14. agents/debugger.md
15. agents/reviewer.md
16. agents/refactor.md
17. agents/release.md

---

# 0) Purpose

This file ensures:

- consistent orchestration
- safe parallel execution
- predictable integration
- self-healing capability

---

# 1) Orchestration Model

This system uses a Manager–Worker model.

Manager responsibilities:

- interpret tasks
- update SSOT files when necessary
- split work into scopes
- assign ownership
- integrate results

Worker responsibilities:

- operate only within assigned scope
- follow SSOT files
- produce handoff upon completion

Workers MUST NOT operate outside assigned scope.

---

# 2) Single Source of Truth Authority

SSOT files have absolute authority:

1. ARCHITECTURE.md
2. CONTRACTS.md
3. SPEC.md
4. SCOPE_MAP.md
5. DECISIONS.md

If implementation conflicts with SSOT:

SSOT wins.

Worker MUST NOT override SSOT.

Worker MUST request Manager update SSOT first.

---

# 3) Parallel Execution Model

Parallel execution is enabled via scope ownership.

Workers may operate in parallel ONLY if:

- ownership does not overlap
- SCOPE_MAP.md allows modification
- shared files are not modified without lock

Manager coordinates parallel execution.

---

# 4) Self-Healing Loop (MANDATORY)

Workers MUST use iterative correction:

Step 1: PLAN
Step 2: IMPLEMENT
Step 3: VALIDATE

If failure detected:

Step 4: DIAGNOSE
Step 5: FIX
Step 6: RE-VALIDATE

Repeat until stable or escalation required.

If failure caused by SSOT conflict:

STOP

Request Manager update SSOT.

---

# 5) Change Authority Rules

Workers MAY modify:

- files within owned scope

Workers MUST NOT modify:

- shared files
- SSOT files
- out-of-scope files

Manager owns shared files by default.

---

# 6) Integration Model

Workers MUST produce handoff using HANDOFF_TEMPLATE.md.

Manager integrates handoffs in priority order:

1. SSOT updates
2. Data layer changes
3. Application layer changes
4. UI layer changes
5. Documentation
6. QA

Manager resolves conflicts.

---

# 7) Compliance Checklist

Before implementing, Codex MUST verify:

- SSOT alignment
- scope ownership
- architectural compliance
- contract compliance

If unclear:

STOP

Request Manager clarification.

Do NOT speculate.
