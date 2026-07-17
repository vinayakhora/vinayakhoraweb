# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is the Hugo static site for **Vinayak Hora** (vinayakhora.in), a Vedic astrology site with content in English and Hindi. It uses the **Anatole** theme, which is not a git submodule — it has been vendored and customized directly inside `themes/anatole`.

## Commands

- `hugo server -D` — run the local dev server, including draft content (`-D`). The command prints the local URL to view the site.
- `hugo` — build the production site into `public/`. Run with no arguments.
- `hugo new content content/en/post/my-post.md` — scaffold a new English post (uses `archetypes/default.md`, which sets `draft = true`).

There is no test suite, linter, or package.json at the repo root — this is a content-driven Hugo site, not an app with build tooling beyond Hugo itself.

### CI/deploy

`.github/workflows/hugo.yml` builds and deploys to GitHub Pages on every push to `main` (or manual dispatch). It pins `HUGO_VERSION` (extended edition), `GO_VERSION`, `NODE_VERSION`, and `DART_SASS_VERSION` — match these locally if builds behave differently than CI. The build command it uses is `hugo --gc --minify --baseURL <pages-url>/`.

## Bilingual content structure

Every piece of user-facing content must exist in **both languages**, kept in parallel directories:

- `content/en/...` — English (`contentDir` set in `config/_default/languages.toml`)
- `content/hi/...` — Hindi (`contentDir` set in `config/_default/languages.toml`)

When adding or editing a post, page, or static content, mirror the change in both `content/en/` and `content/hi/` with matching filenames (e.g. `content/en/post/ganesha-first-lord.md` / `content/hi/post/ganesha-first-lord.md`). New posts are created as drafts (`draft = true` in front matter) and must be flipped to `draft = false` before they'll appear on the live site.

## Configuration

Config lives under `config/_default/` and is split by concern:
- `hugo.toml` — main site config (theme selection, markup/goldmark settings, taxonomies, related-content weighting, Mermaid, services like Disqus/Google Analytics)
- `languages.toml` — per-language settings (title, contentDir, weight); language-specific params can be nested here under `[en.params]` / `[hi.params]` and override the global `params.toml`
- `params.toml` — theme parameters consumed by the Anatole theme's partials (profile picture, date formats, sidebar/content ratio, social icons, analytics providers, etc.)
- `menus.en.toml` / `menus.hi.toml` — per-language nav menu entries (`main` and `footer` menus)

Parameter resolution order: a param defined at the language level (`languages.toml`) takes precedence; otherwise it falls back to the site-wide `hugo.toml`/`params.toml`.

## Theme customization

The Anatole theme has been detached from its upstream repo and lives as a plain directory at `themes/anatole` (see `setup.txt`) — it is edited directly rather than updated via submodule/package manager. Theme partials (the actual HTML building blocks for page sections — sidebar, header, etc.) are in `themes/anatole/layouts/partials/`; e.g. the left sidebar markup is `themes/anatole/layouts/partials/sidebar.html`. To change how a page section looks or reads (including static per-language strings like the YouTube subscribe prompt), edit the relevant partial and wire in language-aware params (params defined in the language config are picked up automatically; use the `relLangURL` filter on URLs/paths that need to resolve within the current language's subtree).

Upstream theme docs: https://github.com/lxndrblz/anatole/wiki

## Static assets

`static/` holds files served as-is at the site root (favicons, `app-ads.txt`, `robots.txt` inputs, images, and `static/app-data/` which contains app-related downloads like the sample horoscope PDF and app data file referenced by the Mobile App page). `public/` is the generated build output — do not hand-edit it, it's overwritten by `hugo`.

The root `layouts/` directory (separate from `themes/anatole/layouts/`) holds site-level template overrides that take precedence over the theme — currently just `robots.txt`.
