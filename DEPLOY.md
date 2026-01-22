GitHub Pages Deployment

Quick (single-file) deployment steps:

1. Push branch and open a PR:
   - git push -u origin refactor/full-refactor-in-browser
   - Open a PR and merge to `master` (or `main`).

2. Enable GitHub Pages:
   - Go to your repository > Settings > Pages.
   - Select `Branch: master` and `Root` as the folder (or `gh-pages` branch if you prefer).
   - Save. Your site will be published at https://<your-org-or-user>.github.io/<repo>/ within a minute.

Notes & options:
- For long-term maintainability consider migrating to a small build system (Vite/React) and publishing the `dist/` folder to GitHub Pages.
- Keep the site as a single-file SPA for zero-build quick edits (what this repo currently uses).
- If you want, I can scaffold a Vite project and migrate the handbook into modular React files (recommended for collaboration and testability).