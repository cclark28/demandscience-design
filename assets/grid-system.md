---
name: Grid System
description: DemandScience grid specification for slides, web, and docs — spacing tokens, column system, and layout rules.
version: 1.0
last-updated: 2026-03-25
---

# DemandScience Grid System

Every layout is built on an 8px base unit. All spacing, sizing, and positioning values are multiples of 8. This ensures perfect visual rhythm across every format.

---

## Base Unit

**8px** — every spacing value is a multiple of 8.

| Token | Value | Use |
|-------|-------|-----|
| `--space-1` | 8px | Micro gaps, icon padding |
| `--space-2` | 16px | Component internal padding |
| `--space-3` | 24px | Card padding, gutter |
| `--space-4` | 32px | Section sub-spacing |
| `--space-5` | 40px | Slide top margin |
| `--space-6` | 48px | Section spacing |
| `--space-7` | 64px | Slide left/right margin |
| `--space-8` | 80px | Large section padding |
| `--space-10` | 96px | Web section padding |

---

## Google Slides Grid

**Canvas:** 960 × 540px (represents 10" × 5.625" in Google Slides)

```
┌─────────────────────────────────────────────────────────────┐  ← 0px
│                      TOP MARGIN (40px)                      │
├──┬───┬──┬───┬──┬───┬──┬───┬──┬───┬──┬───┬──┬───┬──┬───┬──┤  ← 40px
│  │ 1 │  │ 2 │  │ 3 │  │ 4 │  │ 5 │  │ 6 │  │ 7 │  │ 8 │  │
│64│   │16 │   │16 │   │16 │   │16 │   │16 │   │16 │   │16 │64│
│px│col│px │col│px │col│px │col│px │col│px │col│px │col│px │px│
│  │   │   │   │   │   │   │   │   │   │   │   │   │   │   │  │
├──┴───┴──┴───┴──┴───┴──┴───┴──┴───┴──┴───┴──┴───┴──┴───┴──┤  ← 504px
│                    FOOTER BAR (36px) Navy                   │
└─────────────────────────────────────────────────────────────┘  ← 540px
```

| Property | Value | Notes |
|----------|-------|-------|
| Canvas width | 960px | 10" at 96dpi |
| Canvas height | 540px | 5.625" at 96dpi |
| Left margin | 64px | Safe zone |
| Right margin | 64px | Safe zone |
| Top margin | 40px | Above content |
| Footer height | 36px | Navy bar, always present |
| Content area width | 832px | 960 - 64 - 64 |
| Content area height | 428px | 540 - 40 - 36 - 36 padding |
| Columns | 8 | |
| Gutter | 16px | Between columns |
| Column width | 88px | (832 - 7×16) / 8 |

### Common Column Spans (Slides)

| Layout | Columns | Width |
|--------|---------|-------|
| Full width | 8 of 8 | 832px |
| Two column (equal) | 4 of 8 | 400px each + 32px gap |
| Two column (60/40) | 5+3 | 504px + 296px |
| Three column | ~2.5 of 8 | 261px each |
| Sidebar + content | 2+6 | 192px + 592px |

### Pixel Equivalents for Google Slides Type Sizes

Google Slides uses points. At 960px = 10", the conversion is 1pt = 1.333px.

| Size | Points (Slides) | Pixels (HTML) |
|------|----------------|---------------|
| H1 / Title | 32pt | 43px |
| H2 / Heading | 24pt | 32px |
| H3 / Subhead | 18pt | 24px |
| Body | 12–14pt | 16–19px |
| Caption | 9pt | 12px |
| Stat callout | 40pt+ | 53px+ |

---

## Web Grid

**Container:** max-width 1200px, centered.

| Breakpoint | Columns | Gutter | Margin |
|------------|---------|--------|--------|
| Mobile (<768px) | 4 | 16px | 20px |
| Tablet (768–1024px) | 8 | 20px | 32px |
| Desktop (>1024px) | 12 | 24px | 32px |

**Common web column spans:**

| Layout | Desktop | Tablet |
|--------|---------|--------|
| Full | 12 | 8 |
| Half | 6 | 4 |
| One-third | 4 | 8 (stacked) |
| Two-thirds | 8 | 8 |
| Sidebar | 3 | 8 (stacked) |

---

## Docs & PDF Grid

| Property | Value |
|----------|-------|
| Page size | US Letter 8.5" × 11" |
| Margins | 1" all sides |
| Content width | 6.5" |
| Column (2-col layout) | 3.1" + 0.3" gap + 3.1" |
| Body text column | Max 65 characters per line |

---

## CSS Implementation (Web)

```css
:root {
  /* Spacing scale — 8px base unit */
  --space-1:  8px;
  --space-2:  16px;
  --space-3:  24px;
  --space-4:  32px;
  --space-5:  40px;
  --space-6:  48px;
  --space-7:  64px;
  --space-8:  80px;
  --space-10: 96px;

  /* Layout */
  --max-width: 1200px;
  --grid-cols: 12;
  --grid-gap:  24px;
  --margin:    32px;
}

.container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--margin);
}

.grid {
  display: grid;
  grid-template-columns: repeat(var(--grid-cols), 1fr);
  gap: var(--grid-gap);
}
```

---

## Grid Rules

1. **Never break the 8px unit** — all values must be divisible by 8.
2. **Content never touches the margin edge** — always respect the safe zone.
3. **Consistent gutters** — gutter size never changes within a layout.
4. **Slides: left-align to the 64px margin** — text, icons, and shapes start here.
5. **Web: max-width container is centered** — full-bleed sections have their content in a container.
6. **Docs: 1" margins are inviolable** — never reduce below 0.75".
