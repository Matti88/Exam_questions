# Exam_questions

a repo with a quiz app in PWA

FRM Part I Quiz (PWA)
=====================
Installable/offline quiz app with 145 original questions covering Book 1 (Foundations of Risk Management) and Book 2 Chapters 12-17 (Quantitative Analysis).
PWA tags and a service-worker registration are included.

Live site, once GitHub Pages is on: https://matti88.github.io/Exam_questions/

A PWA must be served over HTTPS (or http://localhost) to install. Opening index.html
as a file:// works as a normal page but is NOT installable and won't cache offline.

Run locally:   python3 -m http.server 8000   then open http://localhost:8000/
Host anywhere static over HTTPS (GitHub Pages, Netlify, Cloudflare Pages...): upload the folder as-is.

Install on Android (Chrome): open the HTTPS URL > menu (⋮) > "Install app" / "Add to Home screen".
Install on iPhone/iPad (Safari): open the HTTPS URL > Share > "Add to Home Screen" > Add.
After first load it works offline. If you edit any file, bump CACHE_VERSION in sw.js.
Progress (best score) is kept in the browser's localStorage per device/origin, same keys as the original.

GitHub Pages
------------
`.github/workflows/pages.yml` deploys this repo root on every push to `main`
(`actions/configure-pages` with `enablement: true`, then `upload-pages-artifact` and `deploy-pages`).

`enablement: true` cannot create the Pages site with the default `GITHUB_TOKEN` (that call needs a separate token with administration rights). Enable it once by hand:

**Settings → Pages → Build and deployment → Source: GitHub Actions**

After that, pushes to `main` publish the site. Paths in the manifest and service worker are relative, so the app is scoped to `/Exam_questions/`. `.nojekyll` is in the root so Pages serves the files as-is.
