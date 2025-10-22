# ETHICS 4 BENEFIT Website

## Overview
- Static export of the ETHICS 4 BENEFIT site has been reorganised into a Jekyll project so it can be rebuilt cleanly on GitHub Pages without altering the existing design or copy.
- Original WordPress artefacts that were not needed for the rendered site were removed (e.g. the Simply Static temporary files) while all assets that drive the look and behaviour of the pages remain untouched.
- Each public page now carries Jekyll front matter so the generated output exactly matches the prior HTML while still being configurable via `_config.yml`.

## Structure
- `_config.yml` – core Jekyll settings (site metadata, exclusions, theme disabled).
- `_layouts/default.html` – pass-through layout that keeps the legacy markup intact.
- `index.html` and the section directories (`investors`, `platform`, `traders`, etc.) – original HTML files with minimal front matter for Jekyll processing.
- `wp-content` / `wp-includes` – legacy assets (CSS, JS, media) required for the current appearance.

## Local Development
- Prerequisites: Ruby and Bundler. Install dependencies with `bundle install`.
- Build locally with `bundle exec jekyll serve`; the site will be available at `http://localhost:4000`.
- Because network access was restricted in this environment the gems were not installed here; run the commands above on your machine to verify.

## Deployment
- Commit the project and push to the GitHub Pages branch (e.g. `main` for user/org pages or `gh-pages` for project pages).
- GitHub Pages will detect the Jekyll configuration and rebuild the site automatically, emitting the same HTML that was previously hosted.
- Be sure `_site/` remains ignored (see `.gitignore`) so only source assets are tracked.
