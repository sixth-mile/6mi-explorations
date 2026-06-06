# Sixth Mile Operations — Design & Palette Decisions
*Captured June 2026 — based on How We Work standalone iteration session*

---

## Palette

### Primary colors
- **Dark green `#083d2b`** — wordmark, strong brand moments, Visibility program color. Deep forest green. Reserved and purposeful, not used as a general surface.
- **Berry `#920d4e` / Berry dark `#6f0a3c`** — all CTAs, links, active states, the berry tick in the mile-marker pattern. The unified action color across the entire site.
- **Amber `#ba7517`** — Growth Cohort wayfinding, star ratings, nav arrows, arc bullet dots, widget letter icon accents. Pushed harder as an editorial accent throughout.

### Surface colors
- **White `#ffffff`** — default page background. Pure, not off-white.
- **Linen `#f0ebe4`** — warm neutral surface for pathway bands, CTA bands, placeholder areas. Not cream — deliberately warm without triggering the AI default read.
- **Linen mid `#e2d9cf`** — linen borders and dividers.

### Secondary / supporting
- **Sage `#6f8c7b`** — italic flourish on H1 only. Expressive accent, not structural.
- **Sage tint `#dbe6df`** — host row highlight in the widget (green-family accent).
- **Sage soft `#aebfb4`** — subtle borders within green-context elements.
- **Warm dark brown `#2e1f10`** — Sustainable Expansion program wayfinding only. Deep espresso tone, earthy and serious. Pairs well with linen and amber.
- **Amber light `#fdf3e3`** — widget letter icon backgrounds, light amber surfaces.

### Ink / neutrals (green-tinted, not slate-tinted)
- **Ink `#111c18`** — primary text
- **Ink mid `#3d5248`** — body copy
- **Ink muted `#7a9189`** — labels, captions, secondary text
- **Rule `#d8e4dc`** — hairline borders and dividers (green-tinted)

---

## Typography

### Fonts
- **DM Serif Display** — headings (H1, H2), wordmark, display numbers
- **DM Sans** — body, H3, H4, labels, buttons (weights 300/400/500 only)

### Scale
| Token | Size | Usage |
|---|---|---|
| H1 | clamp(2.4rem, 4.4vw, 3.6rem) | Page hero |
| H2 | 2.2rem | Section display heading |
| H3 | 1.3rem (sans, medium) | Section label / subheading |
| H4 | 0.9rem | Card titles |
| Lead | 1.05rem | Intro paragraphs |
| Body | 0.95rem | Default |
| Small | 0.85rem | Dense UI |
| Meta | 0.78rem | Captions, buttons |
| Eyebrow | 0.72rem | Program labels |
| Label | 0.68rem | Uppercase section labels |

### Key decisions
- **Letter spacing on headings: `0em`** — removed crushing. Let DM Serif breathe naturally.
- **Italic serif on H1 only** — the sage italic is a one-time brand flourish, not a repeating pattern. H2/H3 are roman.
- **H2 and H3 clearly separated** — H2 at 2.2rem serif, H3 at 1.3rem sans medium. Previously too close together (1.8 vs 1.7rem).
- **Program names italicized in body copy** — *Visibility*, *Growth Cohort*, *Sustainable Expansion* use `<em>` when appearing mid-sentence.

---

## Impeccable / AI slop rules addressed

| Rule | Fix |
|---|---|
| Crushed letter spacing | Set to `0em` on all headings |
| Italic serif hero | Kept on H1 only as deliberate flourish; removed from H2/H3 |
| Flat type hierarchy | H2 pushed to 2.2rem, H3 pulled to 1.3rem sans |
| Repeated section kicker labels | Replaced `.block-label` + H3 pattern with `.section-heading` — small uppercase H3 label above a real display H2, used sparingly |
| Eyebrow pills | Stripped background and padding — now plain text labels |
| Icon tile stacked above heading | Icons moved inline beside H4 in `.prop-head` flex row |
| Cream/beige palette | White body, linen for surfaces, slate-pale retired, green-pale retired from page structure |
| "Not just X, it's Y" copy cadence | Removed all refutation patterns — lead with the positive claim |

---

## Component decisions

### Eyebrow
Plain text, no pill. `font-size: 0.72rem`, `font-weight: 500`, `letter-spacing: 0.08em`, `text-transform: uppercase`, `color: var(--ink-muted)`. Program-colored variants override the color only.

### Section heading
`.section-heading` pattern: small uppercase sans H3 label above a display serif H2. H2 can be omitted when the label is sufficient on its own.

### Icon chips
Inline beside H4 in a `.prop-head` flex row. No background container — just the stroke icon at 17px. Accent color from tier scope.

### Prop grid
`repeat(auto-fit, minmax(210px, 1fr))` default. Override to `repeat(2, 1fr)` for explicit 2x2 layouts.

### CTA / pathway bands
Linen background with linen-mid border. Berry primary button. No dark background bands on page-level CTAs.

### Navigation active states
- Visibility: dark green underline
- Growth Cohort: amber underline
- Sustainable Expansion: berry underline
- Nav arrows (→): amber

---

## Voice rules
- No em-dashes
- No emoji
- No "not just X, it's Y" or "X, not Y" constructions
- Program names capitalized and italicized in running body copy
- Sentence case throughout
- Lead with the positive claim — never defend or justify
- `6mi.app` always berry when appearing in body copy

---

## Links
- `sixth mile` in intro → `/about` (placeholder, about page not yet built)
- "Get started" in Expansion pathway band → `/contact` (placeholder)
