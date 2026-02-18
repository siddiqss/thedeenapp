# thedeen.app — Landing Page

Minimal landing page for [thedeen.app](https://thedeen.app), a nonprofit collection of free, offline-first, privacy-focused Islamic web apps.

## Apps

| App | Landing Page | Web App |
|-----|-------------|---------|
| Ramadan Tracker | `/ramadan-tracker` | [ramadan.thedeen.app](https://ramadan.thedeen.app) |
| Umrah & Hajj Guide | `/umrah-guide` | [umrah.thedeen.app](https://umrah.thedeen.app) |

## Stack

Plain static HTML, CSS, and JS. No build step, no framework, no dependencies.

## Project Structure

```
├── index.html                  # Main landing page (100vh)
├── ramadan-tracker/index.html  # Ramadan Tracker detail page
├── umrah-guide/index.html      # Umrah & Hajj Guide detail page
├── styles/main.css             # Shared stylesheet
├── scripts/main.js             # Shared JS (minimal)
├── assets/icons/               # App icon SVGs
├── wrangler.toml               # Cloudflare Pages config
├── _headers                    # Cloudflare custom headers
└── _redirects                  # Cloudflare redirects
```

## Local Development

Serve with any static file server:

```bash
npx serve .
# or
python3 -m http.server
```


## Deployment

Hosted on [Cloudflare Pages](https://pages.cloudflare.com/).

### Via Wrangler CLI

```bash
npx wrangler pages deploy .
```

### Via Git Integration

1. Push this repo to GitHub/GitLab.
2. In the Cloudflare dashboard, create a new Pages project and connect the repo.
3. Set **Build command** to empty (no build step needed).
4. Set **Build output directory** to `/` (root).
5. Deploy.

### Custom Domain

After deploying, add `thedeen.app` as a custom domain in the Cloudflare Pages project settings.

## Analytics

Cloudflare Web Analytics is included as a commented-out snippet in all pages. To enable:

1. Create a Web Analytics site in your Cloudflare dashboard.
2. Copy the beacon token.
3. Uncomment the analytics script in each HTML file and replace `YOUR_TOKEN_HERE` with your token.
