FRM Part I Quiz (PWA)
=====================
Installable/offline FRM Part I quiz: 146 original questions on Book 1 (Foundations of Risk Management) and Book 2 Chapters 12–17 (Quantitative Analysis).
The quiz itself is unchanged; only PWA tags + a service-worker registration were added.

A PWA must be served over HTTPS (or http://localhost) to install. Opening index.html
as a file:// works as a normal page but is NOT installable and won't cache offline.

Run locally:   python3 -m http.server 8000   then open http://localhost:8000/
Host anywhere static over HTTPS (GitHub Pages, Netlify, Cloudflare Pages...): upload the folder as-is.

Install on Android (Chrome): open the HTTPS URL > menu (⋮) > "Install app" / "Add to Home screen".
Install on iPhone/iPad (Safari): open the HTTPS URL > Share > "Add to Home Screen" > Add.
After first load it works offline. If you edit any file, bump CACHE_VERSION in sw.js.
Progress (best score) is kept in the browser's localStorage per device/origin, same keys as the original.
