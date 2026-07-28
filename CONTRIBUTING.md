# Contributing — systems-knowledge-base

## Branches

| Branch | Use |
| --- | --- |
| `main` | Protected — PR required; **`pytest`** must pass |
| `feature/<id>-<short-name>` | Default work — `<id>` when Boards-tracked; omit for vault-only amends |
| `bug/<id>-<short-name>` | Fixes (optional) |
| `chore/<id>-<short-name>` | Tooling / meta (optional) |

No long-lived `dev` / `uat` / `prod`. Work-item linking optional for vaults.

## Pull requests

1. Branch from latest `main` (or your team’s agreed integration branch).
2. Keep the PR focused; vault amends follow [[changing-this-bible]] / ingestion workflows.
3. Ensure CI job **`pytest`** (vault health) is green.
4. Merge only via PR into `main`.
5. Gaps beat invented SoR; do not paste engineering or change-method doctrine here.

House setup and source-control detail live in sibling **agent-harness**:

- `../agent-harness/docs/setup.md`
- `../agent-harness/docs/source-control.md`

## Local checks

```bash
python -m pip install -e ".[dev]"
pytest tests/ -v
```
