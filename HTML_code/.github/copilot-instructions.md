# GitHub Copilot instructions — small static HTML site

Purpose: Give AI coding agents the minimal, specific knowledge to be productive in this repository.

Quick facts
- Project type: single-page static HTML site (no build system, no dependencies).
- Primary file: [About_Me_Webpage.html](About_Me_Webpage.html) — the served page to edit and preview.
- No package.json, no tests, no server-side code discovered.

Big picture
- This repo is a static website. Changes are primarily content/markup/CSS assets. There are no backend services, APIs, or build pipelines to modify.
- Agents should focus on small, surgical edits to HTML/CSS and clear guidance for manual previewing.

Key files to inspect
- [About_Me_Webpage.html](About_Me_Webpage.html): main entry point. Use this file to locate content to change (title, meta, body sections).

Conventions & patterns discovered
- Files are plain UTF-8 text; preserve encoding and avoid adding BOMs.
- Keep markup semantic and small — use <header>, <main>, <footer> where appropriate when adding structure.
- No CSS framework detected; prefer inline or local CSS files placed in an `assets/` or `css/` directory if you add styles.

Developer workflows (explicit, reproducible)
- Preview locally (from repository root folder):

  - With Python (works on Windows):

    `python -m http.server 8000`

    Then open http://localhost:8000/About_Me_Webpage.html in your browser.

  - Or use an editor Live Server extension or `npx live-server .` if you prefer an npm tool.

- Debugging: use the browser DevTools (Elements, Console, Network) to locate layout/JS issues. There is no backend logging to consult.

Project-specific notes and gotchas
- A stray file with a non-standard name (looks like `const words = ['spray', 'limit', 'elite'.txt`) appears in the root. Treat such files as accidental — verify with the repo owner before deleting.
- Because there is no automated test or lint step, any change that affects rendering should be manually previewed in the browser and checked across common viewports.

Examples of safe, typical agent tasks
- Content update: change the page title in [About_Me_Webpage.html](About_Me_Webpage.html) and update the visible heading. Preview with the local server command above.
- Add an asset: create `assets/` then place images or `css/` there and reference them with relative URLs.

When not to change
- Do not assume new tooling (webpack, npm) should be introduced without user approval — this is a tiny static site and the simplest approach is preferred.

If you need more context
- Ask the user whether the stray file is intentional and whether they want a site structure (assets/, css/, js/) introduced.

Feedback
- If any of these points are incomplete or the repository contains hidden files not detected here, tell me which files to inspect and I will update this guidance.
