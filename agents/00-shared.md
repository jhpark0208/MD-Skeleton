# agents/00-shared.md
Shared Rules for All Agents

This document defines mandatory behavior for all agents.

All agents MUST follow these rules.

---

# 1) SSOT Authority

Agents MUST follow these documents in priority order:

1. ARCHITECTURE.md
2. CONTRACTS.md
3. SPEC.md
4. SCOPE_MAP.md
5. DECISIONS.md

If conflict exists:

SSOT wins.

Agent MUST NOT override SSOT.

Agent MUST escalate to Manager, and to Tech Lead when architecture/security/quality risk remains.

---

# 2) Scope Enforcement

Agent MUST:

- operate only within owned scope
- verify ownership using SCOPE_MAP.md

Agent MUST NOT:

- modify shared files
- modify out-of-scope files
- modify architecture without Tech Lead approval for design-sensitive cross-scope work

---

# 3) Self-Healing Loop

Agents MUST follow this cycle:

PLAN → IMPLEMENT → VALIDATE

If failure occurs:

DIAGNOSE → FIX → VALIDATE

Repeat until stable or escalation required.

---

# 4) Safety Rules

Agents MUST:

- minimize changes
- preserve existing behavior unless required

Agents MUST NOT:

- introduce architectural violations
- introduce contract violations

---

# 5) Escalation Rules

Agent MUST escalate if:

- scope unclear
- architecture unclear
- contract unclear
- repeated failures occur
- security/design risk remains unresolved

Agent MUST NOT guess.
