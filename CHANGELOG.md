# Changelog

The changelog documents significant changes only — new features, architectural decisions, and notable bug fixes. Individual CSS tweaks, rule refinements, and minor mobile adjustments are not logged.

## [1.0.1] - 2026-05-15 (current)

- Four CSS properties had been dropped at some point during cleaning up. Restored them.
  - **`hr`** — missing `border: 0 !important` 
  - **`#header`** — missing `background: linear-gradient(90deg, #A9B4AB 0%, #D7979F 50%, #E8D9CB 100%)` (the header gradient)
  - **`#header .primary.navigation a`** — missing `background: none`, `border: none`, `border-bottom: none` (the resets that stop nav links inheriting button chrome)
  - **`fieldset`** — missing the `background` gradient, `border`, and `border-radius: 32px` 

## [1.0.0] - 2026-05-04

### 🎨 Visual & Color Palette

- Named the palette **Poudre & Plume**: antique ivory backgrounds, muted mauve/rose accents, slate sage and rococo teal mid-tones, warm umber text
- Gradient flow: Header → Muted Mauve → Slate Sage; Navigation → Slate Sage → Slate Blue; Sidebar → Slate Sage → Slate Blue; Footer → Slate Blue → Deep Walnut
- All coloured tag pills use light text (white/near-white) to ensure legibility on coloured backgrounds; this is enforced globally across the tag system
- Rating icons recoloured to match palette: General (#71A7B0 teal), Teen (#6890A0 slate), Mature (#D7979F rose), Explicit (#D87884 deep rose)
- Category icons: F/F → Deep Rose, F/M → Rococo Teal, Gen → Sage, M/M → Slate, Multi → conic-gradient quadrant of all four, Other → Warm Parchment
- Warning and completion icons follow the same palette mapping (rose for warnings/incomplete, sage for complete)
- Bookmark icons: Rec → Antique Gold, Public → Rococo Teal, Private → Black, Hidden → Deep Rose
- `<hr>` uses a rainbow `border-image` gradient (sage → rose → gold → teal) — safe because `<hr>` has no `border-radius`

### 🖋️ Typography & Fonts

- Body font: **EB Garamond** (with Garamond, Book Antiqua, Palatino, Georgia as fallbacks); weight 500
- Header font: **Cormorant Garamond** (semibold/bold, applied via `.heading` selector and structural heading rules)
- Fonts loaded via Stylus or system install — AO3 strips `@import`, so the `@import` URL is preserved as a comment for reference
- Base font size set via `--desktop-base: 20px` on `:root`; mobile handled separately in `style_mobile.css`
- Heading scale scoped to `#main` and `#content` only, to avoid inadvertently resizing AO3's structural headings outside those containers

### 🏷️ Tag System (Custom Pill Styling)

- All tag categories (fandom, character, relationship, freeform, additional) styled as rounded pills with per-category background colours
- Fandom tags → Petal Pink (`--clr-rose-soft`)
- Character tags → Slate Blue (`--clr-ocean`)
- Relationship tags → Antique Gold (`--clr-gold`)
- Freeform tags → Dusty Celadon (`--clr-sage`)
- **Architectural decision:** `border-image` is explicitly not used on any element with `border-radius`, to avoid the browser rendering conflict where `border-image` overrides `border-radius`. Tag pills and cards use solid or rgba `border` instead.

### 🏗️ Layout & UI Enhancements

- Work blurb cards, sidebar, and nested fieldsets use the three-tier background system: `--clr-bg` (page) → `--clr-card` (card) → `--clr-card-nested` (nested)
- Zerafina's "Replace the AO3 Icons 2.0" icon set integrated (RSS, kudos heart, lock, rating, category, warning, completion, bookmark icons)
- Kudos heart icon rebuilt via `::before` pseudo-element with CSS `filter` hue-rotation to match rococo teal, replacing AO3's default greyscale image
- Lock icon (`lockblue.png`) replaced via `content: url()` with a filter chain for palette-matched recolour

### 🛠️ Technical Details

- Working file renamed from `style.css` to `style_desktop.css`; mobile styles live in `style_mobile.css`
- All CSS custom properties (palette, alpha variants, font size) centralised in section `0. ROOT VARIABLES` — the only section that needs editing for a recolor
- Alpha token families provided for teal, rose, abyss (warm brown), emerald (sage), and background, covering opacity steps from 6% to 85%
- 24-section table of contents
- `overflow-x: hidden` on `body` suppresses horizontal scroll caused by AO3's full-width structural elements
- `text-rendering: optimizeLegibility` and font-smoothing applied globally via `body *`
