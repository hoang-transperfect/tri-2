# @hoang-tpt/tri-2

[![npm version](https://img.shields.io/npm/v/@hoang-tpt/tri-2)](https://www.npmjs.com/package/@hoang-tpt/tri-2)
[![CI](https://github.com/hoang-transperfect/tri-2/actions/workflows/ci.yml/badge.svg)](https://github.com/hoang-transperfect/tri-2/actions/workflows/ci.yml)
[![license](https://img.shields.io/npm/l/@hoang-tpt/tri-2)](./LICENSE)

A React component library built with TypeScript and Vite.

---

## Requirements

| Peer dependency | Version |
| --- | --- |
| `react` | `^19.0.0` |
| `react-dom` | `^19.0.0` |

## Installation

```bash
npm install @hoang-tpt/tri-2
# or
pnpm add @hoang-tpt/tri-2
# or
yarn add @hoang-tpt/tri-2
```

Import styles once at the root of your application:

```ts
import '@hoang-tpt/tri-2/style.css';
```

---

## Usage

### Button

```tsx
import { Button } from '@hoang-tpt/tri-2';

export function App() {
  return (
    <Button
      label="Click me"
      primary
      onClick={() => console.log('clicked')}
    />
  );
}
```

#### Props

| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| `label` | `string` | — | Button text (**required**) |
| `primary` | `boolean` | `false` | Use the primary (filled) style |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | Controls padding and font size |
| `backgroundColor` | `string` | — | Overrides the background color |
| `onClick` | `() => void` | — | Click handler |

---

## Development

### Prerequisites

- [Node.js](https://nodejs.org/) 22+
- [pnpm](https://pnpm.io/) 10+ (`corepack enable`)

### Setup

```bash
git clone https://github.com/hoang-transperfect/tri-2.git
cd tri-2
pnpm install
pnpm exec playwright install chromium   # one-time browser binary download
```

### Commands

| Command | Description |
| --- | --- |
| `pnpm storybook` | Start Storybook dev server on `localhost:6006` |
| `pnpm build` | Type-check and build the library to `dist/` |
| `pnpm test` | Run component tests (headless Chromium via Playwright) |
| `pnpm lint` | Run oxlint |
| `pnpm build-storybook` | Build static Storybook |

### Adding a component

1. Create `src/components/<Name>/`:
   - `<Name>.tsx` — component + exported `Props` type
   - `<Name>.css` — scoped styles
   - `<Name>.stories.ts` — Storybook stories (used as component tests)
   - `index.ts` — re-exports `<Name>` and `<Name>Props`
2. Add `export * from './components/<Name>';` to `src/index.ts`.

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

## Code of Conduct

See [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md).

## Security

See [SECURITY.md](./SECURITY.md).

## License

[MIT](./LICENSE) © hoang.nguyen
