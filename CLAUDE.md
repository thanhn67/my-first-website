# CLAUDE.md

## Project Overview

Personal website for Thanh Nguyen — a static, single-page site built with HTML, CSS, and minimal vanilla JavaScript (dark mode toggle + scroll animations). No build tools or frameworks.

## Repository Structure

```
.
├── index.html          # Single-page site (nav, home, bio, projects, links, footer)
├── styles.css          # All styles — layout, dark mode, animations, print stylesheet
├── favicon.svg         # Cute chef hat SVG favicon
├── FullSizeRender.jpg  # Profile photo
└── CLAUDE.md           # This file
```

## Tech Stack

- **HTML5** — semantic markup, no templating
- **CSS3** — vanilla CSS with custom properties for theming, no preprocessors
- **Vanilla JS** — dark mode toggle (with localStorage persistence) and IntersectionObserver scroll animations
- **Google Fonts** — Carlito font family loaded via `<link>`
- **No build/bundling** — files are served as-is

## Development Workflow

There is no build step, test suite, or linter configured. To preview changes, open `index.html` in a browser.

### Key conventions

- **Max content width**: 760px (set on `.nav-inner` and `main`)
- **Font**: Carlito (Google Fonts), falling back to Calibri, sans-serif
- **Base font size**: 11pt
- **Color system**: CSS custom properties on `:root` (light) and `body.dark` (dark); never use hardcoded color values in new rules — always reference `var(--token)`
- **Responsive breakpoint**: 600px (single mobile breakpoint)
- **Smooth scrolling**: enabled via `scroll-behavior: smooth` on `html`
- **Fixed nav**: navigation bar is fixed to the top of the viewport
- **Reduced motion**: `prefers-reduced-motion: reduce` disables scroll animations

### Color tokens

| Token | Light | Dark |
|---|---|---|
| `--bg` | `#fff` | `#1a1a2e` |
| `--text` | `#222` | `#d8d8d8` |
| `--heading` | `#111` | `#f0f0f0` |
| `--secondary` | `#555` | `#aaa` |
| `--link` | `#1a6dd4` | `#6db3f2` |
| `--border` | `#eee` | `#2a2a40` |

## Features

- **Dark mode** — toggle button (sun icon &#9728;) in the nav bar, persisted to `localStorage` under the key `theme`
- **Scroll animations** — sections fade in on scroll via IntersectionObserver with the `fade-in` / `visible` CSS classes
- **Print stylesheet** — hides nav/toggle, shows link URLs inline, avoids page breaks inside sections
- **Favicon** — SVG chef hat (`favicon.svg`)
- **Footer** — copyright + "Back to top" anchor link

## Page Sections

The site uses anchor-based navigation across four sections plus a footer:

1. **#home** — Profile photo, name, tagline
2. **#bio** — Short biography
3. **#projects** — Current projects list
4. **#links** — Social media links (X/Twitter, LinkedIn, Instagram)
5. **footer** — Copyright and back-to-top link

## Guidelines for Making Changes

- **Use CSS custom properties** — all colors should reference `var(--token)` so dark mode works automatically.
- When adding new sections, follow the existing pattern: `<section id="name" class="fade-in">` with an `<h2>` heading. The `section + section` border and `fade-in` class handle dividers and animations automatically.
- Maintain the existing visual style: clean, minimal, content-focused.
- Test at the 600px responsive breakpoint and verify dark mode after CSS changes.
- Profile image (`FullSizeRender.jpg`) is displayed as a 140px circle (110px on mobile).
- Respect `prefers-reduced-motion` — avoid adding animations that don't honor this media query.
