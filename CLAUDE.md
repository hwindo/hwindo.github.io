# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

**Local Development:**
```bash
bundle install          # Install Ruby dependencies
bundle exec jekyll serve # Start local server at http://127.0.0.1:4000
```

**Build:**
```bash
bundle exec jekyll build --baseurl ""  # Build site to _site directory
```

## Architecture Overview

This is a Jekyll-based portfolio website hosted on GitHub Pages. The site showcases projects, blog posts, and includes interactive playground components.

**Key Structure:**
- `_config.yaml` - Main Jekyll configuration
- `_data/project_list.yml` - Central project database with metadata, descriptions, and links
- `_layouts/` - Page templates (default, frontpage, post, etc.)
- `_includes/` - Reusable components (header, nav, footer, project-list)
- `_sass/` - Modular SCSS stylesheets imported via `css/styles.scss`
- `_playground/` - Interactive demo components with their own collection
- `_posts/` - Blog articles in markdown format

**Frontend Architecture:**
- Vanilla JavaScript with ES6 modules in `assets/js/`
- Component-based JS (logo animation, screen loader)
- SCSS with BEM-style organization
- Service Worker for offline functionality
- Progressive Web App features (manifest.json, icons)

**Content Management:**
- Projects are managed via YAML data file rather than individual markdown files
- Each project includes metadata (role, year, tags), descriptions, and multiple URL types
- Collections system used for playground demonstrations
- Blog posts follow Jekyll's standard `_posts/` structure

**Deployment:**
- GitHub Actions workflow deploys to GitHub Pages automatically on push to main
- Ruby 3.1 with Ubuntu 22.04 build environment
- Site builds with production JEKYLL_ENV