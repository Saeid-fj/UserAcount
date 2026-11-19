# Responsive Product Grid

A mobile-first product listing built with semantic HTML and modular, token-driven CSS. No build step or dependencies.

## Getting started

Open `index.html` in a browser, or serve the folder locally:

```bash
npx serve .
```

## Project structure

```
.
├── index.html
├── assets/
│   └── fonts/
│       └── vazirmatn/      # Vazirmatn variable font + OFL license
└── styles/
    ├── index.css           # Entry point: imports the files below, in order
    ├── fonts.css           # @font-face for Vazirmatn
    ├── tokens.css          # Design tokens (colors, spacing, type, etc.)
    ├── reset.css           # Browser normalisation
    ├── base.css            # Element defaults and utilities
    ├── layout.css          # Container and product grid
    └── components.css      # Page header, product card, badge
```

## Conventions

- **BEM naming**: `.block`, `.block__element`, `.block--modifier` (e.g. `.product-card__title`, `.badge--danger`).
- **Design tokens**: all colors, spacing, radii and type sizes live in `styles/tokens.css`. Components never hard-code values.
- **Mobile first**: base styles target small screens; `min-width` media queries add columns at `768px` (tablet) and `1024px` (desktop).
- **One section per component**: new components go in `styles/components.css` under their own commented header.

## Typography

The project uses [Vazirmatn](https://rastikerdar.github.io/vazirmatn/) (v33.003), self-hosted as a single variable-weight `woff2` file (weights 100–900). It is preloaded in `index.html`, declared in `styles/fonts.css` with `font-display: swap`, and falls back to the system UI font. Vazirmatn is free under the SIL Open Font License 1.1; see `assets/fonts/vazirmatn/OFL.txt`.

## Accessibility

- Semantic landmarks (`main`, `header`, `section`) and a logical heading order (`h1` → `h2` → `h3`)
- Products are marked up as a list, so screen readers announce how many there are
- Descriptive `alt` text on every image
- Respects `prefers-reduced-motion`
