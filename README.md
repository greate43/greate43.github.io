# greate43.github.io

Root of the GitHub Pages domain. It exists for one reason: Android App Links verification reads
`https://greate43.github.io/.well-known/assetlinks.json` from the domain root, and a project site
(`/Nexora/`) cannot serve that path. The source of truth is `hosting/.well-known/assetlinks.json` in
greate43/Nexora — keep the two identical. `.nojekyll` makes Pages serve the `.well-known` folder.
Everything else redirects to https://greate43.github.io/Nexora/.
