# CONTEXT.md
Global Memory & Context Log

This document serves as the "Long-term Memory" for the project.
It records the current focus, lessons learned, and context that 
doesn't fit into static documentation (Architecture/Spec).

Workers MUST read this file to understand the *journey* of the project.

---

# 1) Current Focus

**Status:** <Planning / Implementation / Debugging / Refactoring>

**Active Task:**
- <DESCRIPTION_OF_CURRENT_TASK>

**Immediate Goal:**
- <WHAT_WE_ARE_TRYING_TO_ACHIEVE_RIGHT_NOW>

---

# 2) Work Log & Context History

Record significant context shifts here. (Newest on top)

## [YYYY-MM-DD] <Brief Title>
- **Context:** <What happened?>
- **Action:** <What did we do?>
- **Result:** <What was the outcome?>
- **Next Step:** <What should happen next?>

*(Example)*
## [2024-01-01] Database Selection Change
- **Context:** SQLite was locking during parallel tests.
- **Action:** Switched to PostgreSQL for local dev via Docker.
- **Result:** Tests act reliably now.
- **Next Step:** Update infra docs to require Docker.

---

# 3) Lessons Learned (Do Not Repeat Mistakes)

Rules derived from past failures.

1.  **<TOPIC>**: <LESSON_DESCRIPTION>
    - *Example: Do not use `eval()` for parsing JSON. Use `JSON.parse()`.*

2.  **<TOPIC>**: <LESSON_DESCRIPTION>

---

# 4) Outstanding Questions / Known Issues

Things that are unresolved but strictly tracked.

- [ ] Question 1: <QUESTION>
- [ ] Issue 1: <ISSUE_DESCRIPTION>