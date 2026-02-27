# CLAUDE.md

## Project Overview

Personal website for Thanh Nguyen — a static, single-page site built with plain HTML and CSS. No build tools, frameworks, or JavaScript.

## Repository Structure

```
.
├── index.html          # Single-page site (nav, home, bio, projects, links sections)
├── styles.css          # All styles — layout, typography, responsive breakpoints
├── FullSizeRender.jpg  # Profile photo
└── CLAUDE.md           # This file
```

## Tech Stack

- **HTML5** — semantic markup, no templating
- **CSS3** — vanilla CSS, no preprocessors (Sass/Less)
- **Google Fonts** — Carlito font family loaded via `<link>`
- **No JavaScript** — purely static content
- **No build/bundling** — files are served as-is

## Development Workflow

There is no build step, test suite, or linter configured. To preview changes, open `index.html` in a browser.

### Key conventions

- **Max content width**: 760px (set on `nav ul` and `main`)
- **Font**: Carlito (Google Fonts), falling back to Calibri, sans-serif
- **Base font size**: 11pt
- **Color palette**: `#222` body text, `#111` headings, `#555` secondary text, `#1a6dd4` links, `#fff` background
- **Responsive breakpoint**: 600px (single mobile breakpoint in `styles.css`)
- **Smooth scrolling**: enabled via `scroll-behavior: smooth` on `html`
- **Fixed nav**: navigation bar is fixed to the top of the viewport

## Page Sections

The site uses anchor-based navigation across four sections:

1. **#home** — Profile photo, name, tagline
2. **#bio** — Short biography
3. **#projects** — Current projects list
4. **#links** — Social media links (X/Twitter, LinkedIn, Instagram)

## Guidelines for Making Changes

- Keep the site simple and static — avoid adding JavaScript or build tooling unless explicitly requested.
- Maintain the existing visual style: clean, minimal, content-focused.
- When adding new sections, follow the existing pattern: `<section id="name">` with an `<h2>` heading, and the CSS `section + section` border-top rule will handle dividers automatically.
- Test responsive behavior at the 600px breakpoint after CSS changes.
- Profile image (`FullSizeRender.jpg`) is displayed as a 140px circle (110px on mobile).
