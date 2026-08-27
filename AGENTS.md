# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-powered personal homepage. `index.html` selects the main layout, while `_layouts/resume.html` contains the page structure and Liquid templates. Reusable fragments live in `_includes/`; icon includes are under `_includes/icons/`. Site content is primarily maintained as YAML in `_data/` (for example, `_data/publications.yml` and `_data/projects.yml`), and global settings and section toggles live in `_config.yml`.

Styles begin at `css/main.scss` and are split into partials under `_sass/`. Put publication images in `images/`, downloadable papers and CVs in `doc/`, and editable design sources in `_assets/`. Do not edit generated or cached directories such as `_site/`, `.sass-cache/`, or `_vendor/`.

## Build, Test, and Development Commands

- `bundle install` installs the Ruby dependencies recorded in `Gemfile.lock`.
- `bundle exec jekyll serve` builds the site and serves it at `http://localhost:4000`; restart it after changing `_config.yml`.
- `bundle exec jekyll build` performs the production-style build used by CI and writes output to `_site/`.
- `bundle exec jekyll build --trace` provides a stack trace when Liquid, YAML, or plugin errors occur.

## Coding Style & Naming Conventions

Use two-space indentation in YAML, HTML/Liquid, and SCSS. Preserve the existing YAML list shape and field names when adding content. Quote values that contain YAML-sensitive punctuation, and keep embedded HTML valid. Use lowercase, descriptive filenames for assets (for example, `images/efficient_defocus_deblur.jpg`). Name SCSS partials with a leading underscore and import them from `css/main.scss`.

No formatter or linter is configured, so keep changes focused and follow the surrounding style. Avoid committing generated build artifacts or operating-system metadata.

## Testing Guidelines

There is no automated test framework or coverage target. Every change should pass `bundle exec jekyll build`. For content or styling changes, also inspect the local site at desktop and narrow widths, check images and external links, and verify print/PDF presentation when modifying résumé layout or print styles.

## Commit & Pull Request Guidelines

Recent commits use short, imperative subjects such as `Update resume header introduction details`, `Fix typo ...`, and `Refactor ...`. Follow that pattern and keep each commit scoped to one logical change.

Pull requests should summarize the visible result, identify affected data or layout files, and report the build command run. Link relevant issues and include before/after screenshots for visual changes. Do not include unrelated `_site/` output or cache files.
