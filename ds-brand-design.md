---
name: ds-brand-design
description: Unified DemandScience design system for slides, docs, web, infographics, and internal/public assets.
version: 2.5
last-updated: 2026-03-25
source: Updated from 25-DS-BrandGuide-General.pdf
---

# DemandScience Design System

Design everything — decks, docs, dashboards, web, infographics — as one **cohesive brand story**: focused, spacious, data‑driven, and predominantly on white.

Use this as the **source of truth** for visual decisions. Format‑specific skills (PPTX/DOCX/XLSX, component libraries, Google Slides, etc.) sit on top of this.

---

## 1. Brand Story & Principles

### 1.1 Mission & Vision

**Mission:** Our mission is to empower B2B Marketers to take back control of their growth.

**Vision:** We envision a world where B2B marketing's complexity has been replaced with transparency and empowerment — enabling marketers to take control of their growth, without compromises and constraints.

### 1.2 What the Brand Should Feel Like

- Open and confident, with generous whitespace
- Data‑driven but human — clarity over spectacle
- Modern, minimal layouts with color as **accent**, not wallpaper
- A breath of fresh air in a messy, overcomplicated market

### 1.3 Core Design Principles

1. **Clarity first:** If a design choice reduces legibility or comprehension, it's wrong.
2. **White as the stage:** Default to white backgrounds; let typography and data do the work.
3. **One focal point per view:** Every slide/screen/page has one obvious hero message or visual.
4. **Color as a highlighter:** Cool greys for structure, brand colors for accents and CTAs only.
5. **Consistency across channels:** Same components and rules for docs, slides, web, infographics, internal and external.
6. **Accessible by default:** Assume WCAG 2.1 AA as the baseline for all digital work.

> For full tone of voice, elevator pitches, and brand messaging see `content/voice-and-tone.md`.

---

## 2. Color System

### 2.1 Palette

**Primary** *(Official values from 25-DS-BrandGuide-General.pdf)*

| Name          | Hex       | PDF Name       | CSS Variable       | Usage                                              |
|---------------|-----------|----------------|--------------------|----------------------------------------------------|
| Navy          | `#061947` | Navy Blue      | `--ds-navy`        | Primary headings, key UI, dark text on white       |
| Electric Blue | `#0266F7` | Electric Blue  | `--ds-blue`        | Links, CTAs, emphasis text, key numbers, interactive |

**Extended**

| Name        | Hex       | PDF Name    | CSS Variable        | Usage                                             |
|-------------|-----------|-------------|---------------------|---------------------------------------------------|
| Baby Blue   | `#CDEDFD` | Baby Blue   | `--ds-blue-light`   | Subtle accent backgrounds, chips, tags, alt table rows |
| Navy Light  | `#0A2A8F` | —           | `--ds-navy-light`   | Hover states on navy, dark gradients              |
| Red Orange  | `#F40356` | —           | `--ds-red-orange`   | Destructive actions and critical alerts           |

**Neutrals (cool greys)**

| Name        | Hex       | CSS Variable        | Usage                                              |
|-------------|-----------|---------------------|----------------------------------------------------|
| Dark Grey   | `#1E293B` | `--ds-dark-grey`    | Main body text on white                            |
| Medium Grey | `#64748B` | `--ds-medium-grey`  | Secondary text, helper copy, muted labels          |
| Light Grey  | `#F8F9FB` | `--ds-light-grey`   | Soft backgrounds for cards/sections                |
| White       | `#FFFFFF` | `--ds-white`        | Default page background everywhere                 |

**Gradient**

| Token | Value | Use |
|-------|-------|-----|
| `--ds-gradient`         | `linear-gradient(to right, #061947, #0266F7)` | Default horizontal |
| `--ds-gradient-135`     | `linear-gradient(135deg, #061947, #0266F7)` | Diagonal — hero & cards |
| `--ds-gradient-45`      | `linear-gradient(45deg, #061947, #0266F7)` | Reverse diagonal |
| `--ds-gradient-radial`  | `radial-gradient(circle at 30% 50%, #0266F7, #061947)` | Overlay / radial focal |
| `--ds-gradient-animated`| `linear-gradient(135deg, #061947, #0266F7, #0A2A8F)` + `@keyframes gradientShift` | Hero animated background |

- Use for: hero areas, title slides, section dividers, closing slides, and high‑impact bands.
- **Not** a default background. Never on slide backgrounds or data cards.

> **Color usage summary:**
> - **White = default background**
> - **Cool greys = structure (cards, panels, table rows)**
> - **Brand colors = accents and CTAs**

> **Rule:** No off‑palette colors. If it's not defined here, it's off‑brand.

### 2.2 CSS Custom Properties (Web / HTML)

```css
:root {
  /* Brand — official values from 25-DS-BrandGuide-General.pdf */
  --ds-navy:       #061947;   /* Navy Blue */
  --ds-navy-light: #0a2a8f;   /* Hover/dark gradient variant */
  --ds-blue:       #0266f7;   /* Electric Blue */
  --ds-blue-light: #cdedfd;   /* Baby Blue */
  --ds-red-orange: #f40356;   /* Destructive / alerts */

  /* Neutrals */
  --ds-dark-grey:   #1e293b;
  --ds-medium-grey: #64748b;
  --ds-light-grey:  #f8f9fb;
  --ds-white:       #ffffff;

  /* Gradient */
  --ds-gradient:         linear-gradient(to right, #061947, #0266f7);
  --ds-gradient-135:     linear-gradient(135deg,   #061947, #0266f7);
  --ds-gradient-animated: linear-gradient(135deg,  #061947, #0266f7, #0a2a8f);

  /* Typography */
  --font-sans: 'Poppins', ui-sans-serif, system-ui, sans-serif;
  --font-body: 'Inter', ui-sans-serif, system-ui, sans-serif;
  --font-mono: ui-monospace, SFMono-Regular, monospace;
}
```

---

## 3. Typography & Hierarchy

### 3.1 Families

| Role              | Family     | CSS Variable    |
|-------------------|------------|-----------------|
| Headings/Display  | Poppins    | `--font-sans`   |
| Body/UI           | Inter      | `--font-body`   |
| Code/Technical    | System mono | `--font-mono`  |

**Google Fonts import (HTML):**

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet" />
```

> **Rule:** Never mix in other font families.

### 3.2 Type Scales

**Marketing / Narrative (web, decks, one-pagers):**

| Level       | Size / Line-height | Family  | Weight |
|-------------|-------------------|---------|--------|
| H1          | 50px / 60px       | Poppins | 600    |
| H2          | 38px / 45px       | Poppins | 600    |
| H3          | 30px / 36px       | Poppins | 600    |
| H4          | 24px / 30px       | Poppins | 600    |
| H5          | 18px / 24px       | Poppins | 600    |
| Body        | 18px / 28px       | Inter   | 400    |
| Body small  | 16px / 24px       | Inter   | 400    |
| Caption     | 12px / 16px       | Inter   | 400    |

**Application / UI:**

| Level          | Size   | Weight   |
|----------------|--------|----------|
| Page title     | 30px   | Semibold |
| Card title     | 24px   | Semibold |
| Dialog title   | 18px   | Semibold |
| Section heading | 16px  | Medium   |
| Label          | 14px   | Medium   |
| Body           | 14–16px | Regular |

**Docs / PDFs (point sizes):**

| Level  | Size      | Family  | Color     |
|--------|-----------|---------|-----------|
| Title  | 28–32pt   | Poppins | Navy      |
| H1     | 22–24pt   | Poppins | Navy      |
| H2     | 18pt      | Poppins | Blue      |
| H3     | 14pt      | Poppins | Navy      |
| Body   | 11pt      | Inter   | Dark Grey |

### 3.3 Alignment & Formatting Rules

- **Default: left‑aligned** across all media.
- Center only:
  - Major hero headlines (H1 in web hero or title slide)
  - Single stat callouts with minimal text
- Body color:
  - Marketing web: `#403F3F` on white
  - Apps/docs: `#1E293B` on white
- Use **bold**, not italic, for emphasis.
- Maintain 55–80 characters per line for long reading.
- Clear semantic hierarchy: no skipping from H1 to H4 without intermediate levels.

> **Rule of thumb:** If you're not sure, left‑align it.

---

## 4. Layout, Space & Composition

### 4.1 Spacing Philosophy

- White is the default background. Avoid full‑bleed color unless there's a specific story reason (hero, divider, closing).
- Use **more whitespace than feels safe** — if everything feels tight, you haven't pushed far enough.
- Group related items tightly; separate groups with generous vertical space.

### 4.2 Common Layout Patterns

| Pattern         | Description                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------|
| Two-column hero | Left: headline + copy + primary CTA. Right: key image/visual (product UI, illustration, or data).  |
| Card grid       | 2×2 or 3×2 cards on white; cool grey/white backgrounds with subtle shadow.                         |
| Stat strip      | Row of 3–4 stats; large number + 1–2 line label; plenty of space between.                          |
| Section band    | Full-width gradient or navy band between sections; short headline + subhead on it; content above and below on white. |

### 4.3 Cards & Panels

- **Border radius:** 10px (`border-radius: 10px;` / PPT ~0.12–0.15")
- **Default background:** white `#FFFFFF`
- **Alternate background:** light cool grey `#F8F9FB`
- **Shadow:** `0 2px 40px rgba(0, 0, 0, 0.10)` for emphasis; no heavy drop shadows.

```css
.ds-card {
  border-radius: 10px;
  background: var(--ds-white);
  box-shadow: 0 2px 40px rgba(0, 0, 0, 0.10);
  padding: 24px;
}

.ds-card--muted {
  border-radius: 10px;
  background: var(--ds-light-grey);
  padding: 24px;
}
```

> Visual target: clean, white layouts with cool grey blocks and brand color accents — never full‑screen color noise.

---

## 5. Components (Shared Across Channels)

### 5.1 Buttons

**Marketing (web, decks, PDFs):** pill‑shaped, bold, clear.

| Variant   | Background    | Text  | Border            | Radius |
|-----------|---------------|-------|-------------------|--------|
| Primary   | `#0266F7`     | White | None              | 100px  |
| Secondary | Transparent   | Blue  | 2px `#0266F7`     | 100px  |

```css
.ds-btn-primary {
  background: var(--ds-blue);   /* #0266F7 — Electric Blue */
  color: var(--ds-white);
  border: none;
  border-radius: 100px;
  padding: 14px 36px;
  font-family: var(--font-sans);
  font-size: 18px;
  font-weight: 600;
}

.ds-btn-secondary {
  background: transparent;
  color: var(--ds-blue);
  border: 2px solid var(--ds-blue);
  border-radius: 100px;
  padding: 12px 34px;
  font-family: var(--font-sans);
  font-size: 18px;
  font-weight: 600;
}
```

**Product / internal UI:** compact, 8px radius, no pills. Aligned to shadcn-style patterns.

### 5.2 Links & Inline Emphasis

- **Links:** Electric Blue `#0266F7`, underlined on hover; **never CTA red**.
- **Inline emphasis (non-link):** Electric Blue `#0266F7` text, bold; no underline.

### 5.3 Tables & Data

| Area         | Style                                      |
|--------------|--------------------------------------------|
| Header row   | Navy `#061947` background, white bold text |
| Body rows    | Alternate white / Baby Blue `#CDEDFD`      |
| Totals row   | Navy `#061947` background, white bold text |
| Borders      | Light grey `#E5E7EB`, minimal lines        |

### 5.4 Charts

**Color order:**

1. Navy `#061947`
2. Electric Blue `#0266F7`
3. Medium Grey `#64748B`
4. Dark Grey `#1E293B`

**Rules:**
- Charts live on white backgrounds with generous margins.
- Limited gridlines; prioritize clear labels and direct annotations.
- Color meaning is consistent across media (e.g., navy = our data, grey = benchmark).

---

## 6. Icons

### 6.1 Icon Library — Google Material Symbols Rounded

**All DemandScience icons — public-facing and internal — use exclusively:**

> **Google Material Symbols, Rounded style**
> Source: https://fonts.google.com/icons?icon.style=Rounded

This applies to: decks, docs, web, infographics, dashboards, internal tools, and all other formats.

**Import (web/HTML):**

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
```

**Usage:**

```html
<span class="material-symbols-rounded">arrow_forward</span>
```

**Icon styling rules:**

| Property      | Rule                                                              |
|---------------|-------------------------------------------------------------------|
| Style         | Rounded **only** — never Outlined, Sharp, or Two-tone            |
| Color         | Navy (`#05195F`) or Blue (`#0066FC`); avoid pink and off-palette |
| Size          | Match surrounding text scale; common: 20px, 24px, 32px, 48px    |
| Background    | On white: use small cool grey or blue-light circle when anchoring needed |
| Fill          | Default `FILL=0` (outlined weight); use `FILL=1` only for active/selected states |
| Weight        | 400 default; 300 for small/compact layouts                       |

> **Rule:** No third-party icon libraries (Font Awesome, Heroicons, Feather, etc.). Material Symbols Rounded is the single icon source for everything DemandScience.

---

## 7. Imagery, Illustrations & UI Elements

### 7.1 Photography Rules

- Use high-quality, natural-looking photos — avoid overly staged stock images.
- **Avoid subjects looking directly at the camera.**
- Select photographs of professionals in authentic environments — home or office settings — showcasing them actively engaged in productive tasks and collaborating.
- Avoid filters or effects on images.
- All photos in rounded rectangles (same 10px radius as cards).
- Use 1–3 images or UI mockups per screen/slide; never collage overload.
- No cliché generic stock (e.g., a plant growing from coins, handshakes on white backgrounds).

### 7.2 Illustrations & UI Elements

- Ensure designs are clear, focused, and free from excess.
- If using UI elements (icons, charts, or highlights), **limit to 3–4 per illustration** to avoid a cramped look.
- Make sure visuals support the content rather than overpowering it.
- Position UI elements strategically around images to keep the focus on people, not graphics.
  - Place some UI elements behind the subject and some in front.
  - Keep larger elements behind the subject.
- If placing an illustration on a white background, add a light blue shape (`#CDEDFD`) behind the characters to prevent them from looking like they're "floating".

### 7.3 Icons in Illustrations

- Icons should be outlined and match brand colors: Navy `#061947` and Electric Blue `#0266F7`.
- Use simple, modern icons — no overcomplicated designs.
- Source: Google Material Symbols Rounded only (see §6).

---

## 8. Motion (Web / Decks)

Full specification: `assets/motion-guide.md`

### Core Principles
1. **Motion has meaning** — every animation communicates something. If it can be removed without confusing the user, remove it.
2. **Motion is responsive** — feedback starts within 100ms of the trigger. Never make users wait for an animation.
3. **Motion is natural** — elements decelerate on arrival, accelerate on exit. No snapping, no floating.
4. **Motion is focused** — one thing moves at a time. Choreograph sequences so attention is guided, not split.
5. **Motion respects users** — `prefers-reduced-motion` is always honoured.

### Easing System (Material Design 3 adapted)

| Token | Curve | Use |
|-------|-------|-----|
| `--ease-emphasized`            | `cubic-bezier(0.2, 0, 0, 1.0)` | Brand-forward transitions |
| `--ease-emphasized-decelerate` | `cubic-bezier(0.05, 0.7, 0.1, 1.0)` | Entering elements |
| `--ease-emphasized-accelerate` | `cubic-bezier(0.3, 0, 0.8, 0.15)` | Exiting elements |
| `--ease-standard`              | `cubic-bezier(0.2, 0, 0, 1)` | UI state changes |
| `--ease-standard-decelerate`   | `cubic-bezier(0, 0, 0, 1)` | UI element entering |
| `--ease-standard-accelerate`   | `cubic-bezier(0.3, 0, 1, 1)` | UI element leaving |
| `--ease-linear`                | `cubic-bezier(0, 0, 1, 1)` | Color/opacity fades ONLY |

### Duration Scale

| Category | Range | Use |
|----------|-------|-----|
| Short `--dur-short-*` | 50–200ms | Hover states, icon changes, focus rings |
| Medium `--dur-medium-*` | 250–400ms | Dropdowns, badges, card hovers |
| Long `--dur-long-*` | 450–600ms | Modals, panels, section reveals |
| Extra Long `--dur-xlong-*` | 700–1000ms | Hero entrances, page transitions |

**Rule:** Scale duration with visual weight. Button hover = 150ms. Full hero reveal = 600–700ms.

### Approved Patterns
- **Fade Up** — scroll reveals: `opacity 0→1 + translateY(24px→0)`, 450ms, `--ease-emphasized-decelerate`
- **Scale In** — modal/overlay enter: `opacity 0→1 + scale(0.92→1)`, 300ms, `--ease-emphasized-decelerate`
- **Slide In** — panel/drawer: `opacity 0→1 + translateX(20px→0)`, 350ms, `--ease-emphasized-decelerate`
- **Hover Lift** — cards/buttons: `translateY(-3px) + shadow`, 200ms, `--ease-standard`
- **Fade Through** — content swap: exit (100ms accelerate) then enter (300ms decelerate)

### Stagger
Multiple elements animate in sequence at 40–60ms intervals. Maximum 6 items staggered.

### Spatial Rules
- Forward/deeper navigation → slide left
- Back navigation → slide right
- Modal/overlay open → scale in from center
- Expand (accordion) → slide down
- Collapse → slide up

### Never
- Infinite decorative loops (loaders excepted)
- Simultaneous competing animations
- Linear easing on positional/scale transitions
- Animating `width`, `height`, `top`, `left` (causes layout jank — use `transform` instead)
- Skipping `prefers-reduced-motion`

---

## 9. Accessibility & Performance (Digital)

### 9.1 Accessibility

- Color contrast meets WCAG 2.1 AA minimum.
- Left‑aligned copy for better readability.
- Semantic elements: real headings, buttons, links, labels.
- Visible focus states; never remove outlines without a strong alternative.
- Don't rely on color alone to indicate state or meaning.

### 9.2 Performance & Asset Choices

- Prefer **SVG** for logos, icons, simple illustrations.
- Use WebP/AVIF for photos with responsive sizes and lazy loading.
- CSS first for layout and motion; avoid heavy JS for simple UI.
- Keep pages lightweight: fewer fonts, optimized images, minimal third-party bloat.

---

## 10. Channel‑Specific Notes

### 10.1 Decks (PPTX / Google Slides)

- **All slide backgrounds are white `#FFFFFF` — every slide, no exceptions.**
- Gradient and navy are used only in contained elements: footer bars, shape accents, CTA buttons — never as a full slide background.
- **All text is left-aligned on all slides — no centered text anywhere.**
- Type scale for slides:
  - H1 / Title: Poppins SemiBold, **32pt**, Navy `#061947`
  - H2 / Heading: Poppins SemiBold, 24pt, Navy
  - H3 / Subhead: Poppins SemiBold, 18pt, Electric Blue `#0266F7`
  - Body: Inter Regular, **12–14pt**, Dark Grey `#1E293B`
  - Captions: Inter Regular, 9pt, Medium Grey
- Every slide has a navy footer bar with "Confidential", DS logo, and page number.

### 10.2 Docs & PDFs

- 1" margins, primarily white pages.
- Left‑aligned text throughout; no justified paragraphs.
- Cool grey card backgrounds for callouts and sidebars.
- CTA buttons in Electric Blue (#0266F7) when there's a clear action.

### 10.3 Web & Landing Pages

- White page background; gradient only in reserved hero/section bands.
- Hero: left‑aligned H1 + body + buttons; supporting visual on the right.
- Sections stack vertically with consistent spacing, cool grey cards, and minimal color blocks.
- Typographic rhythm and card patterns align with deck and doc styles.

### 10.4 Internal Assets

- Same visual standards as external.
- Slightly denser layouts allowed for productivity — never at the expense of legibility.
- Cool grey accents for statuses and internal labels; brand colors for primary meaning and actions.

---

## 11. Design System Validation Rule

**This rule applies to every piece of work created or reviewed in this system.**

Whenever Claude generates, reviews, or iterates on any DemandScience asset — slide, doc, web page, infographic, component, or internal file — it must automatically run a design system check and flag any violations before delivering the output.

### What to check on every output

| Category       | What to validate                                                                 |
|----------------|----------------------------------------------------------------------------------|
| Colors         | Every color used must exist in the approved palette. Flag any hex not in the system. |
| Typography     | Poppins for headings, Inter for body only. Sizes must follow the defined scale.  |
| Alignment      | Body and headings left-aligned by default. Flag any centered text that shouldn't be. |
| CTA color      | Electric Blue `#0266F7` on CTA buttons, links, and interactive states only. Flag any off-palette CTA use. |
| Icons          | Google Material Symbols Rounded only. Flag any other icon library or style.      |
| Spacing        | Generous whitespace. Flag tight, cramped, or inconsistent spacing.               |
| Cards          | 10px radius, white or light grey fill, correct shadow. Flag deviations.         |
| Background     | White is default. Gradient/dark only on hero, dividers, closing. Flag overuse.  |
| Charts/tables  | Must follow the defined color order and table styles.                            |
| Accessibility  | Contrast must meet WCAG 2.1 AA. Flag any low-contrast text or color-only states.|

### How to report violations

When a violation is found, call it out clearly before or alongside the output:

```
⚠ Design System Issue: [what] — [why it's a violation] — [what to use instead]
```

Examples:
- `⚠ Design System Issue: Off-palette color used as a section background — Use Light Grey #F8F9FB instead.`
- `⚠ Design System Issue: Font "Montserrat" found — Only Poppins (headings) and Inter (body) are approved. Replace with Poppins.`
- `⚠ Design System Issue: Icon from Heroicons — All icons must be Google Material Symbols Rounded. Replace with the equivalent Rounded icon.`

If no violations are found, confirm with a single line:
```
✓ Design system check passed.
```

> **This check is mandatory and non-optional.** It runs on all outputs regardless of whether the user asks for it.

---

## 12. Design Do's & Don'ts

*Sourced directly from 25-DS-BrandGuide-General.pdf*

### Do
- Keep layouts clean and professional — avoid clutter
- Use simple, modern icons (no overcomplicated designs)
- Use contrast to make text readable: dark text on light backgrounds, white text on dark
- Make sure visuals support the content (charts, icons, etc.)
- Use Navy Blue for headlines on light backgrounds
- Use white text on dark or gradient backgrounds for readability
- Use Electric Blue to emphasize important points in copy
- Use bold text to highlight key ideas
- Limit UI elements to 3–4 per illustration

### Don't
- Use random or off-brand colors
- Use generic or cliché stock images (e.g., a plant growing from coins)
- Use too many fonts or styles — keep it consistent
- Use subjects looking directly at the camera in photos
- Apply filters or effects to images
- Use more than 3–4 UI decorative elements on a single composition
- Use industry jargon when plain language works

---

## 13. Quick Pre‑Flight Checklist

Before shipping any asset — slide, doc, web page, infographic, or internal file — verify:

- [ ] White is the primary background; gradients/dark used intentionally
- [ ] Body copy and most headings are left‑aligned
- [ ] Colors only from the approved palette; cool greys for cards and structure
- [ ] Poppins for headings, Inter for body; sizes follow shared scales
- [ ] Electric Blue (#0266F7) used for CTA buttons, links, and interactive states
- [ ] All icons are **Google Material Symbols Rounded** — no other icon libraries
- [ ] Cards and images have consistent 10px rounded corners and generous spacing
- [ ] Charts/tables use shared styles and color order
- [ ] Copy is plain‑language, outcome‑focused, and partner‑first
- [ ] Accessible contrast and sensible motion (if digital)
- [ ] Overall feel: clean, white, spacious — color as accent only
