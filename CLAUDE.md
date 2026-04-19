# storyhourimprov.com

Hugo static site using the Docsy theme, deployed to GitHub Pages via GitHub Actions on every push to `main`.

## Hard constraints

- **No backend, no server-side code.** The site is intentionally 100% static to keep hosting free on GitHub Pages. Do not introduce anything that requires a server, paid hosting, or a paid API tier.
- **Third-party API calls must be safe for a public static site.** API keys cannot appear in the source — they'd be visible to anyone. Use GitHub Actions secrets for any keys, and pre-fetch external data at build time rather than from the browser.

## Deployment

Push to `main` → GitHub Actions builds Hugo → deploys to GitHub Pages automatically.
