# Architecture

🇬🇧 [English version](./architecture.en.md)

[Retour au README](../README.md)

## Structure du dépôt

```
rezo-node/
├── adr/         Architecture Decision Records
├── api/         Backend Django + DRF + Channels
│   └── config/  Projet Django (settings, urls, asgi/wsgi)
│   └── games/    app — Faction, Carte, Partie, PartieFaction, ActionHistorique
│   └── links/    app — Lien, SiegeOrdre
│   └── portals/  app — PortailDefinition, Portail
└── web/         Frontend Next.js (App Router, TypeScript, Sass)
```

Monorepo sans outillage dédié (pas de Turborepo/Nx) — voir
[ADR-0002](../adr/0002-monorepo-sans-tooling.md).

## Décisions déjà prises

Voir [adr/](../adr/) pour le détail complet (contexte, conséquences) :

- [ADR-0001](../adr/0001-backend-django-drf-channels.md) — backend Django + DRF + Channels
  (WebSocket temps réel via Daphne/ASGI).
- [ADR-0002](../adr/0002-monorepo-sans-tooling.md) — monorepo `api/` + `web/` sans tooling dédié.
- [ADR-0003](../adr/0003-auth-jwt-argon2id.md) — authentification JWT stateless + argon2id.

## État actuel

- `api/config/urls.py` n'enregistre que `admin/` — aucune route métier.
- Les trois apps Django (`games`, `links`, `portals`) sont installées mais leurs `models.py` et
  `views.py` sont encore les stubs par défaut.
- `channels_redis`, `redis` et `celery` sont dans `requirements.txt` mais aucun `CHANNEL_LAYERS`
  ni config Celery n'existe dans `settings.py` — installés par anticipation, pas encore câblés.
- `web/` est un scaffold `create-next-app` par défaut, sans page spécifique au jeu.

## À compléter au fur et à mesure

- Schéma du modèle de données (MCD/MLD) une fois traduit en `models.py`.
- Diagramme du flux WebSocket une fois les consumers écrits (voir
  [docs/temps-reel.md](./temps-reel.md)).
- Diagramme de déploiement une fois l'infra Caesura configurée (voir
  [docs/deploiement.md](./deploiement.md)).
