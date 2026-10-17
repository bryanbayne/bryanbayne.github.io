# bryanbayne.com — personal academic website

Personal academic/consulting website for Bryan Trannin Bayne, built with
[Quarto](https://quarto.org) and deployed to GitHub Pages via GitHub Actions.

## Local development

```powershell
quarto preview        # live-reloading local server
quarto render         # one-off build into docs/
```

## Structure

| Path | Purpose |
|---|---|
| `_quarto.yml` | Site config: navigation, theme, social metadata, analytics |
| `custom.scss` | All visual styling (fonts, palette, cards, badges) |
| `index.qmd` | Homepage (Quarto "about" page, trestles template) |
| `research.qmd` | Working papers and research interests |
| `cv.qmd` | Web CV (links to `files/cv.pdf`) |
| `consulting.qmd` | Consulting services and portfolio |
| `blog/` | Listing page + posts under `blog/posts/<date-slug>/index.qmd` |
| `files/cv.pdf` | Downloadable CV |
| `images/` | Headshot, favicon |
| `.github/workflows/publish.yml` | Renders and deploys on every push to `main` |

## Deploying

1. Create a GitHub repo (for a clean URL, name it `<username>.github.io`).
2. Push `main`.
3. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. Every push to `main` now rebuilds and deploys the site automatically.
   (`docs/` is gitignored — the Action rebuilds it in CI, so you never commit build output.)

## Adding a blog post

Create `blog/posts/YYYY-MM-DD-slug/index.qmd` with `title`, `description`,
`date`, and `categories` in the front matter. The listing page picks it up
automatically.
