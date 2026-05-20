# Tradveller — Design System

> "We Trade & We Travel — with Style."
> The uniform of the new generation. Designed for movement, inspired by mindset.

Tradveller is a Malaysian streetwear sub‑brand built around one idea: the people who **trade** (assets, ideas, time, energy) are the same people who **travel** — and they need clothing that moves with them. Field‑jacket silhouettes, soft cotton tees, six‑panel caps, small carries. Four categories, tight curation, no logomania.

This design system captures everything needed to design **for** Tradveller — the marks, the colour system, the type pair, the components, the voice, and the page templates that make up the shop.

---

## Sources & provenance

This system was built from a single source repository the user provided:

- **GitHub:** [`Sklee268/Tradveller-Merchandise`](https://github.com/Sklee268/Tradveller-Merchandise) — contains `Landing Page.html`, `Tradveller Design System.html`, `brand-guide.css`, `colors_and_type.css`, `tradveller-merch.css`, and the full official logo PNG set under `assets/`.

Anyone iterating on this system should pull that repo for the original landing page, the long‑form brand book, and the layered CSS stack — it has more detail than fits in this skill folder, and it's the source of truth for everything below.

No Figma files, no separate codebase, no slide decks were provided. The product surface is **one product**: the merch shop (one marketing landing page + product/cart/checkout templates).

---

## Index of files in this folder

| Path | What it is |
|---|---|
| `README.md` | This file — start here. |
| `SKILL.md` | Agent‑Skill entry point. Same content, machine‑readable header. |
| `colors_and_type.css` | The token layer — all colour, type, spacing, radius, shadow CSS variables. **Import this first** on any Tradveller surface. |
| `tradveller-merch.css` | The component layer — promo bar, header, hero, product card, collection grid, footer. Layers on `colors_and_type.css`. |
| `tradveller-pdp.css` | Product detail page + editorial strip styles — gallery, sticky info column, spec strip, story section, callouts, review, cross-sell. Layers on top of `tradveller-merch.css`. |
| `brand-guide.css` | Long‑form brand‑book / specimen page styles. Only needed when rendering a doc like `Tradveller Design System.html`. |
| `assets/` | Logo PNGs in every official lockup × colourway. Use these as `<img>` — do not redraw the bull. |
| `preview/` | The cards you see in the Design System tab — short specimens for tokens, type, components. |
| `ui_kits/shop/` | The reusable component recreation of the live Tradveller shop. Open `index.html` for the full landing page. |
| `fonts/` | Empty unless brand‑supplied Sora .ttf is dropped in — Google Fonts CDN is used by default. |

---

## Content fundamentals

Voice is **quiet, considered, never loud**. Speak like a designer, not a marketer. The brand persuades by being right, not by shouting.

**Tone & cadence**
- **Sentence case** for everything outside the wordmark, section titles, and PROMO chips. No title case ("Our Story" — kept; "Our Story Page" — wrong).
- **No exclamation marks.** Ever. Even on sale banners.
- Short lines. The strongest copy on the site is three to seven words long.
- "We" for the brand, "you" for the customer. Never first‑person singular.
- Em‑dashes are encouraged ("Trade with purpose — Travel with meaning").
- **No emoji.** None. The brand is restrained.

**Voice examples — actual lines from the shop**
- `We Trade & We Travel — with Style.` (master tagline, italic Sora)
- `Designed for movement. Inspired by mindset.` (essay lead)
- `Less, but better.` (product philosophy)
- `Trade with purpose. Travel with meaning. Live with balance.` (footer)
- `The uniform of the new generation.` (collection eyebrow)
- `Thinkers in transit.` (audience pillar)

**Casing rules**
- Wordmark: `TRADVELLER` — always Orbitron 800, uppercase.
- Apparel print: `TVRL.` — Orbitron 800, period in brand purple. **Garment graphic only — never used as a logo, in marketing, or in place of the wordmark.**
- Section titles: Sora 600, sentence case ("Our Products", "The Collection").
- Eyebrows / nav / labels: UPPERCASE with 0.12–0.22em tracking, Sora 500.
- Product names: `Tradveller [Category]` — always lead with the parent brand. ✅ `Tradveller T-Shirt`, ✅ `Tradveller Jackets`, ❌ "TVLR Tee", ❌ "The Bull Cap".

**Price format**
- Always `RM` (caps) + hard space + integer: `RM 60`, `RM 120`. No decimals on round prices.
- Sale: strike old, bold new — `~~RM 80~~  **RM 60**`.

**The five-pillar essay** (paraphrasable but not rewriteable):
1. Life is a journey between two worlds — the one you build and the one you explore.
2. Born from the spirit of **trade and travel**.
3. Clothing made for modern mobility: minimalist, functional, timeless.
4. **Less, but better** — every material, every seam serves a reason.
5. Not luxury, **freedom** — to work anywhere, live everywhere, stay grounded.

---

## Visual foundations

The shop reads in **three notes: ink black, paper white, brand purple**. Everything else is a tonal step between them, or a functional state. There is no secondary brand colour. Purple is a single accent — never a fill of large areas.

**Palette**
- `--tvlr-ink: #0A0A0F` (body text, header, footer)
- `--tvlr-paper: #FFFFFF` (default surface)
- `--tvlr-purple: #6147FD` (bull mark + single accent — buttons hover, cart badge, accents)
- Six‑step neutral scale (`Void → Smoke → Mist → Cloud → Line → Surface`) and a tiny semantic set for `Promo`, `Stock low`, `In stock`, `Press`.

**Type pair**
- **Sora** — the workhorse. Carries the entire shop: section titles (600), product names (600), body (400), eyebrows (500), prices (600). Geometric, slightly squared, modern.
- **Orbitron** — display only. The wordmark, the hero title, voice cards, TVRL. apparel print. Heavy uppercase, +0.04–0.06em tracking. Always 700–800 weight.
- **JetBrains Mono** — receipts, SKUs, hex codes, "vol/issued/doc" metadata in the brand book. Never body copy.

**Spacing & rhythm**
- 4px base scale (`--s-1` = 4 … `--s-25` = 100).
- Page padding: **56px** horizontal at desktop, 32px at < 1200px.
- Section vertical rhythm: **100px top / 80px bottom**.
- Container max width: **1700px** for the shop, **1320px** for the brand book.

**Corner radii**
- `4px` — tiny PROMO chips, mini stamps.
- `6px` — form fields, size buttons.
- `10–12px` — default card radius (product cards, mini cards).
- `18px` — large feature cards (collection blocks, trade banner, voice cards).
- `999px` — pill buttons (Shop now, Check out), tag chips, cart icon buttons.

**Card anatomy**
- Subtle off‑white surface (`--tvlr-surface` #F7F7FA).
- Border: 1px `--tvlr-line` (#E8E8EE) — present but understated.
- Shadow on rest: **none**. Cards lift only on hover.
- Hover: `translateY(-4px)` + `0 20px 40px -16px rgba(10,10,15,.18)`.
- The product image is its own block (`1 / 1.18` aspect), with a tinted gradient background — never a flat fill.

**Backgrounds & imagery**
- Marketing pages tilt **dark**: the hero is near‑black with two layered radial gradients (a purple glow at the bottom centre, a soft white glow upper‑right) plus a triple‑layer of tiny radial dots faking a starfield. No photos in the hero — only the bull silhouette behind the wordmark.
- Product imagery uses **muted, warm gradient panels** under each item: olive/khaki for jackets, taupe/tan for tees, mossy green for caps. Imagery skews **warm, slightly desaturated, matte**, never glossy.
- Collection cards use **full‑bleed gradient + silhouette SVG** of a figure in the garment — not a photo.
- The shop is **light by default**, with strategic dark blocks (promo bar, header, footer, hero, trade banner left half) for rhythm.

**Borders & dividers**
- 1px solid `--tvlr-line` (#E8E8EE) on the light theme; 1px `rgba(255,255,255,.1)` on dark.
- Section breaks in the brand book use a 1px `--tvlr-ink` top rule with a small numbered eyebrow above it — never just whitespace.

**Shadows**
- Cards: `0 12px 24px -16px rgba(10,10,15,.15)` on hover only.
- Modals / cart overlay: `0 24px 60px rgba(0,0,0,.55)`.
- Purple glow (used very sparingly on hero CTA only): `0 0 0 1px rgba(139,123,255,.3), 0 8px 32px rgba(97,71,253,.4)`.

**Buttons**
- **Primary**: black background, white text, pill (999px), 14/28 padding, 14px Sora 500, +0.04em tracking. Hover: background → purple.
- **Light pill**: white background, black text — used on dark banner sections ("Shop now ➜").
- **Ghost**: 1px ink border, transparent. Hover: inverted (black fill, white text).
- **Block CTA**: full‑width, 6px radius (not pill), 18/36 padding, used on product page only ("CHECK OUT").
- Iconography inside buttons is **1.8px stroke, no fill**.

**Press & hover states**
- Hover (links/nav): `color: #fff` (from rgba .92) + a 1px purple underline that scales in from the left over 250ms.
- Hover (product card): `translateY(-4px)` + shadow.
- Hover (primary button): background → purple (#6147FD).
- Press (primary button): background → deep purple (#3D24E0). No squash, no shrink.
- Press (light pill): `translateY(-2px)` keeps even on press.
- Disabled: 50% opacity, no cursor change.

**Animation**
- **Restraint over delight.** Easing: default CSS `ease`, durations 150–300ms.
- Transitions are limited to `color`, `background`, `transform`, `opacity`, `border-color`. No bounces. No spring. No scale > 1.05. No rotation. No parallax.
- The hero has a 3‑dot pagination that animates between slides but no auto‑play indicator.

**Transparency & blur**
- Used **only** on the cart overlay (`rgba(0,0,0,.5)` dim behind a solid card). No frosted glass anywhere else.
- Header / promo bar are **fully opaque black** — no blur on scroll.

**Layout rules**
- Header is sticky (`position: sticky; top: 0; z-index: 50`), 84px tall, solid black.
- Promo bar sits above the header, 36px tall, **not sticky** — it scrolls away.
- Product grid: 4 columns at ≥ 1200px, 2 columns below, 24px gap.
- Collection: asymmetric — one tall block on the left (1.05fr), two stacked cards on the right (1fr).
- Footer: 3‑column (`1.4fr 1fr 1fr`), 80px top padding, **80% line height** for nav links to feel quiet.

**Iconography**
- Inline SVG, **1.6–1.8px stroke**, `stroke="currentColor"`, `fill="none"`. Round line joins.
- 20–24px sized icons in the header, 14–16px inside buttons, 18px in the cart icon button.
- The bull mark itself is **always the PNG logo** — never redrawn. See `assets/`.
- See **ICONOGRAPHY** section below for the full sub‑system.

**The bull**
- The brand's defining mark. A hand‑drawn, angular bull head — frontal, horns out, chest line implied. Always purple (`#6147FD`) on light backgrounds, white (`#FFFFFF`) on dark. Never tinted, never recoloured to match a section.
- Clear space = **1× horn height** around the wordmark, **0.75×** around the solo icon.
- Minimum size: **24px** for the icon, **80px wide** for the horizontal lockup.

---

## Iconography

Tradveller uses **inline SVG only**. No icon font, no Lucide/Heroicons import, no emoji, no Unicode chars‑as‑icons.

The icon language is:
- **Stroke‑only**, 1.6px at 24×24, 1.8px inside buttons.
- `stroke="currentColor"`, `fill="none"`, round line caps, no inner shadows.
- Pulled from a small fixed lexicon: **search, account, bag/cart, arrow‑right, chevron‑left/right, chevron‑down (accordion), heart, check, star (filled), social glyphs (Instagram, Facebook, X)**. That's the whole set.
- Stars in product ratings are the only **filled** icon — `fill="#FACC15"` (the same yellow as the PROMO chip), empty stars `fill="#E5E7EB"`.

**Substitution flag** — the existing repo redraws everything inline. If you need a glyph that isn't in the lexicon above, the closest CDN match is **Lucide** (1.5px stroke, round joins, very similar visual weight). Drop in `<script src="https://unpkg.com/lucide@latest"></script>` and use `<i data-lucide="…"></i>` — but **flag the substitution to a designer** before shipping, because Lucide's joins are subtly rounder than the brand's hand‑drawn set.

**Logo PNGs** are the only "icon assets" in the repo. The bull is **never** SVG‑redrawn for production — always the PNG (see `assets/logo-icon-*.png`). The crude inline SVG bull found in product images on the landing page is a placeholder pattern for **fabric prints only**, not UI.

---

## UI kits in this folder

| Kit | What it covers | Entry |
|---|---|---|
| **`ui_kits/shop`** | The Tradveller merch shop — promo bar, header, hero, products grid, collection asymmetric grid, trade banner, footer. Product card, size picker, qty stepper, cart overlay. | `ui_kits/shop/index.html` |

The shop is the only product surface this brand ships. If a docs site, app, or trader/finance product is added later, drop a new kit alongside this one.

---

## Caveats noted during build

- **No Figma file** was provided. The system is fully grounded in the repo's CSS + HTML, which is itself the source of truth — but if a Figma exists, link it.
- **No Sora `.ttf`** was usable from the repo (only macOS metadata files were present in `uploads/`). The Google Fonts CDN is wired up — metrics are identical. If you have brand‑supplied `.ttf` files, drop them in `fonts/` and uncomment the `@font-face` block at the top of `colors_and_type.css`.
- The original `colors_and_type.css` in the repo referenced **Zilla Slab** and **Gotham** as additional families, but neither is used anywhere in `tradveller-merch.css` or the live landing page — the merch line is **Sora + Orbitron + JetBrains Mono**. They were dropped from this system. Re‑add them only if a future surface (e.g. a corporate site for the parent Tradveller trading product) calls for them.
- The product images on the landing page are **inline SVG illustrations** (folded tee, jacket silhouette, cap, carabiner). These are working placeholders — production should ship product photography. Treat the SVGs as a layout guide for image proportions only.
