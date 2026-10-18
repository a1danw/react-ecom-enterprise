# Ecomm React

## Tech Stack

**Core**

- [React 19](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/docs/)
- [Vite](https://vite.dev/guide/)

**Styling & UI**

- [Tailwind CSS v4](https://tailwindcss.com/docs/styling-with-utility-classes)
- [MUI (Material UI)](https://mui.com/material-ui/getting-started/) + [Emotion](https://emotion.sh/docs/introduction)
- [Base UI](https://base-ui.com/react/overview/quick-start)
- [lucide-react](https://lucide.dev/guide/packages/lucide-react)

**Routing**

- [React Router v7](https://reactrouter.com/start/framework/routing)

## Project Structure

```
src/
├── assets/                 # Static assets (images, icons)
├── components/             # Shared/global components
│   ├── Header.tsx          # Application header
│   └── Footer.tsx          # Application footer
│
├── features/               # Feature based modules (domain driven)
│   └── product/
│       └── components/     # Product specific components
│
├── redux/                  # Global state store (scaffolded, not yet wired up)
├── routes/                 # Route definitions
├── App.tsx                 # Root app component
└── main.tsx                # Application entry point, router setup
```

## Architecture

### Feature-Based Structure

- **Domain driven organization** - Code organized by business features (e.g. `product`).
- **Self contained features** - Each feature includes its own components, and will grow to include hooks, pages, and tests as it expands.
- **Vertical slices** - Same idea as vertical slice architecture on the backend: each feature owns everything it needs top to bottom, rather than being split across horizontal technical layers.

### Component Strategy

- **Global components** (`src/components/`) - Reusable across features (Header, Footer).
- **Feature components** (`src/features/*/components/`) - Feature specific, not shared.
- **Component sources** - MUI for pre-built components, Base UI for headless/unstyled primitives when full styling control is needed.

### Styling Approach

- **Tailwind CSS** - Utility first CSS (installed; not yet wired into the build/entry CSS).
- **MUI + Emotion** - Component library styling for pre-built UI pieces.

### State Management

- A `redux/` folder is reserved for global state, but Redux Toolkit is not yet a dependency and `store.ts` is currently empty. Add `@reduxjs/toolkit` / `react-redux` when shared state is needed.

## Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Lint code
npm run lint
```

## Code Conventions

- **Default exports** for components.
- **TypeScript strict mode** enabled.
- **Path aliases** - `@/` maps to `src/`.
- **Feature based development** - Code organized by business domain rather than technical layers.
