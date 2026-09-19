# EITIE Future Lab

Interactive research games for EITIE's Open Campus presentation: Phone Rescue, Factory Rush, and Shopper Lab. The research themes are digital product passports, applied AI in supply chains and manufacturing, and consumer digital twins.

## Deploy on Cloudflare Pages

1. In the [Cloudflare dashboard](https://dash.cloudflare.com/), open **Workers & Pages → Create application → Pages → Import an existing Git repository**.
2. Connect GitHub, authorize access to **MohammadrezaConstructor/eitieGame**, and select this repository.
3. Enter these settings:

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | `exit 0` |
| Build output directory | `public` |
| Root directory | Leave empty (repository root) |
| Environment variables | None |

4. Select **Save and Deploy**. Cloudflare assigns a live HTTPS address ending in `.pages.dev`. Use the address shown after deployment to share the games or make a QR code.

Select a **Pages** project. This repository serves static files and does not need a Worker, Wrangler deploy command, backend, database, API keys, or paid AI service. Cloudflare Pages' Free plan supports this site; its published limits currently include 500 builds per month and a 25 MiB limit per file. The HTML is about 1.6 MB.

After Git integration is connected, pushes to `main` automatically deploy updates. If the repository is missing in Cloudflare's picker, grant the Cloudflare GitHub app access to this repository.

Official guides: [Static HTML deployment](https://developers.cloudflare.com/pages/framework-guides/deploy-anything/), [Git integration](https://developers.cloudflare.com/pages/get-started/git-integration/), and [Pages limits](https://developers.cloudflare.com/pages/platform/limits/).

## Files and updates

- `public/index.html` is the provided standalone HTML, copied without changes. It includes the compiled application, styles, and embedded images, including the EITIE logo.
- `.gitignore` is the repository's existing ignore file.

Only `public` is published as the website. To update the demo, replace `public/index.html` with the next complete HTML export and commit it to `main`. This repository currently contains the compiled HTML export, not the original editable React project or its tests.

## Local and event use

Open `public/index.html` directly in a browser for the standalone offline version. Optional: run `python3 -m http.server 8000 --directory public` from the repository root to preview it over HTTP at `http://localhost:8000`.

After deploying, check the live URL on the presenting laptop and a phone: open each game, test repair controls and the conveyor, finish a shopper experiment, switch languages, and test replay/reset. Deployment preparation checks do not replace a full gameplay or device audit. Keep a downloaded HTML copy as an offline fallback. External research links require an internet connection.
