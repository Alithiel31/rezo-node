# Rezo Node — API (Django)

Backend Django + Django REST Framework + Channels. Sert l'API REST (CRUD parties/portails/liens) et le flux temps réel (état du plateau par tick, via WebSocket).

## Setup local

```bash
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate sous Windows
pip install -r requirements.txt
```

Copier `.env.example` en `.env` et renseigner :
- `DJANGO_SECRET_KEY`, `DJANGO_DEBUG`
- `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT` — pointe sur le PostgreSQL mutualisé de Caesura en dev local (pas de conteneur Postgres dédié).

```bash
python manage.py migrate
python manage.py runserver
```

## Apps

- `games` — Faction, Carte, Partie, PartieFaction, ActionHistorique.
- `portals` — PortailDefinition, Portail.
- `links` — Lien, SiegeOrdre.

Voir `../Claude outputs/rezo-node-mcd-mld.md` (schéma de données) et `../Claude outputs/rezo-node-suivi-code-organisation.md` (répartition détaillée, conventions) pour le détail.

## Statut

Scaffold uniquement — modèles pas encore écrits. Prochaine étape : traduire le MCD/MLD en `models.py` par app (voir suivi-code-organisation.md pour les points ouverts à trancher avant).
