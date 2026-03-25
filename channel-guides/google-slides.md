---
name: Google Slides Channel Guide
description: DemandScience-specific rules for building slide decks in Google Slides.
version: 2.1
last-updated: 2026-03-25
---

# Google Slides Channel Guide

Reference `ds-brand-design.md` for all base rules. This file covers Google Slides-specific application.

---

## Slide Size

- **Widescreen 16:9** — 25.4cm × 14.29cm (default Google Slides widescreen)
- Do not use 4:3 or custom sizes without explicit approval.

---

## Slide Background

**All slides use a white background. No exceptions.**

- Default background: white `#FFFFFF` — every slide, every type.
- Color and brand elements are applied through text, shapes, cards, and footer bars — not the slide background itself.
- The gradient and navy are used only for contained design elements (footer bars, section shape accents, CTA buttons) — never as a full slide background.

---

## Footer (All Slides)

Every slide includes a footer bar:

- **Height:** ~0.4" from bottom
- **Background:** Navy `#061947` or gradient (`#061947` → `#0266F7`)
- **Contents (left to right):**
  - "Confidential" label — white, Inter 9pt
  - Centered: DS logo (white version)
  - Right-aligned: slide number — white, Inter 9pt

---

## Typography in Slides

**All text on all slides is left-aligned. No centered text anywhere.**

| Level        | Font    | Size    | Weight   | Color                   | Alignment |
|--------------|---------|---------|----------|-------------------------|-----------|
| H1 / Title   | Poppins | 32pt    | SemiBold | Navy `#061947`          | Left      |
| H2 / Heading | Poppins | 24pt    | SemiBold | Navy `#061947`          | Left      |
| H3 / Subhead | Poppins | 18pt    | SemiBold | Electric Blue `#0266F7` | Left      |
| Body         | Inter   | 12–14pt | Regular  | Dark Grey `#1E293B`     | Left      |
| Caption/note | Inter   | 9pt     | Regular  | Medium Grey `#64748B`   | Left      |
| Callout stat | Poppins | 40pt+   | Bold     | Navy or Electric Blue   | Left      |

> **Fallback font:** If Poppins/Inter are unavailable, Google Slides will revert to Arial.

**Formatting tips (from official brand guide):**
- Use **bold** to highlight key ideas
- Use Electric Blue `#0266F7` to emphasize important points in copy
- Use Navy `#061947` for headlines
- Use white text only on the navy footer bar — never on the white slide background

---

## Slide Layout Patterns

### Standard Content Slide
- White background
- H1 title: top-left, Poppins SemiBold 32pt, Navy
- Body: left-aligned, Inter 12–14pt, Dark Grey
- Navy footer bar at bottom

### Two-Column Content
- White background
- Left column: H1 + body text + optional CTA shape
- Right column: image (rounded rectangle mask, 0.15" radius), chart, or product UI
- Equal columns or 55/45 split
- All text left-aligned

### Stat Callout Slide
- White background
- 3–4 stats laid out horizontally, left-to-right
- Large number: Poppins Bold 40pt+, Navy or Electric Blue, left-aligned
- Short label below: Inter 14pt, Medium Grey, left-aligned
- Generous horizontal spacing between stats

### Full Image / Visual Slide
- White background
- Image fills right column or ~60% of slide with rounded rectangle mask (0.15" radius)
- Left column: H1 + supporting copy, all left-aligned

### Quote / Testimonial
- White background
- Quote text: Poppins Bold, large, Navy, left-aligned
- Attribution: Inter, Medium Grey, smaller, left-aligned
- Optional: quotation mark accent shape in Baby Blue `#CDEDFD`

### Divider / Transition Slide
- White background
- Bold section title: Poppins Bold 32pt, Navy, left-aligned
- Optional: thin navy or Electric Blue rule line above title
- Subtitle or section description: Inter 14pt, Medium Grey, left-aligned

---

## Cards in Slides

- Rounded rectangles: ~0.15" corner radius
- Fill: white or light grey `#F8F9FB`
- Shadow: soft, low opacity (Google Slides: drop shadow ~4pt blur, 20% opacity)
- Consistent padding inside card shapes

---

## Color Use in Slides

| Color | Use |
|-------|-----|
| Navy `#061947` | H1 titles, key headings, footer bar background |
| Electric Blue `#0266F7` | Subheadings, callout emphasis, icon color, key numbers |
| Baby Blue `#CDEDFD` | Subtle shape accents, card backgrounds, tag shapes |
| Electric Blue `#0266F7` | CTA button shapes, links, and active emphasis — nowhere else |
| Dark Grey `#1E293B` | All body copy |
| Medium Grey `#64748B` | Captions, secondary labels |
| White `#FFFFFF` | Slide background (always), text on footer bar |
| Gradient | Footer bar only — never a full slide background |

---

## Icons in Slides

- Source: Google Material Symbols Rounded — https://fonts.google.com/icons?icon.style=Rounded
- In Google Slides: export icon as SVG from the icon font site and insert as image.
- Color: Navy `#061947` or Electric Blue `#0266F7` only.
- Size: proportional to surrounding text; never oversized or decorative.

---

## Brand Police — Slides Spot Check

- [ ] All slide backgrounds are white `#FFFFFF`
- [ ] All text is left-aligned — no centered text on any slide
- [ ] H1 is Poppins SemiBold 600 32pt, Navy
- [ ] Body is Inter 12–14pt, Dark Grey
- [ ] Gradient appears only in the footer bar — not the slide background
- [ ] Navy footer bar on every slide with "Confidential", logo, page number
- [ ] CTA buttons use Electric Blue (#0266F7) only
- [ ] Icons are Google Material Symbols Rounded, Navy or Electric Blue

---

## Reference Decks

> Add reference deck links or screenshots here as they are approved.
> Format: [Deck Name] — [link or file path] — [what it demonstrates]

<!-- PLACEHOLDER — drop reference deck files in /templates/google-slides/ -->
