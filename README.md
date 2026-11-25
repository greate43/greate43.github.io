# greate43.github.io

Root of the GitHub Pages domain, and the origin of **greatdevstudios.com**.

- `.well-known/assetlinks.json` — Android App Links for Nexora read it from
  `https://greate43.github.io/.well-known/assetlinks.json`. It must never redirect. The source of truth is
  `hosting/.well-known/assetlinks.json` in greate43/Nexora — keep the two identical. `.nojekyll` makes Pages
  serve the `.well-known` folder.
- `index.html` + `hub.css` — the Greatdev Studios hub. On github.io it forwards visitors to
  https://greatdevstudios.com/ (canonical); the Cloudflare Worker `greatdev-site` serves it there.
- `sitemap-studio.xml` — the hub's own URLs. The Worker generates `robots.txt` and `sitemap.xml` for the apex
  (an index of every app subdomain's sitemap) and for each subdomain.

Each app lives on its own subdomain, served by the Worker from the GitHub Pages sites:
steelrank. → `/fitness/drill/`, docora. → `/Docora/`, subtrack. → `/SubscriptionSaver/`, nexora. → `/Nexora/`
(plus `/.well-known/assetlinks.json`), safespend. → `/SafeSpend/`, and the other fitness apps by store name.
Old addresses (github.io paths, greatdevstudios.com/<app>/) 301 to the subdomain. Files the apps download from
github.io are untouched.
