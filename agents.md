# AGENTS.md

## Project Overview

Static single-page portfolio site. No framework, no build step, no dependencies.

## Architecture

```
/
├── index.html      # Entire site — markup, styles (inline <style>), and JS
├── netlify.toml    # Tells Netlify to publish from the repo root
└── README.md
```

## Key Decisions

- **No framework**: the entire site is one self-contained HTML file. All CSS is in a `<style>` block; all JS is in a `<script>` block at the bottom. This is intentional — the site has no dynamic data needs.
- **Publish directory**: `netlify.toml` sets `publish = "."` so Netlify serves `index.html` from the repo root.
- **Scroll animations**: driven by `IntersectionObserver` — elements with class `reveal` fade in when they enter the viewport. No external animation library.
- **Dashboard mockups**: the Power BI and Excel UI mockups are pure CSS/HTML with inline SVG — no images or external assets.

## Coding Conventions

- CSS custom properties (variables) defined in `:root` for the dark-green colour palette.
- BEM-like flat class names (`.pbi-kpi`, `.excel-cell`, `.step-inner`).
- Responsive breakpoint at 720px via a single `@media` block at the bottom of the stylesheet.
- To add a new project section: copy an existing `<section class="proj-section">` block, increment the number, update IDs and nav links.
