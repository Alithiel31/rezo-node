# Contribuer

🇬🇧 [English version](./docs/en/CONTRIBUTING.md)

Rezo Node est un projet de portfolio personnel, publié sous licence **"Tous droits réservés"**
(voir [LICENSE](./LICENSE)) — contrairement à un projet open source, aucune contribution externe
(pull request, fork) n'est sollicitée ni garantie d'être fusionnée. Ce document décrit surtout
comment le mainteneur (Jacques Duchamplecheval) travaille sur le projet au quotidien, à titre de
transparence pour qui consulte le dépôt.

## Environnement de développement

```bash
git clone git@github.com:Alithiel31/rezo-node.git
cd rezo-node

cd api
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# éditer .env (voir docs/environnement.md)

cd ../web
npm install
```

Détail complet : voir [docs/developpement.md](./docs/developpement.md).

## Décisions d'architecture

Toute décision d'architecture significative (choix de stack, pattern structurant) est consignée
dans une nouvelle ADR sous [`adr/`](./adr/), au format Nygard (Statut / Contexte / Décision /
Conséquences) — voir [adr/README.md](./adr/README.md) pour le gabarit et la liste existante.

## Reproduire les vérifications en local

_À compléter au fur et à mesure_ — aucune CI ni suite de tests n'existe encore (voir
[docs/developpement.md](./docs/developpement.md)).

## Ouvrir une Pull Request

1. Créer une branche depuis `main`.
2. Committer avec un message clair, idéalement au format `type: description` (`feat:`, `fix:`,
   `docs:`, `chore:`...).
3. Mettre à jour [`CHANGELOG.md`](./CHANGELOG.md) dans la section `[Non publié]` si le changement
   est notable.
4. Ouvrir la PR contre `main`.

## Signaler un problème

Ouvrir une issue depuis l'onglet Issues du dépôt. Vérifier d'abord
[TROUBLESHOOTING.md](./TROUBLESHOOTING.md).

## Secrets

Ne jamais committer `api/.env` ni aucun secret réel (clé Django, identifiants de base de
données). Voir [SECURITY.md](./SECURITY.md).
