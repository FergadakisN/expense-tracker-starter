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

This is a single-page React app (Vite + React 19). There is no routing, no backend, no state management library, and no test suite. Transaction data is held in `App` state only (not persisted).

- `src/App.jsx` — root component; owns the `transactions` array and `handleAdd` callback, renders the three child components
- `src/Summary.jsx` — receives `transactions`, computes `totalIncome`, `totalExpenses`, and `balance` internally
- `src/TransactionForm.jsx` — owns its own form state; calls `onAdd(transaction)` prop on submit
- `src/TransactionList.jsx` — receives `transactions`, owns its own filter state (`filterType`, `filterCategory`)
- `src/App.css` — all styles (flat, no CSS modules or Tailwind)
- `src/main.jsx` — React root mount

## Known Issues (Intentional for Course)

- "Freelance Work" is incorrectly typed as `"expense"` instead of `"income"` in the seed data
- The UI has minimal styling and no delete functionality (`.delete-btn` CSS exists but no button is rendered)
