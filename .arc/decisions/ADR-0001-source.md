---
id: ADR-0001
category: component
title: Source
status: accepted
superseded_by: null
component_id: comp_source
responsibility: Express-based Node.js REST API in TypeScript, packaged with a Dockerfile;
  handles auth (JWT), articles, profiles and tags, and reads and writes the database
  through Prisma.
kind: api_service
split_reason: 'Already built: the Express service with a Dockerfile at the root of
  the backend repository. It is a separate server runtime from the React client.'
talks_to:
- component_id: comp_relational_database
  interaction: sync
  evidence: src/prisma/prisma-client.ts
rule: Server-side business logic and data access live in this service and are exposed
  to clients only through its API.
evidence:
- type: scan
  ref: src/main.ts
- type: scan
  ref: src/app/routes/routes.ts
basis: derived
---

## Context

The draft recorded none for this component.

## Decision

**Rule.** Server-side business logic and data access live in this service and are exposed to clients only through its API.

Express-based Node.js REST API in TypeScript, packaged with a Dockerfile; handles auth (JWT), articles, profiles and tags, and reads and writes the database through Prisma.

Kept separate because Already built: the Express service with a Dockerfile at the root of the backend repository. It is a separate server runtime from the React client..

## Talks to

- **Relational Database** (sync) — src/prisma/prisma-client.ts

## Alternatives considered

The draft recorded none for this component.

## Consequences

The draft recorded none for this component.

## Evidence

Basis: derived.
- scan: src/main.ts
- scan: src/app/routes/routes.ts
