# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal academic portfolio website for Nishanth Adithya Chandramouli, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme. It is deployed to GitHub Pages at `https://nishanthadithya.github.io`.

## Development Commands

### With Docker (recommended)
```bash
docker compose pull
docker compose up
# Site available at http://localhost:8080 with LiveReload on :35729
```

### Without Docker (requires Ruby + Bundler + Python3)
```bash
bundle install
bundle exec jekyll serve
# Site available at http://localhost:4000
```

### Other tasks
```bash
bundle exec jekyll build        # Production build → _site/
npx prettier . --write          # Format all files (Liquid-aware)
purgecss -c purgecss.config.js  # Purge unused CSS after build
```

Deployment to GitHub Pages happens automatically via GitHub Actions on push to `main`. Manual deployment: `./bin/deploy`.

## Architecture

**Stack:** Jekyll 4.x (Ruby) + Liquid templates + SCSS + GitHub Pages

### Key Content Directories
| Directory | Purpose |
|---|---|
| `_config.yml` | All site-wide settings — start here for any configuration change |
| `_pages/` | Static pages (about, blog, projects, publications, CV, etc.) |
| `_posts/` | Blog posts (`YYYY-MM-DD-title.md` naming required) |
| `_projects/` | Project portfolio entries |
| `_news/` | News/announcement items |
| `_bibliography/papers.bib` | BibTeX publications (rendered by `jekyll-scholar`) |
| `_data/` | YAML data files: `cv.yml`, `repositories.yml`, `coauthors.yml`, socials |
| `assets/json/resume.json` | JSON Resume format (alternative to `_data/cv.yml`) |

### Key Theme Directories
| Directory | Purpose |
|---|---|
| `_layouts/` | Liquid page templates |
| `_includes/` | Liquid partials (reusable components) |
| `_sass/` | SCSS stylesheets; `_themes.scss` controls color variables |
| `_plugins/` | Custom Jekyll plugins |
| `_scripts/` | JS setup scripts (analytics, search, photoswipe) |

### Configuration-First Design
Nearly everything is controlled via `_config.yml` — analytics, dark mode, navbar/footer behavior, search, social links, max width. Check `_config.yml` before editing templates.

## Common Customization Tasks

- **Personal info / bio:** `_pages/about.md` and `_config.yml`
- **Publications:** Add BibTeX entries to `_bibliography/papers.bib`
- **CV:** Edit `_data/cv.yml` or `assets/json/resume.json`
- **Social links:** `_config.yml` (social section) or `_data/socials.yml`
- **Theme colors:** `_sass/_themes.scss`
- **Navigation pages:** `_config.yml` → `nav_bar` section, and corresponding file in `_pages/`

## Formatting

Prettier with `@shopify/prettier-plugin-liquid` handles all formatting. Config is in `.prettierrc`. The GitHub Actions `prettier.yml` workflow enforces this on PRs.
