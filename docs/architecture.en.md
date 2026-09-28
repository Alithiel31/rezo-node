# Architecture

🇫🇷 [Version française](./architecture.md)

[Back to README](../README.en.md)

## Repo structure

```
rezo-node/
├── adr/         Architecture Decision Records
├── api/         Django + DRF + Channels backend
│   └── config/  Django project (settings, urls, asgi/wsgi)
│   └── games/    app — Faction, Carte, Partie, PartieFaction, ActionHistorique
│   └── links/    app — Lien, SiegeOrdre
│   └── portals/  app — PortailDefinition, Portail
└── web/         Next.js frontend (App Router, TypeScript, Sass)
```

Monorepo with no dedicated tooling (no Turborepo/Nx) — see
[ADR-0002](../adr/0002-monorepo-sans-tooling.md).

## Decisions already made

See [adr/](../adr/) for full detail (context, consequences):

- [ADR-0001](../adr/0001-backend-django-drf-channels.md) — Django + DRF + Channels backend
  (real-time WebSocket via Daphne/ASGI).
- [ADR-0002](../adr/0002-monorepo-sans-tooling.md) — `api/` + `web/` monorepo, no dedicated tooling.
- [ADR-0003](../adr/0003-auth-jwt-argon2id.md) — stateless JWT + argon2id authentication.

## Current state

- `api/config/urls.py` only registers `admin/` — no business routes yet.
- The three Django apps (`games`, `links`, `portals`) are installed, but their `models.py` and
  `views.py` are still the default stubs.
- `channels_redis`, `redis`, and `celery` are in `requirements.txt`, but no `CHANNEL_LAYERS` or
  Celery config exists in `settings.py` yet — installed ahead of time, not wired up.
- `web/` is a default `create-next-app` scaffold, with no game-specific page yet.

## To be filled in over time

- Data model diagram (ERD) once translated into `models.py`.
- WebSocket flow diagram once consumers are written (see
  [docs/temps-reel.en.md](./temps-reel.en.md)).
- Deployment diagram once Caesura infra is configured (see
  [docs/deploiement.en.md](./deploiement.en.md)).
