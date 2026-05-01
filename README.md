# iTunes.css

A CSS library that recreates the classic iTunes desktop interface aesthetic. Based on the older iTunes page design, providing ready-to-use components styled after Apple's iconic media player UI.

> Feel free to send a PR — contributions are always welcome!

---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Components](#components)
  - [Buttons](#buttons)
  - [Sub-Container](#sub-container)
  - [Navbar (WIP)](#navbar-wip)
- [Color System](#color-system)
- [Typography](#typography)
- [Building from Source](#building-from-source)
- [Contributing](#contributing)
- [License](#license)

---

## Installation

**Option 1 — Use the prebuilt CSS directly**

Copy `out/source.css` (or the minified `out/source.min.css`) into your project and link it in your HTML:

```html
<link rel="stylesheet" href="source.css" />
```

**Option 2 — Build from source (SCSS)**

See [Building from Source](#building-from-source) below.

---

## Usage

After including the stylesheet, apply iTunes-style classes to your HTML elements. For example:

```html
<!-- Primary button -->
<button class="btn primary">Buy</button>

<!-- Sub-container -->
<div class="sc">
  <div class="header"><span>My Playlist</span></div>
  <div class="section">
    <span class="header">Song Title</span>
    <span class="text">Artist Name</span>
  </div>
</div>
```

---

## Components

### Buttons

Buttons use the base class `btn` combined with one of the variant classes: `primary`, `secondary`, `tertiary`, or `link`.

| Class | Description |
|-------|-------------|
| `btn primary` | Blue gradient button with rounded corners. Font size `15px`. |
| `btn secondary` | Gray gradient pill button. Font size `13px`. |
| `btn tertiary` | Dark gradient pill button (caption style). Font size `11px`. |
| `btn link` | Inline link-style button with a `›` arrow appended. |

**HTML example:**

```html
<button class="btn primary">Get iTunes</button>
<button class="btn secondary">Learn More</button>
<button class="btn tertiary">Details</button>
<a class="btn link">View all</a>
```

All button text uses the **Sansation Light** font (weight 300) with white text.

---

### Sub-Container

A card-like panel with a header bar and a content section. Apply the class `sc` to a wrapping `<div>`.

**Structure:**

```html
<div class="sc">
  <!-- Header bar -->
  <div class="header">
    <span>Section Title</span>
  </div>

  <!-- Content section -->
  <div class="section">
    <span class="header">Row Header</span>
    <span class="text">Row body text</span>
    <hr />
    <span class="header">Another Row</span>
    <span class="text">More details</span>
  </div>
</div>
```

| Element | Description |
|---------|-------------|
| `div.sc > div.header` | Gradient header bar with rounded top corners. Uses **IBM Plex Mono** bold 12px. |
| `div.sc > div.section` | White content area with border, shadow, and rounded bottom corners. |
| `div.sc > div.section span.header` | Bold 12px label inside a section row. |
| `div.sc > div.section span.text` | Regular 10px body text inside a section row. |
| `div.sc > div.section hr` | Thin divider line spanning 95% of the section width. |

---

### Navbar (WIP)

> ⚠️ The navbar component is currently broken and is **not included** in the compiled output. It is available as a reference in `src/features/navbar.scss`.

The navbar is a pill-shaped horizontal navigation bar with arrow controls and selectable items. It uses a dark inner bar with white text and highlights selected items with a gradient background.

---

## Color System

Colors are defined as SCSS variables in `src/colors/` and exported through `src/colors.scss`.

### Text colors (`src/colors/text.scss`)

| Variable | Value | Usage |
|----------|-------|-------|
| `$primary` | `#000000` | Default body text |
| `$secondary` | `#41524C` | Subdued / secondary text |
| `$secondary-light` | `#9B8C80` | Lighter secondary (e.g., nav bar text) |
| `$caption` / `$tertiary` | `#FFFFFF` | White text (buttons, dark backgrounds) |
| `$link` | `#028ACA` | Link color |

### Button colors (`src/colors/buttons.scss`)

| Variable | Value | Usage |
|----------|-------|-------|
| `$primary` | Blue gradient | Primary button background |
| `$secondary` | Gray gradient | Secondary button background |
| `$tertiary` / `$caption` | Dark gradient | Tertiary button background |
| `$secondary-light` | `#858587` | Secondary button overlay tint |
| `$textShadow` | `#072652` | Button text shadow |
| `$link` | `text.$link` | Link button color |

### Sub-container colors (`src/colors/sub-container.scss`)

| Variable | Value | Usage |
|----------|-------|-------|
| `$header-primary` | Light gray gradient | Header bar background |
| `$header-text` | `#41524C` | Header bar text |
| `$section-primary` | `#FFFFFF` | Section background |
| `$section-header` | `#33393E` | Section row header text |
| `$section-text` | `#000000` | Section body text |
| `$section-br` | `#D9D9D9` | Section divider (`<hr>`) color |

---

## Typography

iTunes.css uses two Google Fonts which are imported automatically:

| Font | Usage |
|------|-------|
| **Sansation** (Light 300, Regular 400, Bold 700) | Button labels, navbar text |
| **IBM Plex Mono** (all weights) | Sub-container headers and body text |

Both fonts are loaded from Google Fonts CDN via `@import` in the stylesheet — no additional setup is required.

---

## Building from Source

**Prerequisites:** Node.js and npm.

```bash
# Install dependencies
npm install

# Build (produces source.css and source.min.css in out/)
npm run build

# Watch mode (auto-recompiles on change)
npm run watch
```

Output files are written to the `out/` directory:

| File | Description |
|------|-------------|
| `out/source.css` | Full unminified CSS with source map |
| `out/source.min.css` | Minified CSS for production use |

**Project structure:**

```
src/
├── app.scss            # Entry point — forwards all modules
├── base.scss           # Global body/html reset
├── imports.scss        # Google Fonts imports
├── colors.scss         # Forwards all color partials
├── colors/
│   ├── text.scss       # Text color variables
│   ├── buttons.scss    # Button color variables
│   ├── sub-container.scss  # Sub-container color variables
│   └── secondary-nav.scss  # (Secondary) nav color variables
└── features/
    ├── buttons.scss    # Button component styles
    ├── subcontainer.scss   # Sub-container component styles
    └── navbar.scss     # Navbar component (WIP, not compiled)
```

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute.

---

## License

[ISC](LICENSE)
