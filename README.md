# WOW Portal Mockup

Static single-page mockup (Tailwind via CDN, no build step). Deploys to Render as a **Static Site**.

## Deploy to Render

Render deploys static sites from a Git repo — there's no drag-and-drop upload, so push this folder to GitHub/GitLab first.

1. Push this folder to a new repo:
   ```bash
   cd wow-portal-mockup
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. In the Render dashboard: **New > Static Site**, connect the repo.
3. Settings:
   - **Build Command:** leave blank
   - **Publish Directory:** `.`
4. Click **Create Static Site**. Render gives you a live `*.onrender.com` URL.

### Faster path: Blueprint deploy
This repo includes `render.yaml`. Instead of step 2–3 above, use **New > Blueprint**, point it at the repo, and Render reads `render.yaml` automatically. (If the dashboard rejects `runtime: static`, swap it for `env: static` — Render has used both keys across versions.)

## Notes
- Tailwind loads from the CDN (`cdn.tailwindcss.com`) at runtime — fine for a mockup/demo, not ideal for production (larger payload, external dependency, no purging of unused classes). Say the word if you want this converted to a compiled Tailwind build later.
- Single page, no routing/backend — this is a static mockup, not a functioning app.
