# MD-Skeleton
[Stack-Adaptive] Customizable AI Markdown templates for developers.

Codex-optimized repository template for safe parallel development using a Single Source of Truth (SSOT) architecture.

This structure ensures predictable integration, contract safety, and architectural consistency across human and agent contributors.

---

# Core Concept

This repository uses a Manager–Tech Lead–Worker orchestration model.

Manager:
- defines requirements
- assigns scope
- coordinates handoffs and integration

Tech Lead:
- owns technical judgment for architecture consistency
- enforces Clean Code and security standards
- adjudicates complex trade-offs before implementation

Workers:
- operate within assigned scope
- follow SSOT files
- submit handoffs

SSOT always overrides implementation.

---

# Single Source of Truth (SSOT)

These files define authoritative system behavior:

| File | Purpose |
|-----|--------|
| CONTEXT.md | long-term project memory |
| ARCHITECTURE.md | system structure and dependency rules |
| CONTRACTS.md | data and interface contracts |
| SPEC.md | feature requirements |
| SCOPE_MAP.md | file ownership |
| DECISIONS.md | architectural decision history |

Do not implement behavior that conflicts with SSOT.

---

# Orchestration Files

| File | Purpose |
|-----|--------|
| AGENTS.md | orchestration entry point |
| CONTEXT.md | long-term context memory |
| PARALLEL.md | parallel execution rules |
| HANDOFF_TEMPLATE.md | Worker → Manager handoff format |
| agents/ | role-specific agent instructions |
| agents/tech_lead.md | technical governance and quality review |

---

# Development Workflow

Typical flow:

1. Define requirements in SPEC.md
2. Define contracts in CONTRACTS.md (if needed)
3. Align design with Tech Lead for quality/security/architecture decisions
4. Assign ownership via SCOPE_MAP.md
5. Implement within scope
6. Submit handoff
7. Manager integrates changes

---

# Parallel Safety

Workers MUST:

- modify only owned files
- follow SSOT
- avoid modifying shared files

If unclear, escalate to Manager.

---

# Getting Started

Before implementation:

1. Update ARCHITECTURE.md
2. Update CONTRACTS.md
3. Define first feature in SPEC.md
4. Assign scope in SCOPE_MAP.md

Then begin implementation.

---

# Compatibility

Works with any language or framework:

- Node.js / TypeScript
- Python / FastAPI
- Java / Spring
- Go
- Rust
- Swift / Kotlin
- and others

---

# License

Apache License 2.0
