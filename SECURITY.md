# Sécurité

🇬🇧 [English version](./docs/en/SECURITY.md)

## Signaler une vulnérabilité

Merci de ne **pas** ouvrir d'issue publique pour signaler une faille de sécurité — une issue
GitHub classique l'expose à tout le monde avant qu'un correctif n'existe.

Signaler via **[l'onglet Security du dépôt](https://github.com/Alithiel31/rezo-node/security/advisories/new)**
(GitHub Security Advisories) — le rapport reste privé entre toi et le mainteneur.

### Ce qu'on peut promettre

- Le projet est maintenu par une seule personne, sur son temps libre : pas de SLA formel.
- Le projet est actuellement un scaffold sans fonctionnalité exposée — le périmètre ci-dessous
  évoluera à mesure que le code métier existe.

## Périmètre

Dans le périmètre :

- Le backend Django (`api/`) et ses dépendances directes.
- Le frontend Next.js (`web/`) et ses dépendances directes.

Hors périmètre :

- Le Postgres mutualisé de Caesura (infrastructure partagée, hors de ce dépôt).
- Une faille nécessitant un accès déjà privilégié à l'infrastructure Caesura.

## Ce qui est déjà en place

_À compléter au fur et à mesure_ — la seule décision de sécurité déjà prise est le choix
d'authentification (JWT stateless + argon2id, CORS restreint au domaine du frontend), documenté
dans [ADR-0003](./adr/0003-auth-jwt-argon2id.md) ; elle n'est pas encore implémentée.

## Versions supportées

Un seul déploiement prévu, pas de branches de version : seul le code sur `main` recevra des
correctifs de sécurité une fois le projet en production.
