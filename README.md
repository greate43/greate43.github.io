# greate43.github.io

Root of the GitHub Pages domain, and the origin of **greatdevstudios.com**.

- `.well-known/assetlinks.json` — Android App Links for Nexora read it from
  `https://greate43.github.io/.well-known/assetlinks.json`. It must never redirect. The source of truth is
  `hosting/.well-known/assetlinks.json` in greate43/Nexora — keep the two identical. `.nojekyll` makes Pages
  serve the `.well-known` folder.
- `index.html` + `hub.css` — the Greatdev Studios hub. On github.io it forwards visitors to
  https://greatdevstudios.com/ (canonical); the Cloudflare Worker `greatdev-site` serves it there.
- `sitemap.xml` (index), `sitemap-studio.xml`, `robots.txt` — for greatdevstudios.com. App sitemaps are served
  by the Worker at `/sitemap-fitness.xml`, `/sitemap-docora.xml`, `/sitemap-subtrack.xml`.

The Worker maps clean paths to the GitHub Pages sites: `/steelrank/` → `/fitness/drill/`, `/docora/` →
`/Docora/`, `/subtrack/` → `/SubscriptionSaver/`, `/nexora/` → `/Nexora/`, `/safespend/` → `/SafeSpend/`, and
the other fitness apps by store name. Files the apps download from github.io are untouched.
