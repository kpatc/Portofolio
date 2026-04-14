# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static, single-page portfolio website with no build system. There are no npm scripts, no compilation step, and no test suite. All changes take effect immediately by refreshing the browser.

- **Live site:** https://kpatc.github.io/Portofolio/
- **Hosting:** GitHub Pages (serves directly from the `main` branch)

## Development

Open `index.html` directly in a browser, or use any static file server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## File Layout

```
index.html                        # Entire single-page app (HTML structure + inline section content)
CSS_JS_IMG/
  CSS_JS/script.css               # All custom styles
  CSS_JS/main.js                  # jQuery-based interactivity (navbar, scroll, animations)
  mail/contact.js                 # Contact form AJAX submission + validation
  mail/jqBootstrapValidation.min.js
  Image/                          # Portfolio screenshots and profile images
  cv.pdf                          # Downloadable resume
```

## Architecture

All content lives in `index.html` as a single long page with anchor-linked sections: Hero → About → Education → Experience → Portfolio → Community → Contact.

**Frontend libraries (all loaded via CDN, no local installs):**
- Bootstrap 5.3.0 — layout and responsive grid
- jQuery — DOM manipulation, used throughout `main.js` and `contact.js`
- Typed.js — animated typing in the hero section
- WOW.js + Animate.css — scroll-triggered entrance animations
- Owl Carousel — carousels
- Isotope — portfolio item filtering by category
- Lightbox — image gallery overlay
- Font Awesome 5.10.0 — icons

**Contact form:** submits via AJAX to a `contact.php` backend (not present in this repo). Validation is handled client-side by `jqBootstrapValidation`.

## Deployment

Pushing to `main` automatically publishes to GitHub Pages. No build step required.
