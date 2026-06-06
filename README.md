# Aligned Compass Holdings — Website

Static one-page marketing site for **Aligned Compass Holdings LLC**.
No build step. No framework. No server. Just static files you can host anywhere.

*Aligning Properties. Strengthening Communities. Building Legacy.*

---

## What's in this folder

```
.
├── index.html                  ← the website (open this)
├── styles.css                  ← all styling
├── assets/
│   ├── logo-horizontal.png         header logo
│   ├── logo-reversed.png           footer logo (reversed, on dark green)
│   ├── icon-compass.png            compass mark (accent)
│   ├── icon-compass-reversed.png   compass mark (light, CTA watermark)
│   ├── photo-hero-neighborhood.jpg hero image
│   ├── photo-approach-blueprint.jpg Investment Approach image
│   ├── photo-markets-map.jpg       Target Markets image
│   ├── photo-ops-interior.jpg      What We Do interior band
│   ├── photo-whoweare-texture.jpg  Who We Are brand-texture image
│   ├── favicon-32.png              browser tab icon
│   ├── apple-touch-icon.png        iOS home-screen icon (180×180)
│   └── icon-512.png                large app icon (512×512)
└── README.md                   ← this file
```

All images are real files on disk and are referenced with **relative paths**.
Nothing depends on the browser, JavaScript, or local storage to display — the page
renders fully even with JavaScript disabled. (A small script only adds the header
shadow-on-scroll and gentle fade-in; it is purely cosmetic.)

Fonts (Spectral, Source Sans 3, IBM Plex Mono) load from Google Fonts over the
network, with system serif/sans fallbacks if offline.

---

## Preview it locally

Just double-click `index.html`, or open it in any browser. Because every path is
relative, it works straight from the folder — no local server required.

(Optional, if you prefer a server: `python3 -m http.server` in this folder, then
visit `http://localhost:8000`.)

---

## Deploy to Cloudflare Pages (via GitHub)

### 1 — Put this folder in a GitHub repo

```bash
cd aligned-compass-site      # this folder
git init
git add .
git commit -m "Aligned Compass Holdings website"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

> The contents of this folder should sit at the **root** of the repo, so that
> `index.html` is at the top level of the repository.

### 2 — Connect the repo to Cloudflare Pages

1. Log in to the **Cloudflare dashboard** → **Workers & Pages** → **Create** →
   **Pages** → **Connect to Git**.
2. Authorize GitHub and select your repository.
3. On the build-settings screen:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`  (the repo root — where `index.html` lives)
4. Click **Save and Deploy.**

Cloudflare publishes the files as-is. Your site goes live at
`https://<project-name>.pages.dev` within a minute.

### 3 — (Optional) Custom domain

In the Pages project → **Custom domains** → **Set up a domain**, add e.g.
`alignedcompassholdings.com` and follow the DNS instructions. Cloudflare issues
the SSL certificate automatically.

### Updating the site later

Edit the files, then:

```bash
git add .
git commit -m "Update copy / images"
git push
```

Cloudflare Pages redeploys automatically on every push to `main`.

---

## Swapping images

Replace any file in `assets/` with a new image **of the same filename** (keep it
optimized — ideally < 300 KB, JPEG for photos). No code changes needed. If you
change a filename, update the matching `src="assets/…"` reference in `index.html`.

---

## Notes

- **Scheduling button** → `https://calendly.com/hello-alignedcompassholdings/30min`
  (opens in a new tab). To change it, find-and-replace that URL in `index.html`.
- **Contact details** (phone, location) and the **legal disclaimer** live in the
  footer of `index.html`.
- This is the production build. The drag-and-drop image editor and the in-page
  "Tweaks" panel used during design are intentionally **not** included here — this
  folder is lean, static, and deployment-ready.

© 2026 Aligned Compass Holdings LLC · All rights reserved
