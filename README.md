# ykvdvd.com

Static portfolio site for Yaakov David. Built to the Claude Design handoff
`Portfolio redesign for ykvdvd.com` (the **v2** artboard).

No build step, no dependencies. Three files.

```
index.html
assets/styles.css
assets/main.js        # mobile nav only
assets/img/           # screenshots (see below)
```

## Run locally

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321

## Deploy

Drag the folder into Netlify / Cloudflare Pages / Vercel, or `rsync` it to any
static host. There is nothing to compile.

## Optional image

`assets/img/og.jpg` (1200×630) is referenced by the `og:image` meta tag for link
previews. Add it whenever you like — browsers never fetch it, so nothing breaks
while it is missing, but social/chat link unfurls will have no image until then.

## Design tokens

Defined once as CSS custom properties at the top of `styles.css`:

| Token          | Value       | Used for                          |
| -------------- | ----------- | --------------------------------- |
| `--ink`        | `#00081a`   | page ground                       |
| `--ink-2`      | `#000E22`   | case section gradient top         |
| `--navy`       | `#001534`   | text on yellow/orange             |
| `--blue`       | `#0066FF`   | brand gradients, contact band     |
| `--blue-lt`    | `#4D8BFF`   | links, eyebrows, hairlines        |
| `--blue-pale`  | `#9FC0FF`   | hero badge text                   |
| `--blue-deep`  | `#132965`   | gradient ends                     |
| `--yellow`     | `#F5EF3E`   | accents, primary CTA, hover       |
| `--orange`     | `#FF8F45`   | header CTA, wound-down states     |
| `--green`      | `#22C55E`   | live status dot                   |

Type: **Oswald** (headings, uppercase) · **DM Sans** (body) · **DM Mono**
(eyebrows, labels, tags, links).

## Notes on fidelity

- Every colour, radius, padding, font-size, line-height and letter-spacing is
  transcribed from the handoff's inline styles.
- The prototype's `style-hover="…"` attributes are implemented as real `:hover`
  rules.
- The handoff had no mobile spec. Added, in the same visual language: a
  hamburger + dropdown panel below 860px, tighter gutters below 560px, and the
  stat / screenshot grids allowed to sit two-up on narrow screens (same
  `auto-fit` rule the design uses, just a smaller track minimum).
- `prefers-reduced-motion` disables the drifting hero grid and the pulsing
  status dot.
- The open mobile panel is opaque rather than translucent: a `backdrop-filter`
  nested inside the header's own `backdrop-filter` composites wrong in Chrome
  and let the hero bleed through it.
- The design's `auto-fit` track minimums (300–330px) cannot shrink below
  themselves and overflowed a 320px phone, so the card grids go explicitly
  single-column under 560px. The stat row — a single row of four by design —
  becomes a clean 2×2 under 900px instead of a 3+1 orphan.
- The handoff's four 9:16 screenshot slots in the Hineni case were dropped at
  your request; the case now runs cards → architecture → shorter reads.

## Content

Real copy throughout. The prototype's placeholder Yamofi paragraph, the
Meor.care description and case, and the architecture diagram's "placeholder
vendor names" were replaced with the real product and stack details. Hero stat
numbers (5 / 4 / 1.4M / 20+) are carried over from the design as-is.
