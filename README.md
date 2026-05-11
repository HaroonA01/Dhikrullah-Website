# Dhikrullah Landing Page

Static landing page for the Dhikrullah app. Detects iOS / Android user agent and redirects to the matching app store, with manual fallback buttons.

## Files

- `index.html` — single-file site, Tailwind via CDN, vanilla JS redirect logic.

## Configure store URLs

Open `index.html` and edit the `URLS` constant near the bottom:

```js
const URLS = {
  ios:     'https://apps.apple.com/...',
  android: 'https://play.google.com/store/apps/details?id=com.haroonaftab.dhikrullah',
  github:  'https://github.com/<user>/<repo>',
};
```

While any URL is left as `'#'`, the auto-redirect for that platform is disabled and the button is inert. Manual buttons remain visible regardless.

## Disable auto-redirect

Set `AUTO_REDIRECT = false` in the script block.

## Deploy on GitHub Pages

1. Create a new GitHub repo (any name, e.g. `dhikrullah-site`).
2. Copy `index.html` (and this README) into it.
3. Push to `main`.
4. Repo Settings → Pages → Source = `main` / `/ (root)` → Save.
5. Site goes live at `https://<user>.github.io/<repo>/` within ~1 minute.
6. Update the share link in the app (`constants/about.ts: APP_STORE_URL`) to that GitHub Pages URL.

## Custom domain (optional)

For `https://dhikrullah.app`:

1. Buy domain, point DNS A records / CNAME to GitHub Pages (see GitHub docs).
2. Add a `CNAME` file containing `dhikrullah.app` to the repo root.
3. Repo Settings → Pages → set custom domain → enable HTTPS.

## Theme

Palette taken from the app's default Sage Garden theme (`constants/themes.ts`). CSS variables switch automatically via `prefers-color-scheme`.
