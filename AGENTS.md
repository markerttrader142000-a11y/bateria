# Base44 dev environment notes

- The entire app is `index.html` — a static, self-contained page (battery calculator, pt-BR). No build step, no framework, no backend.
- State persists to `localStorage` and syncs to a free public key-value API at `https://textdb.dev/api/data/bateria-a7e2c94f81d603b5` (and a `-gate` key for the access code config). textdb.dev needs no credentials.
- Run with `docker compose -f docker-compose.base44.yml up -d` — nginx:alpine serves the repo root on port 3000, bind-mounted read-only, so file edits are picked up on the next request.
- There is no live-reload dev server; after editing `index.html`, force a preview reload (`reload_preview`).
- Verify it works by checking the page title contains "Cálculo de Bateria" at http://localhost:3000/.
