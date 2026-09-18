# Baby Name Generator

A small Nuxt 3 app that suggests baby names filtered by gender, popularity, and name length. Pick the three options, get the matching names, and drop the ones you do not like.

> Learning project from 2022. It is finished in the sense that it works, but it is not maintained.

## What it does

- Filters a local name list by gender, popularity, and length.
- Renders the matches as cards.
- Lets a name be removed from the current result set.

## Tech stack

- Nuxt 3 and Vue 3
- TypeScript
- Sass
- ESLint, Prettier, and Stylelint with a Husky pre-commit hook

## Getting started

### Requirements

- Node.js
- yarn or npm

### Installation

```bash
yarn install
```

### Development

```bash
yarn dev
```

The development server runs at `http://localhost:3000`.

## Useful commands

```bash
yarn build         # Build for production
yarn generate      # Build a static output
yarn preview       # Preview the production build
yarn lint:script   # Lint the scripts
yarn lint:style    # Lint the styles
```

## How it works

The name data and the `Gender`, `Popularity`, and `Length` enums live in `data`. Selection state is a single reactive object, and the filtered result is recomputed whenever one of the three options changes. There is no backend and no persistence — a reload resets everything.

## Project structure

```text
components/
├── Option.vue     # One filter group
└── Card/Name.vue  # A single name card

data/              # Name list and option enums
app.vue            # Filter state and result computation
```

## Status

Unmaintained. The dependency versions are from 2022 and are not kept current.

## License

No open-source license has been declared yet. Until a license is added, reuse and redistribution are not granted by default.

Made with love by [Laflamme](https://github.com/lafllamme).
