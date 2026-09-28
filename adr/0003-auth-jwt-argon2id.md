# ADR-0003 — Authentification JWT stateless + argon2id

**Statut** : accepté (2026-09)

## Contexte

L'API REST (DRF) et le frontend Next.js sont déployés séparément (voir ADR-0002), le frontend consommant l'API à distance plutôt que servi par Django lui-même. Une authentification par session/cookie classique Django complexifie ce découplage (CORS + cookies cross-origin).

## Décision

Authentification par JWT stateless (`djangorestframework-simplejwt`) plutôt que sessions Django, avec hachage des mots de passe en argon2id (`Argon2PasswordHasher`, natif Django). CSRF désactivé sur les endpoints API (pas de cookies de session côté API — protection CSRF Django conservée uniquement si l'admin Django reste exposé).

## Conséquences

- Découplage propre entre API et frontend, cohérent avec le déploiement séparé.
- Nécessite de gérer le refresh token côté frontend (endpoint `/api/auth/token/refresh/`).
- CORS doit être restreint explicitement au domaine du frontend (`django-cors-headers`, pas de wildcard) — sans quoi le JWT en header devient une surface d'attaque plus large qu'un cookie `HttpOnly`.
