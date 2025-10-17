# YouCore - Streetwear and Footwear Brand Website

**YouCore** is a modern, responsive frontend for a streetwear and footwear brand. It is a static, component-driven site built with semantic HTML, modular SCSS, JavaScript, and Handlebars templates — bundled with Webpack for a fast development workflow and optimized production builds.

Live demo: https://abhayshah1810.github.io/hackathonDeploy/

---

## 1) What is this website

YouCore is a prototype storefront/brand landing site focused on clean, modern streetwear aesthetics. It demonstrates:
- Component-based structure (re-usable header, footer, product cards, hero, etc.)
- Responsive layouts for mobile, tablet and desktop
- Simple client-side interactions (menus, sliders, light UI behaviors)
- Fast dev feedback with a local dev server and Hot Module Replacement (HMR) via Webpack

This project is intended as a frontend demo — not a full e-commerce backend.

---

## 2) How to run (copy & run locally)

Prerequisites
- Node.js (v14+ recommended) and npm on macOS
- Git (to clone the repo)

Clone, install and run:
```bash
git clone https://github.com/AbhayShah1810/hackathonSubmission.git
cd hackathonSubmission
npm install
npm run start      # starts dev server, usually at http://localhost:8080
```

Build for production:
```bash
npm run build      # outputs optimized files into the dist/ (or configured) folder
# optionally preview production build locally:
npx serve dist     # install `serve` globally or use npx for a quick static server
```

If your dev server uses a different port, the terminal output will show the correct URL. On macOS, use the Terminal app included with the OS.

Troubleshooting
- If npm install fails: delete node_modules and package-lock.json, then run `npm install` again.
- If Node version is incompatible: use nvm to install/select a supported Node version:
  ```bash
  nvm install 18
  nvm use 18
  ```
- If port 8080 is in use, pass an environment variable or edit the dev script in package.json.

---

## 3) Detailed explanation of the tech used

This section explains each major tool and why it’s used.

HTML
- Semantic, accessible markup for pages and components.
- Templates (Handlebars) output consistent HTML structure across pages and components.

SCSS (Sass)
- SCSS provides variables, nesting, mixins, and partials for modular, maintainable styles.
- Typical structure:
  - _variables.scss — colors, breakpoints, spacing tokens
  - _mixins.scss — reusable style patterns
  - components/ — per-component style partials
  - main.scss — imports partials and compiles to a single CSS file
- Compiled and bundled by Webpack (sass-loader → css-loader → style-loader or extracted CSS in production).

JavaScript (ES modules)
- Organizes behavior into small modules (menu toggles, sliders, small UI utilities).
- Bundled by Webpack so you can use modern JS (imports/exports).
- Keeps interaction unobtrusive — purely client-side, no backend required for the demo.

Handlebars
- Templating engine used to create reusable HTML templates and partials (headers, footers, product cards).
- Enables consistent markup and easier content updates without repeating HTML.

Webpack
- Bundles JS, compiles SCSS, processes images/fonts, and generates the final production output.
- Dev server with HMR provides fast feedback when editing code.
- Production build enables optimizations: minification, code-splitting, asset hashing for cache busting (if configured).

NPM scripts
- Shortcuts for common tasks:
  - npm run start — run the dev server
  - npm run build — produce production assets
  - (optional) npm run deploy — push to GitHub Pages if configured

Assets and optimization
- Images and fonts are handled by Webpack loaders or the asset modules API to copy/optimize into the build.
- Production pipeline should minimize CSS/JS and optimize images to improve load times.

Project architecture (typical)
- src/
  - index.hbs / pages/ — Handlebars templates
  - assets/ — images, fonts
  - styles/ — SCSS partials and main.scss
  - scripts/ — JS modules
- public/ — static files copied to the build
- webpack.config.js — bundling rules and dev server config
- package.json — dependencies and scripts

How to customize
- Colors: change SCSS variables in _variables.scss.
- Components: edit or add Handlebars partials and their SCSS and JS counterparts.
- Add pages by creating new Handlebars templates and wiring them into the build.

Deployment
- The repository includes a GitHub Pages demo. You can deploy builds by pushing the production output to gh-pages or using a CI/CD pipeline that serves the dist/ folder.


# Contributing to YouCore

Thanks for your interest in improving this project. This document gives quick, practical steps for contributing.

## Quick start — run locally
1. Clone the repo:
   ```bash
   git clone https://github.com/AbhayShah1810/hackathonSubmission.git
   cd hackathonSubmission
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start dev server:
   ```bash
   npm run start
   ```
4. Build production bundle:
   ```bash
   npm run build
   ```

## Report bugs & request features
- Open an issue describing steps to reproduce, expected vs actual behavior, and environment (Node/npm versions).
- Attach screenshots or minimal reproduction where helpful.

## Make changes (recommended workflow)
1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feat/short-description
   ```
3. Make changes, keep commits small and focused.
4. Run the dev server and manual checks.
5. Push branch and open a Pull Request against the main branch with a clear description and screenshots if applicable.

## Code style & tests
- Prefer semantic HTML, modular SCSS, and small ES modules.
- Run any available linters/formatters before committing (project may include ESLint/Prettier).
- Add tests for new/changed logic where applicable.

## Commit message guideline
- Use present-tense, short summary, e.g.:
  - feat: add product carousel
  - fix: correct cart item count update
  - docs: update README

## Review & merge
- PRs should include a concise description of changes and any verification steps.
- Maintain backwards-compatible changes where possible.
- Squash/fixup commits when requested by reviewers.

## License
This project is MIT licensed. By contributing you agree your contributions will be licensed under the project license.


hackathonSubmisson/
├─ .gitignore
├─ README.md
├─ CONTRIBUTING.md
├─ package.json
├─ webpack.config.js
├─ index.html
├─ login.html
├─ men.html
├─ women.html
├─ category.html
├─ cart.html
├─ checkout.html
├─ assets/
│  ├─ css/
│  │  ├─ libs.bundle.css
│  │  └─ theme.bundle.css
│  ├─ js/
│  │  ├─ vendor.bundle.js
│  │  └─ theme.bundle.js
│  ├─ images/
│  │  ├─ banners/
│  │  ├─ categories/
│  │  ├─ logos/
│  │  └─ favicon/
│  └─ fonts/
├─ src/                # (if present — source files for Webpack)
│  ├─ templates/       # Handlebars templates (.hbs)
│  ├─ styles/          # SCSS source files
│  └─ scripts/         # JS source files
├─ public/             # static assets copied to build (optional)
└─ dist/               # production output (generated by build)
