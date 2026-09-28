# Rezo Node

🇫🇷 [Version française](./README.md)

[![License](https://img.shields.io/badge/License-All%20rights%20reserved-lightgrey.svg)](./LICENSE)
[![Django](https://img.shields.io/badge/Django-6.1-green?logo=django)](https://www.djangoproject.com/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org/)

Solo territory-capture game in the vein of Ingress (portals, links, capture), rendered with an
abstract Mini Metro-style visual. Personal practice project — no defense, no external deadline.

---

## Goals

- Build skills in Django + Django REST Framework + Channels (backend) and Next.js/TypeScript (frontend).
- Build a portfolio piece demonstrating a full game design process (game design → use cases → user stories → implementation).
- Experiment with multi-platform publishing (PWA → Play Store → Steam, exploratory).

---

## Status

**Scaffolding only** — Django and Next.js initialized, Postgres connection configured. No model,
view, or game logic implemented yet. See [adr/](./adr/) for architecture decisions already made.

---

## Architecture

Django + DRF + Channels backend (REST API + real-time WebSocket), separate Next.js frontend,
shared Postgres instance on Caesura (Raspberry Pi 5 homelab). Repo structure, decisions already
made, and what's still to build: see [docs/architecture.en.md](./docs/architecture.en.md).

---

## Local development

```bash
cd api && python -m venv venv && source venv/bin/activate && pip install -r requirements.txt
cd web && npm install
```

Full setup details, required environment variables: see
[docs/developpement.en.md](./docs/developpement.en.md).

---

## Environment variables

Full list with descriptions: see [docs/environnement.en.md](./docs/environnement.en.md).

---

## Real-time

Planned broadcast of board state over WebSocket (Django Channels). Current status: see
[docs/temps-reel.en.md](./docs/temps-reel.en.md).

---

## Deployment

Target: Docker on Caesura. Not yet configured. See
[docs/deploiement.en.md](./docs/deploiement.en.md).

---

## Stack

| Layer | Technology |
|---|---|
| Backend | Django 6.1 · Django REST Framework · Django Channels (Daphne/ASGI) |
| Database | PostgreSQL (shared instance, hosted on Caesura) |
| Frontend | Next.js 16 (App Router) · React 19 · TypeScript · Sass |
| Target infra | Docker · Caesura (Raspberry Pi 5 homelab) |
| Target auth | Stateless JWT (`djangorestframework-simplejwt`) · argon2id (see [ADR-0003](./adr/0003-auth-jwt-argon2id.md)) |

## In-depth documentation

- [Architecture and repo structure](./docs/architecture.en.md)
- [Local development](./docs/developpement.en.md)
- [Environment variables](./docs/environnement.en.md)
- [Real-time (WebSocket/Channels)](./docs/temps-reel.en.md)
- [Deployment](./docs/deploiement.en.md)
- [Accessibility](./docs/accessibilite.en.md)
- [Handoff guide](./docs/guide-de-reprise.en.md)
- [Architecture Decision Records](./adr/README.md)

## Contributing

See [docs/en/CONTRIBUTING.md](./docs/en/CONTRIBUTING.md).

## Troubleshooting

See [TROUBLESHOOTING.en.md](./TROUBLESHOOTING.en.md).

## Security

To report a vulnerability, see [docs/en/SECURITY.md](./docs/en/SECURITY.md) — no public issue.

## License

**All rights reserved** — see [LICENSE](./LICENSE). The code is publicly visible as a portfolio
piece; this is not an open source project, and no license to use or contribute is granted.

---

Made by **Jacques Duchamplecheval** ([alithiel31](https://github.com/Alithiel31))
