# Security

🇫🇷 [Version française](../../SECURITY.md)

## Reporting a vulnerability

Please **do not** open a public issue to report a security flaw — a regular GitHub issue exposes
it to everyone before a fix exists.

Report via **[the repo's Security tab](https://github.com/Alithiel31/rezo-node/security/advisories/new)**
(GitHub Security Advisories) — the report stays private between you and the maintainer.

### What we can promise

- The project is maintained by a single person, in their spare time: no formal SLA.
- The project is currently a scaffold with no exposed functionality — the scope below will
  evolve as business logic gets written.

## Scope

In scope:

- The Django backend (`api/`) and its direct dependencies.
- The Next.js frontend (`web/`) and its direct dependencies.

Out of scope:

- Caesura's shared Postgres instance (shared infrastructure, outside this repo).
- Any flaw requiring already-privileged access to Caesura infrastructure.

## What's already in place

_To be filled in over time_ — the only security decision made so far is the authentication
approach (stateless JWT + argon2id, CORS restricted to the frontend's domain), documented in
[ADR-0003](../../adr/0003-auth-jwt-argon2id.md); it is not implemented yet.

## Supported versions

A single deployment is planned, no version branches: only the code on `main` will receive
security fixes once the project is in production.
