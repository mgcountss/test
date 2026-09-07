# mgcounts.com — AJ Counts (OMIS portfolio)

A fast, mobile-first, single-page personal site positioning **AJ Counts** for
**OMIS — Operations Management & Information Systems** work. No build step, no
frameworks, no dependencies: just HTML, CSS, and a little vanilla JavaScript.

**Live (GitHub Pages):** https://mgcountss.github.io/test/

## Files

| File | What it is |
|------|------------|
| `index.html` | All page content and structure |
| `styles.css` | Design system, light/dark themes, responsive layout |
| `script.js` | Theme toggle, mobile nav, scroll-reveal, active-nav, footer year |
| `favicon.svg` | "AJ" monogram tab icon |
| `.github/workflows/deploy-pages.yml` | Enables + deploys the site to GitHub Pages |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Run it locally

It's static — just open `index.html` in a browser. For a local server:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Personalize it

The content is real — your projects, metrics, skills, and contact links from
mgcounts.com. The **only** placeholder left (marked `<!-- EDIT -->` in
`index.html`) is:

- **LinkedIn URL** — in the Contact section, replace
  `https://www.linkedin.com/in/your-profile` with your real profile (or delete
  that button if you don't want it).

Everything else — the email (`straightfrommgyt@gmail.com`), GitHub, YouTube, and
all project links — points at your real accounts and live sites.

## Deploy

Deployment is automated by **`.github/workflows/deploy-pages.yml`**. On every push
to the default branch it builds the static site and publishes it to GitHub Pages
(the workflow enables Pages automatically the first time). The site is served at:

> https://mgcountss.github.io/test/

### Using the custom domain (mgcounts.com) later

This deploy intentionally does **not** claim `mgcounts.com`, so it won't disturb
your existing site there. When you're ready to move the domain to this repo:

1. Repo **Settings → Pages → Custom domain** → enter `mgcounts.com` and save.
2. Point DNS at GitHub Pages (apex `A`/`AAAA` records, or a `CNAME` for `www`) per
   GitHub's custom-domain docs. GitHub will add/commit a `CNAME` file for you.

## Notes

- **Accessible:** semantic landmarks, skip link, visible focus, ARIA on the nav/toggle,
  respects `prefers-reduced-motion`, and a `<noscript>` fallback so content never hides.
- **Themes:** follows the visitor's system light/dark by default; the toggle remembers
  their choice in `localStorage`.
- **Performance:** one small CSS file, one small JS file, an inline SVG favicon, and
  self-contained icons — no image payloads, no libraries.
