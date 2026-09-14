# syedfahadrizvi.github.io

Personal academic portfolio for **Syed Muhammad Fahad Rizvi** — Senior Machine Learning Engineer
(computer vision, 3D reconstruction, multi-object tracking, MLOps). Built with the
[al-folio](https://github.com/alshedivat/al-folio) Jekyll theme (gem-based, `theme: al_folio_core`).

## Structure

- `_config.yml` — site configuration and identity.
- `_pages/about.md` — homepage (`/`).
- `_pages/projects.md` — projects grid (`/projects/`).
- `_pages/cv.md` — CV page (`/cv/`), rendered from `_data/cv.yml` (rendercv format).
- `_projects/*.md` — five project case studies (photogrammetry, label-free detection,
  US DOT challenge, VRU tracking, camera calibration). Pipeline diagrams use Mermaid.
- `_data/socials.yml` — social links (GitHub, LinkedIn, email).
- `assets/` — images (incl. `img/photogrammetry-grid.jpg`) and theme assets.

## Build & deploy

GitHub Pages cannot build al-folio natively (it uses unsupported plugins), so
`.github/workflows/deploy.yml` builds the site on GitHub Actions and publishes `_site/` to the
`gh-pages` branch on every push to `main`. GitHub Pages must be configured to serve from
`gh-pages`.

### Local preview (requires Ruby)

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.
