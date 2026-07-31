# @hoang-tpt/tri-2

## 0.0.1

### Added

- `Button` component with `primary`, `size`, `backgroundColor`, `label`, and `onClick` props
- Storybook stories used as component tests via `@storybook/addon-vitest`
- Vite library build producing ESM output (`dist/index.js`) and type declarations (`dist/index.d.ts`)
- CI pipeline (lint, build, test) for GitHub Actions and Azure DevOps
- CD pipeline: automated publish to npm on merge of a Version Packages PR (via Changesets)
