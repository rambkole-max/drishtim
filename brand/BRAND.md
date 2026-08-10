# Drishtim — brand guide

**Concept: broadcast lens.** An aperture that transmits. The lens on the left is what we capture;
the waves on the right are what we make sure people see. Both halves of the studio in one mark.

Built from *drishti* (दृष्टि) — Sanskrit for sight.

---

## The mark

| File | Use |
|---|---|
| `logo/mark.svg` | Primary. On ink or any dark ground |
| `logo/mark-on-light.svg` | Primary. On paper or any light ground |
| `logo/mark-compact.svg` | Below ~48px. One wave instead of two, heavier strokes |
| `logo/mark-mono-dark.svg` | Single colour, dark. Print, stamps, embroidery |
| `logo/mark-mono-white.svg` | Single colour, light. Reversed out of photography |

**Which one at which size**

- Above 48px — `mark.svg`, both waves
- 24–48px — `mark-compact.svg`, one wave
- Below 24px — `favicon/favicon-16.svg`, solid lens, no outline

The two-wave version collapses below about 40px. Don't force it; that's what the compact cut is for.

## Lockups

| File | Use |
|---|---|
| `logo/lockup-horizontal.svg` | Default. Website header, email signature, letterhead |
| `logo/lockup-horizontal-on-light.svg` | Same, light grounds |
| `logo/lockup-stacked.svg` | Square-ish spaces. Includes `LATUR · INDIA` |
| `logo/wordmark.svg` | Text alone, where the mark already appears nearby |

## Favicon and app icons

| File | Use |
|---|---|
| `favicon/favicon.svg` | Browser tab, any size |
| `favicon/favicon-16.svg` | Fallback for very small raster export |
| `favicon/maskable.svg` | Android/PWA. Safe zone respected — art scaled to 62% |

## Social

| File | Use |
|---|---|
| `social/avatar.svg` | Instagram, LinkedIn, Facebook profile. 512×512, full bleed |
| `social/og-image.svg` | Link previews. 1200×630 |

---

## Colour

| Name | Hex | Use |
|---|---|---|
| Ink | `#0A0A09` | Primary ground |
| Paper | `#EDEBE5` | Light ground, and the mark's linework on ink |
| Flare | `#FF4D1C` | The aperture. Accent, one per view |
| Acid | `#D8FF3E` | Live states only — active nav, hover, current step |
| Deep | `#0E4A43` | Secondary panels, rarely |

**Rule:** flare is the aperture and the accent. It never becomes a background for large areas of text.
Acid only ever marks something that is *currently happening*.

## Type

| Role | Face | Setting |
|---|---|---|
| Display | **Archivo** | Variable, `wdth` 106–120, `wght` 800–900, tracking −0.03 to −0.045em, uppercase |
| Voice | **Instrument Serif** | Italic only, for single emphasised words inside display lines |
| Body / UI | **Space Grotesk** | 400 and 500. Labels at 11px, tracking 0.16–0.2em, uppercase |

Archivo replaced Fraunces in August 2026. Fraunces is retired across the studio.

---

## Clear space and minimum size

- **Clear space:** the height of the hexagon aperture, on all four sides. Nothing enters it.
- **Minimum size:** 24px tall for the mark, 96px wide for the horizontal lockup.

## Don't

- Don't recolour the aperture. It is always flare, or mono in single-colour applications
- Don't add effects — no shadow, no gradient, no glow, no outline
- Don't stretch. Scale proportionally only
- Don't rotate the mark. The waves always travel right
- Don't place the colour mark on a busy photograph — use `mark-mono-white.svg`
- Don't recreate the wordmark in another typeface

---

## ⚠ Before any print or third-party use

The lockup and wordmark SVGs reference **Archivo** by `font-family`. They render correctly on the web,
where the site loads Archivo from Google Fonts — but on a machine without Archivo installed they fall
back to Helvetica or Arial and the wordmark will be wrong.

**Convert the text to outlines** in Figma, Illustrator or Inkscape before sending a logo to a printer,
a signboard maker, or any third party. Save those as `lockup-horizontal-outlined.svg`.

The mark, favicons and avatar are pure geometry with no text, so they are safe everywhere as they are.

## Raster exports still needed

Everything here is SVG. Produce PNGs at these sizes when needed — Figma or `svgexport` will do it:

- `favicon` → 16, 32, 48, 180 (apple-touch), 192, 512
- `avatar` → 512×512 PNG for Instagram and LinkedIn upload
- `og-image` → 1200×630 **PNG or JPG** — several platforms do not render SVG link previews

That last one matters. Ship a raster OG image before launch.
