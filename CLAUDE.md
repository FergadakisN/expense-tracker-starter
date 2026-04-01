# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install       # install dependencies
npm run dev       # start dev server at http://localhost:5173
npm run build     # production build
npm run lint      # run ESLint
npm run preview   # preview production build
```

## Architecture

This is a single-page React app (Vite + React 19). All application logic lives in one file:

- `src/App.jsx` — the entire app: state management, filtering logic, form handling, and rendering
- `src/App.css` — all styles (flat, no CSS modules or Tailwind)
- `src/main.jsx` — React root mount

There is no routing, no backend, no state management library, and no test suite. Transaction data is held in component state only (not persisted).

## Known Issues (Intentional for Course)

- `amount` is stored as a string in state, so `reduce` concatenates instead of summing — totals are wrong
- "Freelance Work" is incorrectly typed as `"expense"` instead of `"income"` in the seed data
- The UI has minimal styling and no delete functionality (`.delete-btn` CSS exists but no button is rendered)
