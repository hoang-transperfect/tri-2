# Changesets

This folder is managed by [@changesets/cli](https://github.com/changesets/changesets).

## Workflow

1. **During development** — when your PR contains a user-visible change, run:
   ```bash
   pnpm changeset
   ```
   Answer the prompts (bump type + summary). Commit the generated `.changeset/<random>.md` file with your PR.

2. **On merge to `main`** — the Release workflow detects the changeset file and opens a "Version Packages" PR that bumps `package.json` and updates `CHANGELOG.md` automatically.

3. **On merge of the Version PR** — the Release workflow publishes the new version to npm automatically.

## Bump types

| Type | When to use | Example |
|---|---|---|
| `patch` | Bug fix, docs, internal refactor | `0.0.1 → 0.0.2` |
| `minor` | New component or prop, backwards-compatible | `0.0.1 → 0.1.0` |
| `major` | Breaking API change | `0.0.1 → 1.0.0` |
