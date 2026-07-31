# Contributing

Thank you for your interest in contributing! This document explains the process.

## Table of contents

- [Development setup](#development-setup)
- [Making changes](#making-changes)
- [Commit convention](#commit-convention)
- [Adding a changeset](#adding-a-changeset)
- [Pull request guidelines](#pull-request-guidelines)
- [Release process](#release-process)

---

## Development setup

```bash
git clone https://github.com/hoang-transperfect/tri-2.git
cd tri-2
pnpm install
pnpm exec playwright install chromium
```

Verify everything works before you start:

```bash
pnpm lint && pnpm build && pnpm test
```

Start Storybook to develop components in isolation:

```bash
pnpm storybook
```

---

## Making changes

1. Fork the repository and create a branch:
   ```bash
   git checkout -b feat/my-component
   ```
2. Make your changes. See [Adding a component](./README.md#adding-a-component) for the file structure.
3. Ensure all checks pass locally:
   ```bash
   pnpm lint && pnpm build && pnpm test
   ```
4. Add a changeset (see below).
5. Open a pull request against `main`.

---

## Commit convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(button): add loading state
fix(button): correct focus ring on keyboard navigation
docs: update Button usage example
chore: upgrade vitest to 4.2
```

| Prefix | When |
| --- | --- |
| `feat` | New component or backwards-compatible capability |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `chore` | Tooling, deps, CI — nothing user-facing |
| `BREAKING CHANGE` | Include in footer for any breaking API change |

---

## Adding a changeset

Every PR that changes something user-visible (a component, a prop, a CSS variable, a breaking change) **must** include a changeset. Run:

```bash
pnpm changeset
```

The interactive prompt asks:
1. **Bump type** — `patch` (bug fix) / `minor` (new capability) / `major` (breaking)
2. **Summary** — one sentence that goes straight into `CHANGELOG.md`

Commit the generated `.changeset/<hash>.md` file with your PR. PRs without a required changeset will be flagged in review.

Internal-only changes (docs, tests, CI, tooling) do not need a changeset.

---

## Pull request guidelines

- Keep PRs focused — one concern per PR.
- Include a story for any new component or new interactive state.
- Tests are provided by the Storybook stories themselves (`@storybook/addon-vitest`); the story **is** the test.
- Accessibility: run `pnpm storybook`, open the A11y panel, and resolve any violations before submitting.

---

## Release process

Releases are fully automated:

1. A PR with a changeset is merged to `main`.
2. The Release workflow opens a **"Version Packages"** PR that bumps `package.json` and updates `CHANGELOG.md`.
3. A maintainer reviews and merges the Version PR.
4. The Release workflow publishes the new version to npm and creates a GitHub Release.

Maintainers do not manually edit version numbers or push tags.
