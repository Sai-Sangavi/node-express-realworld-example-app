---
id: ADR-0002
category: component
title: Relational Database
status: accepted
superseded_by: null
component_id: comp_relational_database
responsibility: Stores users, articles, comments, tags and follows; runs on PostgreSQL,
  with schema and migrations managed by Prisma in the backend repository.
kind: infrastructure
split_reason: 'Backing service the API depends on: Prisma schema declares a postgresql
  datasource (src/prisma/schema.prisma).'
rule: Only the Source service reads or writes the database, and schema changes go
  through Prisma migrations.
evidence:
- type: scan
  ref: src/prisma/schema.prisma
basis: derived
---

## Context

The draft recorded none for this component.

## Decision

**Rule.** Only the Source service reads or writes the database, and schema changes go through Prisma migrations.

Stores users, articles, comments, tags and follows; runs on PostgreSQL, with schema and migrations managed by Prisma in the backend repository.

Kept separate because Backing service the API depends on: Prisma schema declares a postgresql datasource (src/prisma/schema.prisma)..

## Alternatives considered

The draft recorded none for this component.

## Consequences

The draft recorded none for this component.

## Evidence

Basis: derived.
- scan: src/prisma/schema.prisma
