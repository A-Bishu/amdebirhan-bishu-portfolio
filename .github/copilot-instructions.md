# Copilot instructions for this portfolio site

- This is a static HTML/CSS portfolio site. There is no JavaScript, no package manager, no build pipeline, and no backend code in this repo.
- Key files:
  - `index.html`, `about.html`, `skills.html`, `projects.html`, `resume.html`, `contact.html` are standalone pages.
  - `styles.css` is the single shared stylesheet for layout, typography, buttons, responsive behavior, and form styling.

## Architecture and patterns
- Every page uses a repeated `<header><nav>` block and a `<footer>`. Navigation links are duplicated in each page, so updates to the menu should be applied consistently across all HTML files.
- Each content area is wrapped in a `<section>` block. For example, `projects.html` uses `<div class="project">` wrappers for project entries.
- The stylesheet uses simple utility-like classes:
  - `.button` for CTA links
  - `.skills-list` for the responsive skill grid
  - `form`, `form input`, `form textarea`, `form button` for contact page styling
- Page content links are relative, so keep `href="styles.css"` on every page and preserve the same directory layout.

## Project-specific conventions
- The project is delivered as static pages, so avoid introducing server-side logic or backend dependencies.
- `contact.html` uses `mailto:amde.kbishu@gmail.com` for the form action. There is no form processing service in this repository.
- `projects.html` includes project entries for HairStyle AI, SurfIntel, and Pill-Smart mobile apps.
- Avoid local-only file URLs such as `file:///C:/Users/Amde/Desktop/Certificate/file.pdf` in `resume.html`.
- When editing page metadata, verify page titles reflect each page purpose (for example, `Projects`, `Skills`, `Resume`, `Contact`).
- Add a page-specific `<meta name="description">` tag to each HTML page for better static site semantics.
  - Suggested fix: verify each page title matches the page purpose, especially when editing `projects.html`, `skills.html`, or `resume.html`.

## Developer workflow
- Preview locally by opening `index.html` in a browser or using a simple static server from the repo root, for example:
  - `cd /Users/amdebishu/Desktop/Apps/amdebirhan-bishu-portfolio`
  - `python3 -m http.server`
- There is no npm/yarn command or test suite to run in this repo.
- Changes are deployed by publishing the static files directly.

## When modifying the site
- Prefer adjusting layout and theme in `styles.css` rather than adding inline styles to individual HTML pages.
- Keep navigation order and link text consistent across pages.
- If adding a new page, copy the existing header/footer structure from another page and include the stylesheet link.
- Keep external references to live URLs in `projects.html` and `resume.html` accurate.

## Notes for AI agents
- Do not invent backend APIs or server-side components; this repository is static-only.
- Validate that all links in the navigation and footer are correct after edits.
- Watch for copy/paste inconsistencies in page metadata and section headings.
 - Watch out for local-only file URLs such as `file:///C:/Users/Amde/Desktop/Certificate/file.pdf` in `resume.html`.

## Deployment
 - This site is intended to be published as static HTML/CSS files. There is no CI/CD pipeline or deployment script in the repository.
 - Use a static hosting provider (GitHub Pages, Netlify, Azure Static Web Apps, etc.) or upload the files directly to a web host.
