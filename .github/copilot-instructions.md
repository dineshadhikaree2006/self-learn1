<!-- Copilot instructions for AI coding agents in this minimal static site repo -->
# Copilot instructions — self-learn1

Purpose: Help an AI agent be immediately productive in this small static-site workspace.

- **Project type:** Single-folder static site (HTML, CSS, JS). Key files: [aa.html](aa.html), [index.css](index.css), [index.js](index.js), [README.md](README.md).
- **No build system or deps:** There is no package.json, no bundler, and no tests. Treat this as plain static content.

Quick actionable notes
- Fix the script include in `aa.html`: it currently uses a link tag. Replace

```html
<link rel="javascript" href="./index.js">
```
with

```html
<script src="./index.js"></script>
```

- `index.js` is an empty stub file. Add page logic there; keep DOM-ready initialization simple (e.g., `DOMContentLoaded`).
- CSS lives in `index.css`; prefer small, utility-first selectors for this project rather than a large framework.

How to run and debug locally
- Open `aa.html` directly in a browser for quick edits, or serve the folder to avoid cross-origin issues for fetch/XHR.

Example (from workspace root):

```powershell
python -m http.server 8000
# then open http://localhost:8000/aa.html
```

- Alternatively, use VS Code Live Server extension to auto-reload during edits.

Conventions and patterns (repo-specific)
- Single-page layout: `aa.html` is the primary entrypoint. Keep page-specific scripts in `index.js` and styles in `index.css`.
- Relative paths: All asset references are relative; avoid absolute filesystem paths because the project often lives under OneDrive on Windows.
- Minimalism: Prefer direct DOM manipulation and small helper functions rather than introducing frameworks.

What agents should not assume
- No package manager scripts (npm, pip) are present — do not try to run `npm install` or similar unless you add a manifest first.
- No CI configuration or test harness exists in repository — adding one requires creating config files.

Where to look for common edits
- Add interactive logic: [index.js](index.js)
- Update markup: [aa.html](aa.html)
- Style changes: [index.css](index.css)
- Project notes: [README.md](README.md) (currently contains a placeholder).

Suggested first tasks for a new agent
1. Correct the script tag in [aa.html](aa.html).
2. Add a small `DOMContentLoaded` handler in [index.js](index.js) with a console log to verify wiring.
3. Serve locally with `python -m http.server` and verify the page loads.

If anything is unclear or you need more context (e.g., intended UI behavior), ask the human owner before adding external libraries or CI.
