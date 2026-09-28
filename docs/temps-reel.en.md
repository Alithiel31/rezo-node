# Real-time (WebSocket / Channels)

🇫🇷 [Version française](./temps-reel.md)

[Back to README](../README.en.md)

## Intent

Broadcast board state (portals, links, captures) to connected clients on every tick, via Django
Channels (WebSocket, ASGI/Daphne) rather than REST polling — see
[ADR-0001](../adr/0001-backend-django-drf-channels.md).

## Current state

- `channels` and `daphne` are installed and declared in `INSTALLED_APPS`; `ASGI_APPLICATION`
  points to `config.asgi.application`.
- No consumer or WebSocket routing has been written yet.
- `channels_redis` and `redis` are in `requirements.txt`, but no `CHANNEL_LAYERS` is configured —
  the layer will be in-memory (in-process) for now, per ADR-0001 (sufficient for a single-process
  solo game; to be revisited if horizontal scaling becomes necessary).

## To be filled in over time

- Message format (protocol, broadcast game events).
- Consumers and routing (`config/asgi.py`, per-app `routing.py`).
- Decision to switch to a Redis `CHANNEL_LAYERS` if multiple workers become necessary.
