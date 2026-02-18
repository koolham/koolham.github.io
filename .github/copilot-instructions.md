# koolham.github.io – Copilot Instructions

Personal developer portfolio for Landex Development. Static HTML/CSS site deployed via GitHub Pages to `www.landex.dev` (see `CNAME`).

## Stack

No build tools, no JavaScript, no package manager. Edit `index.html` and `styles.css` directly and push — GitHub Pages deploys automatically.

## Architecture

Single page (`index.html`) with three visual sections inside `.container`:

1. **`.bio`** — About/contact card. Uses `position: relative` to anchor two absolutely-positioned children: `.links` (top-right corner) and `.donate-button` (bottom-right corner).
2. **`.games`** — List of projects. Each entry is a `.game-item` flex row: a fixed-size `.game-image` on the left, `.game-info` text on the right. Alternating item background colours via `.game-item:nth-child(2)`.
3. **`.tech-stack`** — Flex row of `.tech-logo` images sized with `clamp()`.

The `<header>` is outside `.container` and holds the full-bleed banner logo (`.site-logo`) via a nested `.header-inner > .header-flex` structure.

## Key Conventions

- Max content width is `min(90vw, 1024px)` applied consistently on `header`, `.header-inner`, and `.container`.
- Two responsive breakpoints: `@media (max-width: 900px)` (shrinks images, removes header padding) and `@media (max-width: 600px)` (stacks `.game-item` vertically, collapses links).
- All card surfaces share the same shadow/radius pattern: `border-radius: 12px; box-shadow: 0 6px 12px rgba(0,0,0,0.1)`.
- Images live in `images/`; logos are PNG files referenced by filename in `index.html`.
- Use HTML `class` attribute (not `className`) — the footer currently has a `className` typo that has no visual effect but should be corrected to `class` when touched.
