# Evan — Composer (static portfolio)

Simple static portfolio with a homepage and a bio page.

Preview locally:

Windows PowerShell:

```
# from repository root
python -m http.server 8000

# then open http://localhost:8000/index.html
```

Files added:

- `index.html` — landing page
- `bio.html` — biography and contact
- `css/styles.css` — site styles

Next steps you might want:

- Replace placeholder contact emails
- Add audio samples and scores
- Add more pages for press, works, and recordings

## Publishing to GitHub Pages

This repository is ready to be served as a GitHub Pages site. The site is a plain static site (HTML + CSS) and already uses relative links so it will work as a project site at:

	https://<your-github-username>.github.io/portfolio1/

What I added:

- `.nojekyll` — prevents GitHub Pages' Jekyll processor from ignoring files/directories that start with an underscore.
- `.github/workflows/pages.yml` — a GitHub Actions workflow that automatically deploys the repository to GitHub Pages whenever you push to `main`.

How to publish (quick):

1. Make sure this repo is pushed to GitHub (replace the remote URL if you haven't already):

```powershell
# from repository root
git init ; git add . ; git commit -m "Prepare site for GitHub Pages" ; git branch -M main ; git remote add origin https://github.com/<your-github-username>/portfolio1.git ; git push -u origin main
```

2. The workflow `pages.yml` will run on push and publish your site. Wait a minute and then visit:

	https://<your-github-username>.github.io/portfolio1/

Alternative: enable Pages from the repository Settings > Pages and set the source to the `main` branch (root). If you prefer manual publishing, this is fine too.

Notes and tips
- Keep links relative (no leading `/`) so pages and assets work from the project path — your files already follow this pattern (e.g. `css/styles.css`, `bio.html`).
- If you add a custom domain, add a `CNAME` file with your domain in the repository root and configure DNS.
- If you use other build steps later (Sass, bundlers), adapt the workflow to build and upload the `dist` folder instead of the repo root.

If you want, I can also add a small `CNAME` template, a nicer workflow that builds with a static site generator, or enable a deploy preview step. Tell me which option you prefer.

