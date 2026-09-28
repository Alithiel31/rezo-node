# Variables d'environnement

🇬🇧 [English version](./environnement.en.md)

[Retour au README](../README.md)

## Backend (`api/.env`, depuis `api/.env.example`)

| Variable | Description | Défaut (`.env.example`) |
|---|---|---|
| `DB_NAME` | Nom de la base PostgreSQL | `rezo_node` |
| `DB_USER` | Utilisateur PostgreSQL | `rezo_node` |
| `DB_PASSWORD` | Mot de passe PostgreSQL | `change-me` |
| `DB_HOST` | Hôte PostgreSQL (Postgres mutualisé de Caesura en dev) | `your-db-host` |
| `DB_PORT` | Port PostgreSQL | `5432` |
| `DJANGO_SECRET_KEY` | Clé secrète Django (signature de session, tokens) | `change-me` |
| `DJANGO_DEBUG` | Active le mode debug Django (`true`/`false`) | `true` |

## Frontend (`web/`)

Aucune variable d'environnement pour l'instant — scaffold `create-next-app` par défaut.

## À compléter au fur et à mesure

- Variables JWT (`djangorestframework-simplejwt`) une fois l'auth implémentée (voir
  [ADR-0003](../adr/0003-auth-jwt-argon2id.md)).
- Variables Redis/Celery si ces dépendances sont un jour câblées (voir
  [docs/architecture.md](./architecture.md)).
