# ADR Index

One line per decision — the rule, not the reasoning. Read the full ADR (`.arc/decisions/ADR-NNNN-*.md`) for context and rationale.

## Accepted — binding rules

| ADR | Category | Status | Rule |
|---|---|---|---|
| ADR-0001 | component | accepted | Server-side business logic and data access live in this service and are exposed to clients only through its API. |
| ADR-0002 | component | accepted | Only the Source service reads or writes the database, and schema changes go through Prisma migrations. |
