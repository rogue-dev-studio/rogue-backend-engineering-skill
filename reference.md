# Backend Engineering - Reference

## Layering

| Layer | Responsibility |
|-------|----------------|
| Transport | HTTP/CLI: parse, authorize entry, map response |
| Application/Service | Use-case, transactions, orchestration |
| Domain | Pure business rules when the project separates them |
| Persistence | Eloquent/Query/Repository |

## Laravel-oriented notes (when stack is Laravel)

- Form Request for validation; Policy for authz
- Resource/API Resource for response shaping
- Job + queue for async work
- Do not put long business rules in Migration/Observer without documentation

## Node-oriented notes (when stack is Node)

- Thin router; service module; schema validation (Zod/etc. per project)
- Centralized error middleware

## Anti-patterns

- God service without bounds
- Query in Blade/React via raw SQL string
- Silent catch that swallows errors
- Cache without TTL/invalidation
