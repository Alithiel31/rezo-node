# Déploiement

🇬🇧 [English version](./deploiement.en.md)

[Retour au README](../README.md)

## Cible

Déploiement prévu via Docker sur **Caesura** (homelab Raspberry Pi 5 du mainteneur), API et
frontend déployés séparément (voir [ADR-0002](../adr/0002-monorepo-sans-tooling.md)).

## État actuel

Aucun `docker-compose.yml`, `Dockerfile` ni workflow CI/CD n'existe encore dans ce dépôt.

## Publication multi-plateforme (exploratoire)

Un des objectifs du projet (voir [README](../README.md#objectifs)) est d'expérimenter la
publication au-delà du web : PWA → Play Store → Steam. Purement exploratoire à ce stade, aucune
démarche entamée.

## À compléter au fur et à mesure

- `docker-compose.yml` et `Dockerfile` une fois le déploiement configuré.
- Pipeline CI/CD.
- Variables d'environnement de production (voir [docs/environnement.md](./environnement.md)).
