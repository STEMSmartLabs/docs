# STEM Smart Labs — Docs (Rich + Formatted) — 20250813-103928

This is a single MkDocs project for both products with:
- Rich product pages (hero photos, playlists, module table)
- Properly formatted code blocks with line numbers
- Material theme and compact footer

## Quick start
```bash
pip install -r requirements.txt
mkdocs serve
```

## Deploy to GitHub Pages
```bash
git init && git add . && git commit -m "docs: initial"
git branch -M main
git remote add origin https://github.com/<ORG_OR_USER>/<REPO>.git
git push -u origin main
mkdocs gh-deploy --force
```
