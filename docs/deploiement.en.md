# Deployment

🇫🇷 [Version française](./deploiement.md)

[Back to README](../README.en.md)

## Target

Deployment is planned via Docker on **Caesura** (the maintainer's Raspberry Pi 5 homelab), with
the API and frontend deployed separately (see [ADR-0002](../adr/0002-monorepo-sans-tooling.md)).

## Current state

No `docker-compose.yml`, `Dockerfile`, or CI/CD workflow exists in this repo yet.

## Multi-platform publishing (exploratory)

One of the project's goals (see [README](../README.en.md#goals)) is to experiment with
publishing beyond the web: PWA → Play Store → Steam. Purely exploratory at this stage, nothing
started yet.

## To be filled in over time

- `docker-compose.yml` and `Dockerfile` once deployment is configured.
- CI/CD pipeline.
- Production environment variables (see [docs/environnement.en.md](./environnement.en.md)).
