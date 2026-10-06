# Campus Inventory Frontend

React and Vite frontend for the LavaLust Product Management API. The browser
communicates with the API over HTTP; database credentials belong only in the
backend environment and must never be added here.

## Requirements

- Node.js 20.19+ or 22.12+
- The LavaLust API running locally or deployed

## Local development

From this directory, copy `.env.example` to `.env.local` and set
`VITE_API_BASE_URL` to the API origin (without a trailing slash). The example
uses `http://127.0.0.1:3000` for the local LavaLust development server.

```powershell
npm ci
npm run dev
```

Open the URL printed by Vite. Sign in with a user already created in the API
database. For cross-origin local development, configure the backend
`CORS_ALLOWED_ORIGINS` to match Vite's origin exactly.

## Production build

```powershell
npm ci
npm run build
```

Vite writes the static production site to `dist/`. Configure
`VITE_API_BASE_URL` in the static host's build environment to the deployed
LavaLust API URL, and configure the API's `CORS_ALLOWED_ORIGINS` to the exact
HTTPS origin serving this frontend.

## Render

The included `render.yaml` defines this repository as a Render Static Site.
Create the site from the Blueprint, set `VITE_API_BASE_URL` to the deployed API
origin, then add the resulting frontend HTTPS origin to the backend's
`CORS_ALLOWED_ORIGINS`.
