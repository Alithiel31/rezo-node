# Rezo Node

Jeu de territoire solo façon Ingress (portails, liens, capture) avec un rendu visuel abstrait façon Mini Metro. Projet de practice personnel — pas de soutenance ni d'échéance externe.

## Objectifs

- Monter en compétence sur Django + Django REST Framework + Channels (backend) et Next.js/TypeScript (frontend).
- Constituer une pièce de portfolio démontrant une conception de jeu complète (game design → use cases → user stories → implémentation).
- Expérimenter la publication multi-plateforme (PWA → Play Store → Steam, à but exploratoire).

## Stack

- **Backend** : Django + DRF + Channels (WebSocket temps réel), PostgreSQL.
- **Frontend** : Next.js (App Router, TypeScript, Sass).
- **Infra** : Docker, déployé sur Caesura (homelab Raspberry Pi 5).

## Structure du repo

```
api/     Backend Django (apps : games, links, portals)
web/     Frontend Next.js
adr/     Architecture Decision Records
```

`Conception/` et `Claude outputs/` sont exclus du repo (voir `.gitignore`) — conception détaillée disponible dans le Project Claude "Rezo-Node" (game design, use cases, user stories) et en local dans `Claude outputs/` (cahier des charges, MCD/MLD, suivi).

## Démarrage local

Voir `api/README.md` et `web/README.md`.

## Statut

Scaffolding uniquement (Django + Next.js initialisés, connexion Postgres configurée). Aucun modèle, vue ou composant métier implémenté pour l'instant. Voir `adr/` pour les décisions d'architecture déjà prises.
