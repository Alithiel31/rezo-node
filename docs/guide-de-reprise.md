# Guide de reprise

🇬🇧 [English version](./guide-de-reprise.en.md)

[Retour au README](../README.md)

Rezo Node a un seul mainteneur réel (**Jacques Duchamplecheval**, alias GitHub `Alithiel31`). Ce
document existe pour qu'une autre personne — ou Jacques lui-même après une longue coupure —
puisse reprendre le projet. Il est volontairement court pour l'instant : le projet est un
scaffold, rien n'est encore déployé.

## 1. Comprendre le projet — ordre de lecture recommandé

1. [README.md](../README.md) — vue d'ensemble, objectifs, statut
2. [adr/](../adr/) — décisions d'architecture déjà prises
3. [docs/architecture.md](./architecture.md) — structure du dépôt, état actuel
4. [docs/developpement.md](./developpement.md) — lancer le projet en local
5. [docs/environnement.md](./environnement.md) — variables de configuration

## 2. Ce qui tourne, et où

| Composant | Où | Comment y accéder |
|---|---|---|
| Code source | [`github.com/Alithiel31/rezo-node`](https://github.com/Alithiel31/rezo-node) | Accès GitHub |
| Base de données de développement | Postgres mutualisé sur **Caesura** (homelab Raspberry Pi 5 du mainteneur) | Accès réseau au Caesura — **à compléter par le mainteneur** |
| Application en production | Aucune pour l'instant — projet non déployé | — |

## 3. Secrets et accès nécessaires pour agir

Aucun secret réel n'est stocké dans ce dépôt (voir `.gitignore` et
[SECURITY.md](../SECURITY.md)). Pour reprendre le projet en pratique :

- **Accès administrateur au dépôt GitHub** [`Alithiel31/rezo-node`](https://github.com/Alithiel31/rezo-node)
- **Accès au Postgres mutualisé de Caesura** (identifiants réels correspondant à `DB_USER`/`DB_PASSWORD`/`DB_HOST`, voir [docs/environnement.md](./environnement.md))
- **Accès au Project Claude "Rezo-Node"** — la conception détaillée (game design, use cases, user stories, MCD/MLD) vit hors du dépôt (voir la note du [README](../README.md), section Structure) — **à compléter par le mainteneur** (où ce workspace est-il hébergé, comment y accéder)

## 4. Risques connus à garder en tête

- **Mainteneur unique** — ce document réduit le risque mais ne le supprime pas.
- **Conception hors dépôt** — la documentation de conception détaillée n'est pas versionnée avec
  le code ; sans accès au Project Claude associé, la reprise se limite au code et aux ADR déjà
  écrits.
- **Rien de déployé** — pas encore de risque d'infrastructure en production, mais aussi pas de
  procédure de remise en marche à documenter tant que ça n'existe pas.

## À compléter par le mainteneur

- [ ] Où et comment accéder au Project Claude "Rezo-Node" (conception, MCD/MLD)
- [ ] Identifiants d'accès à Caesura (Postgres mutualisé, et plus tard Docker/déploiement)
- [ ] Personne(s) de confiance à contacter en cas d'indisponibilité prolongée du mainteneur
