# Claros

A browser app for examining where your beliefs come from and training how you argue. Claros runs entirely in the browser: it scores your answers, shows the result on a dashboard and keeps your history in `localStorage`.

[Bahasa Indonesia](README.id.md)

## Modules

| Route | Module | Purpose |
| --- | --- | --- |
| `/` | Dashboard | Overview, including a short note on where the name Claros comes from |
| `/audit` | Belief Audit | Record a belief and audit it |
| `/gym` | Critical Gym | Steel-manning challenges and a scenario simulator for cognitive biases |
| `/map` | Origin Map | Plots the source of each belief against your confidence in it |
| `/score` | Clarity Score | Tracks how your belief map shifts over time |

The analysis in `src/services/aiService.js` is a local scoring routine written to match a future `POST /api/analyze` response. Nothing is sent to a server.

## Tech stack

React, Vite, React Router, Recharts, Tailwind CSS. Deployed on Vercel (`vercel.json`).

## Getting started

```bash
npm install
npm run dev        # development server
npm run build      # production build into dist/
npm run lint
```

## Project structure

```
src/pages        one file per module
src/components   shared UI
src/context      app state
src/services     scoring (aiService.js) and storage (dbService.js)
prototype/       the earlier static HTML version of the four modules
```

`prototype/` comes from the former Verity repository, merged here with its history.
