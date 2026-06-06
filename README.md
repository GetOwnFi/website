# OwnFi — Marketing Website

> **Keep custody. Access opportunity.**

The public marketing site for **OwnFi**, a non-custodial software interface for
discovering, comparing and executing self-directed interactions with third-party
decentralised finance (DeFi) protocols. Users retain custody, approve their own
transactions, and make their own decisions.

This repository contains **only the static marketing site**. It has no backend, no
app, no wallet connection and no API calls. The OwnFi product app is built
separately and is **not live yet**.

---

## What's here

| Page | File | Purpose |
| --- | --- | --- |
| Home | `index.html` | Hero, value props, product preview, updates, waitlist, disclaimer |
| About | `about.html` | What OwnFi is (and is not), principles, status |
| Privacy Policy | `privacy.html` | Informational-only privacy stub |
| Terms & Risk | `terms.html` | Terms of use and DeFi risk disclosure |

```
.
├── index.html            # Home
├── about.html            # About
├── privacy.html          # Privacy Policy
├── terms.html            # Terms & Risk disclosure
├── favicon.svg           # Site icon
├── robots.txt            # Crawl rules
├── sitemap.xml           # Sitemap
├── .nojekyll             # Tell GitHub Pages to skip Jekyll processing
└── assets/
    ├── css/styles.css    # Single stylesheet (design system)
    ├── js/main.js        # Minimal JS (mobile menu + footer year)
    └── img/
        ├── logo.svg       # Brand mark
        └── og.svg         # Open Graph / social share image
```

No build step, no dependencies, no bundler. Just static files.

---

## Run locally

Because everything is static, you can open `index.html` directly in a browser.
For correct relative paths and a closer match to production, serve it over HTTP:

```bash
# Python 3 (no install needed on most systems)
python3 -m http.server 8000

# or Node
npx serve .
```

Then visit <http://localhost:8000>.

---

## Deploy to GitHub Pages

This site is designed to be served from the **repository root** of the
[`GetOwnFi`](https://github.com/GetOwnFi) org.

1. Push this repository to GitHub (default branch `main`).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set:
   - **Source:** *Deploy from a branch*
   - **Branch:** `main`
   - **Folder:** `/ (root)`
4. Save. Your site publishes at `https://<org>.github.io/<repo>/` within a minute or two.

> Prefer a `/docs` folder instead? Move all files into a `docs/` directory and pick
> **Folder: `/docs`** in step 3. Everything else stays the same.

The included `.nojekyll` file ensures GitHub Pages serves files as-is (important so
the `assets/` folder is published unchanged).

### Custom domain (optional)

To serve from `getownfi.com`:

1. Add a `CNAME` file at the repo root containing a single line: `getownfi.com`.
2. In **Settings → Pages → Custom domain**, enter `getownfi.com` and save.
3. At your DNS provider, point the domain at GitHub Pages (an `ALIAS`/`ANAME` or
   `A` records for the apex, plus a `CNAME` for `www`).

The canonical/OG URLs in the HTML already assume `https://getownfi.com/`. Update
them if you deploy under a different domain.

---

## Editing common things

- **Contact email** — the site uses `mailto:hello@getownfi.com` links (in the
  footer, the early-access call-to-action, and the About / Privacy / Terms
  pages). `mailto:` opens the visitor's own email client, so no mail server is
  required. Search for `hello@getownfi.com` to change the address.
- **Early access** — there is intentionally **no signup form** (the site has no
  backend or mail server to send email from). The "Be first to try OwnFi"
  section is a `mailto:` call-to-action instead. If you later add a hosted form
  service (e.g. Formspree), you can swap the button for a form.
- **Colors / branding** — all design tokens live at the top of
  `assets/css/styles.css` under `:root` (neutral slate palette + one teal accent).
- **Social share image** — `assets/img/og.svg`. Some platforms prefer a raster
  PNG/JPG at 1200×630; if needed, export the SVG to PNG and update the
  `og:image` / `twitter:image` tags.

---

## Principles reflected in the copy

- **Self-custody first** — assets never leave the user's wallet without their signature.
- **Transparency** — protocol, chain, fees, yield source and risk indicators shown before acting.
- **Plain English** — no hype; estimated yields are variable and never guaranteed.

The site intentionally avoids language like *bank account*, *guaranteed*, *risk-free*,
*protected savings*, *we manage your money*, *fixed income*, or *personalised advice*.

---

## License

Copyright © OwnFi. All rights reserved unless a license file says otherwise.
