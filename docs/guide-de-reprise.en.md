# Handoff guide

🇫🇷 [Version française](./guide-de-reprise.md)

[Back to README](../README.en.md)

Rezo Node has a single real maintainer (**Jacques Duchamplecheval**, GitHub handle `Alithiel31`).
This document exists so that another person — or Jacques himself after a long break — can pick
the project back up. It's deliberately short for now: the project is a scaffold, nothing is
deployed yet.

## 1. Understanding the project — recommended reading order

1. [README.md](../README.en.md) — overview, goals, status
2. [adr/](../adr/) — architecture decisions already made
3. [docs/architecture.en.md](./architecture.en.md) — repo structure, current state
4. [docs/developpement.en.md](./developpement.en.md) — running the project locally
5. [docs/environnement.en.md](./environnement.en.md) — configuration variables

## 2. What's running, and where

| Component | Where | How to access |
|---|---|---|
| Source code | [`github.com/Alithiel31/rezo-node`](https://github.com/Alithiel31/rezo-node) | GitHub access |
| Development database | Shared Postgres on **Caesura** (maintainer's Raspberry Pi 5 homelab) | Network access to Caesura — **to be filled in by the maintainer** |
| Production application | None yet — project not deployed | — |

## 3. Secrets and access needed to act

No real secret is stored in this repo (see `.gitignore` and [docs/en/SECURITY.md](./en/SECURITY.md)).
To actually take over the project:

- **Admin access to the GitHub repo** [`Alithiel31/rezo-node`](https://github.com/Alithiel31/rezo-node)
- **Access to Caesura's shared Postgres** (real credentials matching `DB_USER`/`DB_PASSWORD`/`DB_HOST`, see [docs/environnement.en.md](./environnement.en.md))
- **Access to the "Rezo-Node" Project Claude workspace** — detailed design (game design, use cases, user stories, data model) lives outside the repo (see the [README](../README.en.md)'s Structure note) — **to be filled in by the maintainer** (where this workspace is hosted, how to access it)

## 4. Known risks to keep in mind

- **Single maintainer** — this document reduces the risk but does not remove it.
- **Design lives outside the repo** — detailed design documentation is not versioned with the
  code; without access to the associated Project Claude workspace, handoff is limited to the
  code and ADRs already written.
- **Nothing deployed** — no production infrastructure risk yet, but also no recovery procedure to
  document until one exists.

## To be filled in by the maintainer

- [ ] Where and how to access the "Rezo-Node" Project Claude workspace (design, data model)
- [ ] Access credentials for Caesura (shared Postgres, and later Docker/deployment)
- [ ] Trusted contact(s) in case the maintainer is unavailable for an extended period
