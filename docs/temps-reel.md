# Temps réel (WebSocket / Channels)

🇬🇧 [English version](./temps-reel.en.md)

[Retour au README](../README.md)

## Intention

Diffuser l'état du plateau (portails, liens, captures) à chaque tick vers les clients connectés,
via Django Channels (WebSocket, ASGI/Daphne) plutôt que du polling REST — voir
[ADR-0001](../adr/0001-backend-django-drf-channels.md).

## État actuel

- `channels` et `daphne` sont installés et déclarés dans `INSTALLED_APPS` ; `ASGI_APPLICATION`
  pointe vers `config.asgi.application`.
- Aucun consumer, ni routing WebSocket n'est encore écrit.
- `channels_redis` et `redis` sont dans `requirements.txt` mais aucun `CHANNEL_LAYERS` n'est
  configuré — le layer sera en mémoire (in-process) pour l'instant, per ADR-0001 (suffisant pour
  un jeu solo mono-process ; à revoir si le besoin de scaling horizontal apparaît).

## À compléter au fur et à mesure

- Format des messages échangés (protocole, événements du jeu diffusés).
- Consumers et routing (`config/asgi.py`, `routing.py` par app).
- Décision de bascule vers un `CHANNEL_LAYERS` Redis si plusieurs workers deviennent nécessaires.
