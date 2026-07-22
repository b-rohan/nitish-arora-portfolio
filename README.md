# Deploying to GitHub Pages

This folder (`site/`) is a static site — just `index.html` + `images/`. No build step.

## Option A — Web UI (no git needed)

1. Go to github.com → New repository → name it (e.g. `portfolio`) → Create.
2. On the repo page, click **Add file → Upload files**, drag in `index.html` and the `images` folder, then **Commit changes**.
3. Go to **Settings → Pages**.
4. Under **Source**, select **Deploy from a branch**, branch `main`, folder `/root` → **Save**.
5. Wait ~1 minute, then visit `https://<your-username>.github.io/<repo-name>/`.

## Option B — Command line

```bash
cd site
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages the same way: **Settings → Pages → Source: Deploy from a branch → main /root → Save**.

## Using a personal domain (e.g. `nitisharora.com`)

1. In **Settings → Pages**, enter it under **Custom domain** and save (this creates a `CNAME` file in the repo).
2. At your domain registrar, add a `CNAME` record pointing to `<your-username>.github.io`.

## Notes

- If you name the repo `<your-username>.github.io`, the site is served at the root URL instead of `/repo-name/`.
- Any push to `main` auto-redeploys the site — no extra steps needed.
