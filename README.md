# drishtim.in

Website and brand assets for **Drishtim** — a founder-led creative studio in Latur, Maharashtra.
Reels, photography, paid campaigns and brand identity.

Single-page static site. No build step, no dependencies — open `index.html` and it runs.

---

## Contents

```
├── index.html                  the site
├── site.webmanifest            PWA manifest
├── robots.txt · sitemap.xml
└── brand/
    ├── BRAND.md                usage guide — read before using any asset
    ├── logo/                   marks, lockups, wordmark, mono cuts
    ├── favicon/                browser + PWA icons
    ├── social/                 avatar, OG image
    └── concepts-batch-1..3.html   the 30 explored directions, kept for reference
```

## The logo

**Broadcast lens.** An aperture that transmits — the lens is what we capture, the waves are what we
make sure people see. Built from *drishti* (दृष्टि), Sanskrit for sight.

Sizing, colour, clear space and the don'ts are in [`brand/BRAND.md`](brand/BRAND.md).

## Design

| | |
|---|---|
| Ground | Ink `#0A0A09` with a fixed artwork layer — lens rings, dot matrix, crop marks, drifting colour |
| Surfaces | Frosted glass panels, `backdrop-filter: blur(22px) saturate(150%)` |
| Accent | Flare `#FF4D1C`, with acid `#D8FF3E` reserved for live states |
| Type | Archivo (display) · Instrument Serif (italic voice) · Space Grotesk (UI) |
| Device | 35mm rebate rail down the left edge, tracking scroll position by frame |

Respects `prefers-reduced-motion`. Rail, custom cursor and blur effects drop below 900px.

---

## ⚠ Before deploying

1. **Export a raster OG image.** `brand/social/og-image.svg` must become a PNG or JPG — several
   platforms do not render SVG link previews.
2. **Outline the wordmark** for any print or third-party use. See BRAND.md.
3. **Check performance on a real mid-range Android.** Heavy `backdrop-filter` is the most expensive
   thing on the page. If it stutters, drop `--blur` from `22px` to `10px` in `:root`.

## Local preview

```bash
python3 -m http.server 8000
# http://localhost:8000
```

Root-relative paths (`/brand/...`) need a server — opening the file directly will not resolve icons.

## Deploy

Any static host. Netlify, Vercel, Cloudflare Pages and GitHub Pages all work with zero config —
point them at the repo root.

---

## Content accuracy

Copy on this site reflects decisions recorded in `DRISHTIM-SITE-CHANGE-BRIEF.md` and `FACTS.md`:
Instagram and Facebook only (no YouTube), rate card v2 (₹29,999 / ₹59,999 / ₹99,999 / ₹44,999),
Bharat Fine Dine at 4.5★ with 530+ reviews, September slots open.

`FACTS.md` is authoritative. If this site and that file disagree, the file wins — fix the site.

© 2026 Drishtim · Latur, Maharashtra
