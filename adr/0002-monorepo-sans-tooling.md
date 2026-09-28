# ADR-0002 — Monorepo sans tooling dédié

**Statut** : accepté (2026-09)

## Contexte

Le backend Django (`api/`) et le frontend Next.js (`web/`) doivent cohabiter dans un même repo pour un projet solo, sans besoin de partager du code entre les deux (pas de types/schémas générés partagés, pas de package commun).

## Décision

Structure en monorepo simple : deux dossiers (`api/`, `web/`) dans un seul repo Git, sans outil de monorepo dédié (pas de Turborepo, pas de Nx).

## Conséquences

- Simplicité maximale pour un projet solo — pas de configuration d'outillage à maintenir.
- Pas de build orchestration commune : chaque dossier a son propre cycle de build/déploiement, ce qui convient au déploiement séparé prévu (API et frontend déployés indépendamment sur Caesura).
- À reconsidérer seulement si du code partagé apparaît (ex. schémas de validation dupliqués entre DRF serializers et types TypeScript).
