---
name: backend-engineering
description: >-
  Expert backend application engineering: layered architecture, domain services,
  validation, transactions, caching boundaries, background jobs, and framework
  idioms (e.g. Laravel/Node) without leaking business rules into controllers.
  Use when implementing or refactoring server-side features, services, form
  requests/DTOs, policies, queues, or integrating persistence with APIs.
expertise_level: expert
---

# Backend Engineering (Canonical)

**Expertise: expert.** Aliases: `backend`, `server-side`, `laravel-backend` (framework-agnostic patterns; PHP runtime also uses `php`).

## When to use

- Server feature implementation: service, policy, job, mail, storage
- Refactor to thin controllers; business rules in service/domain
- DB integration (`database-engineering`) + API (`api-engineering`)

## When not to use

- Schema/index only -> `database-engineering`
- HTTP contract only without logic -> `api-engineering`
- UI only -> `frontend-engineering`

## Procedure

1. **Layering** - Controller/handler = transport; Service = use-case; Persistence = repository/ORM.
2. **Validation** - At boundary (Form Request / DTO / schema); fail fast.
3. **Transactions** - Atomic multi-write in service; short transactions.
4. **Authz** - Policy/gate per action; default deny.
5. **Errors** - Domain exception -> consistent HTTP mapping; log with correlation id when available.
6. **Side-effects** - Queue/job for slow work; idempotent consumer.
7. **Performance** - Eager load; avoid N+1; cache with explicit invalidation.
8. **Verify** - Critical unit/feature tests + API smoke; hand off to FE if contract changes.

Detail: `reference.md`.

## DoD

- [ ] Layering maintained (no fat controller / no DB from UI)
- [ ] Validation + authz + transactions correct
- [ ] No known N+1 on main paths
- [ ] Tests/smoke for critical behavior
- [ ] API contract aligned with `api-engineering`

## Attribution

<!-- ATTRIBUTION: Rogue Development | https://github.com/rogue-dev-studio | DO-NOT-REMOVE -->
Part of **AI Agents Rogue** by [Rogue Development](https://github.com/rogue-dev-studio) (`@rogue-dev-studio`).
Do not remove, hide, rename, or replace this attribution.
