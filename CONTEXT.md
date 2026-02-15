# CONTEXT.md
Global Memory & Context Log

This document serves as the "Long-term Memory" for the project.
It records the current focus, lessons learned, and context that 
doesn't fit into static documentation (Architecture/Spec).

Workers MUST read this file to understand the *journey* of the project.

---

# 1) Current Focus

**Status:** Planning

**Active Task:**
- create Claude Code branch baseline and convert core governance documents from template placeholders to concrete defaults

**Immediate Goal:**
- make SSOT and orchestration docs immediately executable for a real project kickoff

---

# 2) Work Log & Context History

Record significant context shifts here. (Newest on top)

## [2026-02-15] Claude Code Baseline Initialization
- **Context:** Repository started with template placeholders and Codex-specific naming in key docs.
- **Action:** Created a new branch for Claude Code alignment and updated SSOT baseline values.
- **Result:** Core orchestration documents now contain concrete defaults and clearer governance expectations.
- **Next Step:** Add project-specific architecture/contracts/spec details before implementation work begins.

*(Example)*
## [2024-01-01] Database Selection Change
- **Context:** SQLite was locking during parallel tests.
- **Action:** Switched to PostgreSQL for local dev via Docker.
- **Result:** Tests act reliably now.
- **Next Step:** Update infra docs to require Docker.

---

# 3) Lessons Learned (Do Not Repeat Mistakes)

Rules derived from past failures.

1.  **Template Drift**: Unfilled placeholders cause inconsistent execution and interpretation across contributors.
    - *Always replace template tokens before starting real implementation tasks.*

2.  **Governance Ambiguity**: Missing gate criteria leads to risky implementation shortcuts.
    - *Require explicit Tech Lead gate status for architecture/security-sensitive changes.*

---

# 4) Outstanding Questions / Known Issues

Things that are unresolved but strictly tracked.

- [ ] Question 1: Should scope-owned paths be switched from template directories to actual repository directories after first feature scaffolding?
- [ ] Issue 1: Integration order wording differs between some governance docs and should be normalized in a follow-up decision.
