# AGENTS.md

## Repository Overview & Verification of Configuration Files

A complete inspection of the repository was performed to verify all build and environment configurations:
- `package.json` / `package-lock.json` / `yarn.lock` / `pnpm-lock.yaml`: **None exist.**
- `requirements.txt` / `pyproject.toml` / `Pipfile` / `setup.py`: **None exist.**
- Existing rules files (`.cursorrules`, `.cursor/rules`, `.windsurfrules`, `.clinerules`, `.copilot/rules`, `CLAUDE.md`, etc.): **None exist.**
- CI/CD configurations (`.github/workflows/`): **None exist.**
- Tooling / Linter / Formatter configs (`.eslintrc`, `.prettierrc`, `biome.json`, `stylelint`, etc.): **None exist.**
- Git Remote: `https://github.com/Zirins/bensonlin.github.io.git` (GitHub Pages user repository, tracked on branch `main`).

---

## Commands (Run, Test, Lint)

### 1. Run / Dev Commands
- **Verified in repo:** **None.**
- **Details:** There is no package manager, bundler, or local dev server configured in this repository.
- **Execution notes:** As a static website, the code can be served using standard static HTTP servers (e.g., `python -m http.server` or `npx serve`) or by opening `index.html` directly in a browser, but no specific run command is configured, automated, or defined in project files.

### 2. Test Commands
- **Verified in repo:** **None.**
- **Details:** There are no test frameworks (Jest, Vitest, Playwright, Cypress, etc.), test files, or test execution scripts in this repository.
- *Note:* Text inside `index.html` mentions proof points for featured projects (e.g., "81 backend tests", "49 frontend tests" for DropForge), but those tests belong to external project repositories, not this portfolio site.

### 3. Lint / Format Commands
- **Verified in repo:** **None.**
- **Details:** No HTML, CSS, or JavaScript linters, formatters, or validators are configured or installed in this repository.

---

## Stack & Architecture

- **Platform:** GitHub Pages static site (`bensonlin.github.io`).
- **Domain Configuration:** Custom domain `bensonlin.me` configured via root `CNAME`.
- **Technologies:**
  - **HTML5:** Semantic document structure in `index.html` (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<figure>`, `<footer>`).
  - **CSS3:** Inlined in `index.html` within a `<style>` block. Uses CSS custom properties (`--cream`, `--navy`, `--burgundy`, etc.), CSS Grid, Flexbox, responsive fluid typography (`clamp()`), and media queries.
  - **JavaScript:** Vanilla ECMAScript inlined in `index.html` within a single `<script>` block before `</body>`. Manages mobile navigation toggle, scroll-aware navigation styling, and `IntersectionObserver` reveal animations.
  - **Third-Party CDN Dependencies:** Google Fonts preconnect and stylesheet link in `<head>` loading `Cormorant Garamond` and `DM Sans`.
  - **Build Pipeline:** None. No compilation, transpilation, or bundling step is used.

---

## Folder & File Conventions

All active files are placed in a flat structure directly at the repository root:

- `index.html` — The entire website (markup, embedded CSS styles, and embedded JavaScript).
- `CNAME` — GitHub Pages domain routing (`bensonlin.me`).
- `Benson_Lin_Resume.pdf` — Resume asset linked directly in the navigation bar, hero actions, and contact section.
- `headshot.jpg` — Portrait image displayed in the "About" section.
- `dropforge.png` — Screenshot preview asset for Project 01 (DropForge).
- `orbit.png` — Screenshot preview asset for Project 02 (Orbit).
- `vigil.png` — Screenshot preview asset for Project 03 (Vigil).
- `huddle_chat_png.png` — Screenshot asset present in root (retained from earlier commits; currently not linked in `index.html`).
- `.agents/` — Directory present in the repository root (currently empty).

**Conventions:**
- Assets are referenced using flat root relative paths (e.g., `src="headshot.jpg"`, `href="./Benson_Lin_Resume.pdf"`). There are no subfolders like `src/`, `assets/`, `images/`, `css/`, or `js/`.

---

## Hard Constraints Stated in Repo

1. **Browser-Ready Root `index.html`:** The site is hosted directly by GitHub Pages from repository root on `main`. `index.html` must remain fully executable by web browsers without requiring a compilation step, unless an explicit build and deploy pipeline is added.
2. **Custom Domain Binding:** The `CNAME` file must be preserved with `bensonlin.me` to ensure custom domain routing remains active on GitHub Pages.
3. **In-Code Pending TODO Constraints:**
   - Line 12: `<!-- TODO: Add <meta property="og:image"> after an approved social preview is provided. -->`
   - Line 13: `<!-- TODO: Add <link rel="canonical"> after the production portfolio URL is confirmed. -->`
   - Line 14: `<!-- TODO: Add a favicon when an approved icon asset is available. -->`
4. **Accessibility Constraints Defined in Code:**
   - Skip link (`<a class="skip-link" href="#main-content">Skip to content</a>`) must remain the first focusable element inside `<body>`.
   - Motion accessibility: `@media (prefers-reduced-motion: reduce)` must be respected (disables smooth scrolling, sets transition durations to near zero, and forces `.fade-section` elements to be visible).
   - Focus states: `:focus-visible` outline (`3px solid var(--burgundy); outline-offset: 4px;`) must be maintained on interactive elements.
   - Touch targets: Buttons and interactive elements maintain explicit minimum heights (`40px` for small buttons, `44px` for primary/secondary buttons and text links).
   - Layout responsiveness: Breakpoints are set at `920px`, `720px`, and `520px`, with a minimum body width of `320px`.

---

## Items That Could Not Be Confirmed

1. **Run, Test, and Lint Commands:** No command-line scripts or task runner commands exist anywhere in the repository configuration.
2. **Package / Dependency Management:** No dependency manifest (`package.json`, `requirements.txt`, `pyproject.toml`) exists.
3. **Automated Testing:** No test files, test fixtures, or test configurations exist for this repository.
4. **Code Quality / Linting Rules:** No linting rules or code formatting rules (ESLint, Stylelint, HTMLHint, Prettier) are defined.
5. **CI / CD Pipeline:** No GitHub Actions workflows or automated deployment scripts exist in the repository; deployment is unconfirmed beyond GitHub's default Pages branch publishing.
6. **Purpose of `.agents/` Directory:** The `.agents/` directory is present in the repository root but completely empty; no configuration or instructions exist within it.
7. **Usage of `huddle_chat_png.png`:** `huddle_chat_png.png` exists in the repository root but is not currently referenced in `index.html` (the Huddle Chat project entry in the "More Projects" section has text only and no `<img>` element).
