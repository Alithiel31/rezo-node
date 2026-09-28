# Développement local

🇬🇧 [English version](./developpement.en.md)

[Retour au README](../README.md)

## Backend (`api/`)

```bash
cd api
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate sous Windows
pip install -r requirements.txt
cp .env.example .env
# éditer .env — voir docs/environnement.md
python manage.py migrate
python manage.py runserver
```

`DB_HOST` pointe par défaut sur le PostgreSQL mutualisé de Caesura — pas de conteneur Postgres
local dans ce dépôt pour l'instant.

## Frontend (`web/`)

```bash
cd web
npm install
npm run dev   # http://localhost:3000
```

Scaffold `create-next-app` par défaut, aucune page spécifique au jeu pour l'instant.

## Tests et CI

Aucune suite de tests ni pipeline CI n'existe encore — seuls les stubs `tests.py` vides générés
par Django sont présents dans chaque app.

## À compléter au fur et à mesure

- Commandes de lint/format une fois les outils choisis.
- Reproduction de la CI en local, une fois qu'un pipeline existe.
