# Quantum Verse 2026 — Render Deployment

This is a single static HTML file (`index.html`), so it needs **zero build
step** on Render. There are two ways to deploy it — pick whichever is easier
for you.

## Option A — One-click Blueprint (uses `render.yaml`, already included)

1. Create a new GitHub (or GitLab) repository and push this folder to it:
   ```bash
   cd quantum-verse-2026
   git init
   git add .
   git commit -m "Quantum Verse 2026 site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
2. Go to the [Render Dashboard](https://dashboard.render.com/) → **New +** →
   **Blueprint**.
3. Connect the repo you just pushed. Render will detect `render.yaml`
   automatically and set everything up (no build command, publish path `./`).
4. Click **Apply** — Render builds and deploys in under a minute.
5. Your site is live at `https://quantum-verse-2026.onrender.com`
   (or whatever name you choose).

## Option B — Manual Static Site (no `render.yaml` needed)

1. Push the folder to GitHub/GitLab as in step 1 above.
2. In the Render Dashboard: **New +** → **Static Site**.
3. Connect your repo.
4. Leave **Build Command** empty and set **Publish Directory** to `.`
   (the repo root, since `index.html` lives there).
5. Click **Create Static Site**.

## After deploying

- **Free automatic HTTPS** and a global CDN are included by default.
- **Custom domain**: Dashboard → your site → *Settings* → *Custom Domains* →
  add your domain (e.g. `quantumverse.tjspc.edu`) and point its DNS to
  Render per the on-screen instructions.
- **Updating the site**: just edit `index.html`, commit, and push — Render
  auto-redeploys on every push to your connected branch.
- **Changing the event date/countdown**: search `index.html` for
  `2026-08-25T10:30:00` and update it before your next event.

## Files in this folder

- `index.html` — the full site (single file: HTML + CSS + JS, no dependencies)
- `render.yaml` — Render Blueprint config (Option A)
- `README.md` — this file
