# Codex Orchestration Entry Point

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
- clear technical quality gates

---

# 1) Orchestration Model

This system uses a Manager–Tech Lead–Worker model.

Manager responsibilities:

- interpret tasks and split work into scopes
- assign ownership using `SCOPE_MAP.md`
- coordinate handoff and integration

Tech Lead responsibilities:

- enforce architecture consistency and security posture
- gate quality decisions for design-sensitive changes
- preserve long-term maintainability and technical coherence

Worker responsibilities:

- operate only within assigned scope
- follow SSOT and shared rules
- produce handoff upon completion

Workers MUST NOT operate outside assigned scope.

---

# 2) Decision Authority

Authority ladder:

1. SSOT files:
   - ARCHITECTURE.md
   - CONTRACTS.md
   - SPEC.md
   - SCOPE_MAP.md
   - DECISIONS.md
2. Tech Lead technical judgment
3. Manager execution decision

If SSOT has no direct guidance and technical risk remains:

- Worker MUST escalate to Manager
- Manager MUST route to Tech Lead before proceeding
- For architecture/security/design-risk changes, Tech Lead MUST gate before implementation starts

SSOT wins all direct conflicts.

---

# 3) Single Source of Truth Authority

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
For technical risk, Worker MUST also include Tech Lead before proceeding.

---

# 4) Parallel Execution Model

Parallel execution is enabled via scope ownership.

Workers may operate in parallel ONLY if:

- ownership does not overlap
- SCOPE_MAP.md allows modification
- shared files are not modified without approval

Manager coordinates parallel execution.

For architecture/security-sensitive areas:

- Tech Lead review is required before implementation starts.

---

# 5) Self-Healing Loop (MANDATORY)

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

Request Manager and/or Tech Lead update SSOT.

---

# 6) Change Authority Rules

Workers MAY modify:

- files within owned scope

Workers MUST NOT modify:

- shared files without explicit approval
- SSOT files
- out-of-scope files

Manager owns shared files by default.
Tech Lead may request additional checkpoints on architecture/security/maintainability-sensitive changes.

Shared-files requiring Tech Lead review:

- architectural edits
- security-sensitive edits
- design-sensitive cross-cutting edits

---

# 7) Integration Model

Workers MUST produce handoff using HANDOFF_TEMPLATE.md.

Manager integrates handoffs in priority order:

1. SSOT updates
2. Data layer changes
3. Application layer changes
4. UI layer changes
5. Documentation
6. QA

Manager resolves conflicts.
Tech Lead signs off technical-quality-sensitive integrations.

---

# 8) Compliance Checklist

Before implementing, Codex MUST verify:

- SSOT alignment
- scope ownership
- architectural consistency
- security and maintainability implications

If unclear:

STOP

Request Manager and Tech Lead clarification.
