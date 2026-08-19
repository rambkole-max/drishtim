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

## Colour and type

⏳ **Open for the current redesign.** The old palette and type system were cleared 19 Aug 2026 to
give the drishtim-web redesign a clean slate — nothing here is a constraint until new choices are
made and written back into this file.

---

## Clear space and minimum size

- **Clear space:** the height of the hexagon aperture, on all four sides. Nothing enters it.
- **Minimum size:** 24px tall for the mark, 96px wide for the horizontal lockup.

## Don't

- Don't add effects — no shadow, no gradient, no glow, no outline
- Don't stretch. Scale proportionally only
- Don't rotate the mark. The waves always travel right

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
