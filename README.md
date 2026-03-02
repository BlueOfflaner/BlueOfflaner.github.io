# Hexo Personal Blog

This repository contains a Hexo-based personal blog with the Butterfly theme and GitHub Pages deployment workflow.

## Local development

```bash
npm install
npm run server
```

Open `http://localhost:4000`.

## Build static files

```bash
npm run build
```

Generated files are in `public/`.

## GitHub Pages deployment

1. Update the placeholders in `_config.yml`:
   - `url`
   - `deploy.repo`
2. Update the placeholders in `_config.butterfly.yml`:
   - `social` GitHub link
   - `giscus.repo`
   - `giscus.repo_id`
   - `giscus.category_id`
   - `google_analytics`
3. Push to `main` or `master` branch.
4. In GitHub repo settings, set Pages source to `GitHub Actions`.

The workflow file is `.github/workflows/deploy-pages.yml`.
