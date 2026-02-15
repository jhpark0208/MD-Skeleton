# SCOPE_MAP.md
Single Source of Truth: Scope Ownership Map

This document defines file and directory ownership by scope.

Its purpose is to enable safe parallel development by preventing
multiple Workers from modifying the same files.

Workers MUST follow this document.

If ownership unclear:

- STOP
- request Manager ownership assignment

Do NOT modify files outside assigned scope.

---

# 0) Purpose

This file ensures:

- safe parallel execution
- prevention of file conflicts
- predictable integration
- clear ownership boundaries

This document is language-agnostic and framework-agnostic.

Replace placeholders once repository structure is defined.

---

# 1) Scope Definitions

Scopes represent logical ownership areas.

Default scopes:

- ui
- api
- data
- infra
- docs
- qa

Additional scopes MAY be added if needed.

---

# 2) Scope Ownership (Generic Template)

Replace placeholders with actual paths when repository structure exists.

---

## Scope: ui

Responsibilities:

- user interface
- presentation logic
- client interaction handling

Owned paths:

- templates/ui/
- examples/ui/

Examples (do not assume unless confirmed):

- frontend/
- ui/
- client/

Must NOT modify:

- data persistence logic
- infrastructure configuration
- shared contracts

---

## Scope: api

Responsibilities:

- application logic
- request handling
- orchestration of system behavior

Owned paths:

- templates/api/
- examples/api/

Examples:

- backend/
- api/
- services/

Must NOT modify:

- UI presentation logic
- persistence implementation directly

---

## Scope: data

Responsibilities:

- data structures
- persistence logic
- data integrity enforcement

Owned paths:

- templates/data/
- examples/data/

Examples:

- database/
- models/
- persistence/

Must NOT modify:

- UI logic
- application orchestration logic

---

## Scope: infra

Responsibilities:

- environment configuration
- deployment configuration
- runtime configuration

Owned paths:

- templates/infra/
- examples/infra/

Examples:

- config/
- infrastructure/
- deployment/

Must NOT modify:

- business logic
- presentation logic

---

## Scope: docs

Responsibilities:

- documentation
- usage guides
- architecture explanations

Owned paths:

- docs/
- README.md

---

## Scope: qa

Responsibilities:

- validation logic
- test definitions
- verification tools

Owned paths:

- tests/
- templates/qa/

Examples:

- tests/
- validation/

---

# 3) Shared / Manager-Owned Files

These files are shared and owned by Manager by default.

Workers MUST NOT modify these without Manager approval.

Shared files:

- ARCHITECTURE.md
- CONTRACTS.md
- SPEC.md
- DECISIONS.md
- SCOPE_MAP.md
- CLAUDE.md
- PARALLEL.md
- HANDOFF_TEMPLATE.md
- README.md
- CONTEXT.md
- agents/tech_lead.md
- agents/manager.md
- agents/

Also shared:

- root configuration files
- dependency lock files
- global configuration files

Examples (do not assume):

- package manager lock files
- global config files

Manager MAY grant temporary ownership.

---

# 4) Ownership Rules

Rule 1:

Worker MUST modify only owned paths.

Rule 2:

If file not mapped:

- Manager assigns ownership

Rule 3:

New files inherit ownership from directory.

Rule 4:

Shared files require Manager approval.

---

# 5) Conflict Resolution Priority

If ownership conflict occurs:

Priority order:

1. ARCHITECTURE.md
2. CONTRACTS.md
3. SPEC.md
4. SCOPE_MAP.md
5. Manager decision
6. Minimal change principle

---

# 6) Manager Responsibilities

Manager MUST:

- assign ownership when unclear
- prevent overlapping ownership
- update this document when repository structure evolves

---

# 7) Future Customization Instructions

When tech stack and repository structure are known:

Update:

- owned paths per scope
- shared files list
- scope responsibilities if needed

Do NOT remove scope structure.

---

# 8) Worker Compliance Checklist

Before modifying any file, Worker MUST verify:

- file belongs to owned scope
- file is not shared
- modification follows ARCHITECTURE.md
- modification follows CONTRACTS.md
- modification follows SPEC.md

If ownership unclear:

STOP

Request Manager assignment.

Do NOT modify file.
