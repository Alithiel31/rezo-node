# Rezo Node

🇬🇧 [English version](./README.en.md)

[![License](https://img.shields.io/badge/License-All%20rights%20reserved-lightgrey.svg)](./LICENSE)
[![Django](https://img.shields.io/badge/Django-6.1-green?logo=django)](https://www.djangoproject.com/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org/)

Jeu de territoire solo façon Ingress (portails, liens, capture) avec un rendu visuel abstrait
façon Mini Metro. Projet de practice personnel — pas de soutenance ni d'échéance externe.

---

## Objectifs

- Monter en compétence sur Django + Django REST Framework + Channels (backend) et Next.js/TypeScript (frontend).
- Constituer une pièce de portfolio démontrant une conception de jeu complète (game design → use cases → user stories → implémentation).
- Expérimenter la publication multi-plateforme (PWA → Play Store → Steam, à but exploratoire).

---

## Statut

**Scaffolding uniquement** — Django + Next.js initialisés, connexion Postgres configurée. Aucun
modèle, vue ou composant métier implémenté pour l'instant. Voir [adr/](./adr/) pour les décisions
d'architecture déjà prises.

---

## Architecture

Backend Django + DRF + Channels (API REST + WebSocket temps réel), frontend Next.js séparé,
Postgres mutualisé sur Caesura (homelab Raspberry Pi 5). Structure du dépôt, décisions déjà
prises et ce qui reste à construire : voir [docs/architecture.md](./docs/architecture.md).

---

## Développement local

```bash
cd api && python -m venv venv && source venv/bin/activate && pip install -r requirements.txt
cd web && npm install
```

Détail des deux setups, variables d'environnement requises : voir
[docs/developpement.md](./docs/developpement.md).

---

## Variables d'environnement

Liste complète avec description : voir [docs/environnement.md](./docs/environnement.md).

---

## Temps réel

Diffusion prévue de l'état du plateau via WebSocket (Django Channels). État d'avancement : voir
[docs/temps-reel.md](./docs/temps-reel.md).

---

## Déploiement

Cible : Docker sur Caesura. Pas encore configuré. Voir
[docs/deploiement.md](./docs/deploiement.md).

---

## Stack

| Couche | Technologie |
|---|---|
| Backend | Django 6.1 · Django REST Framework · Django Channels (Daphne/ASGI) |
| Base de données | PostgreSQL (mutualisée, hébergée sur Caesura) |
| Frontend | Next.js 16 (App Router) · React 19 · TypeScript · Sass |
| Infra cible | Docker · Caesura (homelab Raspberry Pi 5) |
| Auth cible | JWT stateless (`djangorestframework-simplejwt`) · argon2id (voir [ADR-0003](./adr/0003-auth-jwt-argon2id.md)) |

## Documentation approfondie

- [Architecture et structure du dépôt](./docs/architecture.md)
- [Développement local](./docs/developpement.md)
- [Variables d'environnement](./docs/environnement.md)
- [Temps réel (WebSocket/Channels)](./docs/temps-reel.md)
- [Déploiement](./docs/deploiement.md)
- [Accessibilité](./docs/accessibilite.md)
- [Guide de reprise](./docs/guide-de-reprise.md)
- [Architecture Decision Records](./adr/README.md)

## Contribuer

Voir [CONTRIBUTING.md](./CONTRIBUTING.md).

## Dépannage

Voir [TROUBLESHOOTING.md](./TROUBLESHOOTING.md).

## Sécurité

Pour signaler une vulnérabilité, voir [SECURITY.md](./SECURITY.md) — pas d'issue publique.

## License

**Tous droits réservés** — voir [LICENSE](./LICENSE). Code visible publiquement à titre de
portfolio ; ce n'est pas un projet open source, aucune licence d'utilisation ou de contribution
n'est accordée.

---

Fait par **Jacques Duchamplecheval** ([alithiel31](https://github.com/Alithiel31))
