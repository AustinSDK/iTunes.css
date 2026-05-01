# Contributing to iTunes.css

Thanks for taking the time to contribute! Here's how to get started.

---

## Getting Started

1. **Fork** the repository and clone your fork.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run the watch mode while working on styles:
   ```bash
   npm run watch
   ```
4. Make your changes inside the `src/` directory.
5. Build the output files before committing:
   ```bash
   npm run build
   ```
6. Commit both your source changes **and** the rebuilt `out/` files.

---

## Project Structure

```
src/
├── app.scss            # Entry point — forwards all modules
├── base.scss           # Global body/html reset
├── imports.scss        # Google Fonts imports
├── colors.scss         # Forwards all color partials
├── colors/             # Color variable files
└── features/           # Component style files
out/
├── source.css          # Compiled CSS (commit this)
└── source.min.css      # Minified CSS (commit this)
```

---

## Guidelines

- **SCSS only** — edit source files in `src/`. Do not edit `out/` files by hand.
- **Follow existing naming conventions** — color variables live in `src/colors/`, component styles in `src/features/`.
- **Forward new modules** — if you add a new feature file, forward it from `src/app.scss`; if you add a new color file, forward it from `src/colors.scss`.
- **Keep it iTunes-accurate** — styling choices should be consistent with the classic iTunes desktop UI aesthetic.
- **Run the build** — always run `npm run build` and include the updated `out/source.css` and `out/source.min.css` in your PR.

---

## Reporting Bugs / Requesting Features

Open an issue at [GitHub Issues](https://github.com/AustinSDK/iTunes.css/issues) with as much detail as possible.

---

## Pull Requests

- Use a descriptive title and describe what your PR changes.
- If you're fixing a bug, reference the issue number (e.g., `Fixes #12`).
- If you're adding a new component, include a brief HTML usage example in the PR description.
