# Poudre et Plume — AO3 Site Skin

**Poudre et Plume** is a soft, romantic site skin for [Archive of Our Own](https://archiveofourown.org) (AO3), built on a palette of dusty pink, slate blue, antique gold, and aged ivory. It is a full palette recolor of [Peacock Flare](https://github.com/intothisshadow/AO3-SiteSkin_PoudreetPlume) by intothisshadow, preserving the original structure and logic while replacing every colour with the Poudre & Plume scheme.

**Based on:** Peacock Flare by intothisshadow  
**Version:** 1.0.1  
**AO3 instructions:** 
**GitHub:** https://github.com/intothisshadow/AO3-SiteSkin_PoudreetPlume

---

## Screenshots

<details>
<summary>Desktop</summary>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop1.jpg" width="48%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop2.jpg" width="48%" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop3.jpg" width="48%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop4.jpg" width="48%" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop5.jpg" width="48%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_desktop6.jpg" width="48%" />
 </p>
</details>


<details>
<summary>Mobile</summary>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile1.jpg" width="30%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile2.jpg" width="30%" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile3.jpg" width="30%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile4.jpg" width="30%" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile5.jpg" width="30%" />
  &nbsp;
  <img src="https://raw.githubusercontent.com/intothisshadow/AO3-SiteSkin_PoudreetPlume/refs/heads/main/screenshots/screenshot_mobile6.jpg" width="30%" />
</p>
</details>



## File Structure

```
style_desktop.css  Desktop stylesheet
style_mobile.css   Mobile add-on (requires style.css as parent skin)
stylus_fonts.css   Optional: loads custom fonts via the Stylus browser extension
CHANGELOG.md       Version history
README.md          This file
```

---

## How to Install

### Fonts via Stylus (recommended)

AO3's skin system cannot load external fonts directly. For the best experience, install them on your system or load the fonts separately using *Stylus*, a free browser extension.

1. Install Stylus for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/styl-us/) or [Chrome](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne)
2. Click the Stylus icon → **Manage** → **Write new style**
3. Paste the contents of `stylus_fonts.css` into the code editor
4. Under **Applies to**, select **URLs on the domain** and enter `archiveofourown.org`
5. Name it (e.g. `Poudre et Plume Fonts`) and save

Without this step the skin falls back to Garamond / Book Antiqua / Palatino Linotype /Palatino, / Georgia / serif for body text, Monaco / Consolas / Courier  / Courier New / Courier / monospace for code elements — which still looks good, just not exactly as designed.

### Desktop skin (required)

1. Go to **Hi, user! → My Dashboard → Skins → Create Site Skin**
2. Paste the contents of `style_desktop.css` into the CSS field
3. Set **Media** to `all`
4. Save — do **not** activate it directly if you are also using the mobile add-on

### Mobile add-on (recommended)

1. Go to **Hi, user! → My Dashboard → Skins → Create Site Skin**
2. Paste the contents of `style_mobile.css` into the CSS field
3. Set **Media** to all of:
   - `handheld`
   - `only screen and (max-width: 62em)`
   - `only screen and (max-width: 42em)`
4. Under **Parent Skin**, select the desktop skin you created above
5. Save and **activate this skin** — AO3 will automatically apply the parent skin alongside it. You only ever activate the child.

### Desktop only (no mobile add-on)

If you don't want the mobile add-on, activate the desktop skin directly instead.

### Icon replacements

The Zerafina icon replacement set is built into `style_desktop.css` as Section 24 — no separate skin needed. The colours have been adapted to match the Poudre et Plume palette. Based on [ZerafinaCSS's Replace the AO3 Icons 2.0](https://github.com/ZerafinaCSS/Replace-the-AO3-Icons-2.0).

To remove the icon replacements, delete Section 24 from `style_desktop.css`.

---

## Customising the Palette

All colours are defined as CSS variables in the `:root` block at the top of `style.css` (Section 0). To create a new colour scheme, **only edit that block** — all variable usages throughout the file will update automatically.

The variables cover:

- **Solid colours** — page background, card levels, accent tones (blush, mauve, rose, slate, gold, sage, ivory)
- **Alpha variants** — semi-transparent versions of rose, mauve, blush, and slate for overlays, shadows, and borders
- **Font size** — `--desktop-base` controls the base `rem` size for the entire page

---

## Stylesheet Structure

The desktop stylesheet is divided into 24 sections:

| # | Section |
|---|---------|
| 0 | Root variables |
| 1 | Global / reset |
| 2 | Typography |
| 3 | Links |
| 4 | Header & navigation |
| 5 | Greeting / user menu |
| 6 | Sidebar & dashboard |
| 7 | Buttons & actions |
| 8 | Forms & inputs |
| 9 | Tag system |
| 10 | Work blurb cards |
| 11 | Work page |
| 12 | Comments |
| 13 | Inbox |
| 14 | Dropdowns & listboxes |
| 15 | Notices & alerts |
| 16 | Front page (splash) |
| 17 | Index pages (media, fandoms, collections) |
| 18 | Profile & stats pages |
| 19 | Reading history |
| 20 | Miscellaneous (scrollbar, selection, pre) |
| 21 | System (sessions, skins, docs, FAQ, TOS, proxy) |
| 22 | AO3 default elements |
| 23 | Footer |
| 24 | Replace the AO3 icons (Zerafina) |

The mobile stylesheet is divided into `@media` blocks matching AO3's own breakpoints (≤62em shared/tablet, ≤42em portrait phone, ≤30em very small phones), each with internal comments grouping rules by type.

---

## Fonts

Three custom fonts are used. Because AO3 site skins cannot load external fonts, install the fonts in your system or use the included `stylus_fonts.css` with the Stylus browser extension (see install instructions above). Without this step the skin falls back to Garamond / Book Antiqua / Palatino Linotype /Palatino, / Georgia / serif for body text, Monaco / Consolas / Courier  / Courier New / Courier / monospace for code elements — which still looks good, just not exactly as designed.

- **EB Garamond** (body text) — https://fonts.google.com/specimen/EB+Garamond
- **Cormorant Garamond** (headers / site title) — https://fonts.google.com/specimen/Cormorant+Garamond
- **Source Code Pro** (code & monospace elements) — https://fonts.google.com/specimen/Source+Code+Pro

---

## Credits

- Icon replacements based on [ZerafinaCSS Replace the AO3 Icons 2.0](https://github.com/ZerafinaCSS/Replace-the-AO3-Icons-2.0), included in Section 24 of the desktop stylesheet

---

## Version

| **Version** | **Date**     | **Description**                 |
| ----------- | ------------ | ------------------------------- |
| **1.0.1**   | May 15, 2026 | Restored missing css            |
| **1.0.0**   | May 4, 2026  | Initial release + mobile add-on |

The changelog documents significant changes only — new features, architectural decisions, and notable bug fixes. Individual CSS tweaks, rule refinements, and minor mobile adjustments are not logged.
