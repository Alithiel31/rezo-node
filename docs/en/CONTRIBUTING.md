# Contributing

🇫🇷 [Version française](../../CONTRIBUTING.md)

Rezo Node is a personal portfolio project, published under an **"All rights reserved"** license
(see [LICENSE](../../LICENSE)) — unlike an open source project, no external contribution (pull
request, fork) is solicited or guaranteed to be merged. This document mostly describes how the
maintainer (Jacques Duchamplecheval) works on the project day to day, for transparency.

## Development environment

```bash
git clone git@github.com:Alithiel31/rezo-node.git
cd rezo-node

cd api
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# edit .env (see docs/environnement.en.md)

cd ../web
npm install
```

Full details: see [docs/developpement.en.md](../developpement.en.md).

## Architecture decisions

Any significant architecture decision (stack choice, structuring pattern) is recorded as a new
ADR under [`adr/`](../../adr/), Nygard-style (Status / Context / Decision / Consequences) — see
[adr/README.md](../../adr/README.md) for the template and existing list.

## Reproducing checks locally

_To be filled in over time_ — no CI or test suite exists yet (see
[docs/developpement.en.md](../developpement.en.md)).

## Opening a Pull Request

1. Create a branch off `main`.
2. Commit with a clear message, ideally `type: description` (`feat:`, `fix:`, `docs:`, `chore:`...).
3. Update [`CHANGELOG.md`](../../CHANGELOG.md) under `[Unreleased]` if the change is notable.
4. Open the PR against `main`.

## Reporting an issue

Open an issue from the repo's Issues tab. Check [TROUBLESHOOTING.en.md](../../TROUBLESHOOTING.en.md) first.

## Secrets

Never commit `api/.env` or any real secret (Django key, database credentials). See
[docs/en/SECURITY.md](./SECURITY.md).
