# snatch OS — portfolio

An interactive desktop-style portfolio for **0x_snatch** (builder · trader · onchain degen).

A single self-contained `index.html` — a faux operating system where every icon, folder, and
window is part of the portfolio:

- **Portfolio** folder — projects grouped into Trading Systems / Web & Apps / Bots & Automation / Libraries & Infra
- **s_block** — an animated, clickable build-ledger of the projects (by category, in order)
- **Market** — live BTC chart (Binance REST + WebSocket)
- **Beans Photos** — photo gallery with viewer + downloads
- **Internet** — a mini browser of the live sites
- **README.txt / PerpDEX / Tokenomics.txt** — text files
- **Contact** — sends real email (via FormSubmit)

## Tech

Pure static HTML. React/ReactDOM/Babel are loaded at runtime from the unpkg CDN; everything else
(markup, logic, images, fonts config) is inlined into the single file. No build step.

## Deploy (Vercel)

This is a zero-config static site:

1. Push this repo to GitHub.
2. In Vercel → **New Project** → import the repo.
3. Framework preset: **Other** (no build command, no output dir — it serves `index.html`).
4. Deploy.

That's it — Vercel serves `index.html` at the root.

## Notes

- The site fetches React/Babel from `unpkg.com` and market data from `api.binance.com` at runtime,
  so it needs internet access in the visitor's browser (works on any normal connection).
- The Contact form posts to FormSubmit; the owner inbox must confirm the one-time activation email
  before messages are delivered.
