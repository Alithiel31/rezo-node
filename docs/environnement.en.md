# Environment variables

🇫🇷 [Version française](./environnement.md)

[Back to README](../README.en.md)

## Backend (`api/.env`, from `api/.env.example`)

| Variable | Description | Default (`.env.example`) |
|---|---|---|
| `DB_NAME` | PostgreSQL database name | `rezo_node` |
| `DB_USER` | PostgreSQL user | `rezo_node` |
| `DB_PASSWORD` | PostgreSQL password | `change-me` |
| `DB_HOST` | PostgreSQL host (Caesura's shared instance in dev) | `your-db-host` |
| `DB_PORT` | PostgreSQL port | `5432` |
| `DJANGO_SECRET_KEY` | Django secret key (session signing, tokens) | `change-me` |
| `DJANGO_DEBUG` | Enables Django debug mode (`true`/`false`) | `true` |

## Frontend (`web/`)

No environment variables yet — default `create-next-app` scaffold.

## To be filled in over time

- JWT variables (`djangorestframework-simplejwt`) once auth is implemented (see
  [ADR-0003](../adr/0003-auth-jwt-argon2id.md)).
- Redis/Celery variables if those dependencies ever get wired up (see
  [docs/architecture.en.md](./architecture.en.md)).
