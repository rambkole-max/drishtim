# drishtim.in

Website and brand assets for **Drishtim** — a founder-led creative studio in Latur, Maharashtra.
Reels, photography, paid campaigns and brand identity.

Single-page static site. No build step to *run* it — open `index.html` and it works. One vendored
script (`vendor/motion.min.js`) is pre-built and checked in, so there's still nothing to install.

---

## Contents

```
├── index.html                  the site
├── site.webmanifest            PWA manifest
├── robots.txt · sitemap.xml
├── vendor/
│   ├── motion.min.js           self-hosted Motion build — animate, scroll, inView, stagger
│   └── LICENSE.md              Motion's MIT licence, carried with the bundle
└── brand/
    ├── BRAND.md                usage guide — read before using any asset
    ├── logo/                   marks, lockups, wordmark, mono cuts
    ├── favicon/                browser + PWA icons
    ├── social/                 avatar, OG image
    └── concepts-batch-1..3.html   the 30 explored directions, kept for reference
```

### Motion

`vendor/motion.min.js` is a hand-picked, esbuild-bundled subset of the `motion` package pinned in
`../package.json` (`animate`, `scroll`, `inView`, `stagger`, `spring`, `easeOut` — the only exports
`index.html` uses). It's self-hosted rather than pulled from a CDN so the page has zero runtime
network dependency and the version can't drift silently.

`index.html` imports it in a `<script type="module">` and drives: the scroll-progress rail, the
staggered reveal of grid rows (services, team, plans, process steps, work items), the hero tag
pop-in, and the stat counters. If the import fails for any reason, a `catch` block adds
`.motion-fallback` to `<html>` and falls back to the plain CSS/vanilla-JS versions of the same
effects — the page never depends on the module succeeding.

**To rebuild after bumping the `motion` version** (run from inside `drishtim-web/`, where its own
`package.json` / `node_modules` live):

```bash
npm install                      # picks up the new version from package.json
echo "export { animate, scroll, inView, stagger, spring, easeOut } from 'motion';" > _motion_entry.mjs
npx esbuild _motion_entry.mjs --bundle --format=esm --minify --target=es2020 \
  --outfile=vendor/motion.min.js
rm _motion_entry.mjs
cp node_modules/motion/LICENSE.md vendor/LICENSE.md
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

1. **Wire the contact form.** `<form action="REPLACE_WITH_FORM_ENDPOINT">` near the bottom of
   `index.html` is still a placeholder — pick a form backend (Formspree, Getform, a Cloudflare
   Worker, etc.), paste the real endpoint, and send a test submission before this goes live.
2. **Outline the wordmark** for any print or third-party use. See BRAND.md.
3. **Check performance on a real mid-range Android.** Heavy `backdrop-filter` is the most expensive
   thing on the page. If it stutters, drop `--blur` from `22px` to `10px` in `:root`.
4. **Eyeball the Motion effects in an actual foregrounded tab** (scroll-progress rail, staggered
   card reveals, counters) — they're driven by `requestAnimationFrame` and were built against the
   library's source rather than watched end-to-end live, since the sandbox this was built in keeps
   its tab backgrounded and `rAF` starved. Everything degrades to the plain CSS/JS version via
   `.motion-fallback` if the import ever fails, so worst case is the old behaviour, not breakage —
   but give it one real look before shipping.

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

Copy on this site reflects decisions recorded in `../FACTS.md` and `../DRISHTIM-OFFER.md` —
channels sold, the rate card, and Bharat Fine Dine's rating and review count. **The figures are
not repeated here.** `../FACTS.md` is authoritative: if this site and that file disagree, the file
wins — fix the site.

© 2026 Drishtim · Latur, Maharashtra
