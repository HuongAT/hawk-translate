# Hawk Translate — GitHub Pages Site

A two-page static site for the **Hawk Translate** browser extension (Firefox / Chrome / Edge).

## Files

| File | Purpose |
|---|---|
| `index.html` | Landing page — hero, features, backends, languages, install CTAs |
| `privacy.html` | Privacy policy page (linked from the extension store listings) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (no Jekyll processing) |

Everything is **single-file** — no build step, no dependencies. Fonts are loaded from Google Fonts via CDN.

## Deploying to GitHub Pages

### Option A — User/Organization site
1. Create a public repo named `<your-username>.github.io`.
2. Drop these files in the root.
3. Push to `main`. Site goes live at `https://<your-username>.github.io/`.

### Option B — Project site (recommended for the extension)
1. Push these files to a repo (e.g. `hawk-translate`) in a branch (`main`) or in a `/docs` folder.
2. Go to **Settings → Pages**.
3. Under **Source**, pick the branch (and `/docs` if you used that folder).
4. Save. Site goes live at `https://<your-username>.github.io/hawk-translate/`.

```bash
git init
git add .
git commit -m "Hawk Translate site"
git branch -M main
git remote add origin git@github.com:<your-username>/<repo>.git
git push -u origin main
```

## Things you should customize before going live

In `index.html`, search for these placeholders and update them:

- `id="firefox-link"` — set `href` to your Firefox AMO listing URL
- `id="chrome-link"` — set `href` to your Chrome Web Store listing URL
- `id="edge-link"` — set `href` to your Edge Add-ons listing URL
- The "Get Hawk Translate" button (`href="#install"`) currently scrolls to the install section; you can also point it at the Firefox listing if you prefer

In `privacy.html`:
- The **Contact** section at the bottom — replace the generic GitHub-issue language with your actual contact email or repo URL.
- The **Last updated** date in the hero — bump it whenever you make a material change.

## Privacy policy URL for store listings

When submitting to the Firefox AMO, Chrome Web Store, or Microsoft Edge Add-ons, paste this as your privacy policy URL:

```
https://<your-username>.github.io/<repo>/privacy.html
```

Or for a user/organization site:

```
https://<your-username>.github.io/privacy.html
```

## Design notes

- **Typography:** Fraunces (display, italic-heavy) + Inter Tight (body) + JetBrains Mono (eyebrows / captions)
- **Palette:** Deep midnight ink (`#0c1420`) + warm paper (`#f5f1e8`) + amber/gold accent (`#fbbf24`) + sage and rust as secondary accents
- **Aesthetic:** Editorial / modern, with a warm "old-paper-meets-newsroom" feel that fits the language-learning theme
- **Responsive:** All sections collapse cleanly to mobile (breakpoints at 980px, 720px, 600px)
- **No JS dependencies:** Just one tiny IntersectionObserver for scroll-reveal

## License

MIT (matches the extension itself).