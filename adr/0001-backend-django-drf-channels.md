# ADR-0001 — Choix du backend : Django + DRF + Channels

**Statut** : accepté (2026-09)

## Contexte

Rezo Node avait initialement été envisagé avec un backend Node/Express puis FastAPI. FastAPI avait déjà été démontré sur un autre projet (ParseAndCutV2), ce qui limitait l'intérêt portfolio d'un second projet sur la même stack. Le jeu nécessite par ailleurs un flux temps réel (diffusion de l'état du plateau à chaque tick) que ni Node/Express seul ni FastAPI ne fournissent nativement sans ajout.

## Décision

Backend en Django + Django REST Framework pour l'API REST, complété par Django Channels (avec Daphne comme serveur ASGI) pour le WebSocket temps réel.

## Conséquences

- Diversifie le portfolio (stack différente de ParseAndCutV2) et correspond à une stack plus présente dans les offres d'emploi web au Québec.
- Nécessite d'apprendre Django en même temps que d'implémenter le jeu (pas de expérience préalable avec le framework).
- Channels tourne en in-memory pour l'instant (pas de layer Redis dédié) — suffisant pour un jeu solo mono-process sur Caesura ; à revoir si le besoin change (plusieurs workers, scaling horizontal).
