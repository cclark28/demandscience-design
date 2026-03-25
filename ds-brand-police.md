---
name: ds-brand-police
description: Mandatory design system validator. Run this check against every DemandScience asset before it is delivered, approved, or published.
version: 2.0
last-updated: 2026-03-25
---

# DemandScience Brand Police

**This file is a mandatory check — not optional guidance.**

Run every item below against any DemandScience asset before it leaves your hands: slides, docs, web pages, infographics, components, emails, internal files. If something fails, flag it and fix it before delivery.

---

## Two Levels of Enforcement

### 🚫 STOP — Work halts. Design approval required before proceeding.
### ⚠ WARNING — Flag and correct before delivering.

STOP conditions are non-negotiable. Work does not continue under any circumstance until Design has reviewed and given written approval. See `governance/brand-enforcement.md` for the full list of STOP triggers and the escalation protocol.

**Design contact:** Marketing@demandscience.com · Slack: #design-team

---

## STOP Message Format

Issue this block whenever a STOP condition is detected:

```
╔══════════════════════════════════════════════════════════════╗
║           🚫  DESIGN GOVERNANCE — STOP                      ║
║                                                              ║
║  This request cannot be completed without                    ║
║  Design team review and approval.                            ║
║                                                              ║
║  VIOLATION:    [what rule was triggered]                     ║
║  REQUESTED:    [what was asked for]                          ║
║  RULE:         [the specific standard being violated]        ║
║                                                              ║
║  TO PROCEED:                                                 ║
║  → Email:  Marketing@demandscience.com                       ║
║  → Slack:  #design-team                                      ║
║                                                              ║
║  Do not publish or share any materials until Design          ║
║  has reviewed and given written approval.                    ║
╚══════════════════════════════════════════════════════════════╝
```

---

## STOP Triggers — Immediate Block

Issue a STOP message and halt all work when any of the following are detected in a request or output:

| Trigger | Rule violated |
|---------|--------------|
| Icon library other than Google Material Symbols Rounded | Icon library lock — no exceptions |
| Font other than Poppins or Inter | Typography lock — no exceptions |
| Any hex color not in the approved palette | Color palette lock — no off-palette colors |
| CTA buttons using colors other than Electric Blue `#0266F7` | CTA color lock — Electric Blue only for CTAs |
| Charts using default tool colors (Excel/Sheets palette) | Chart color order is mandatory |
| Charts or visuals on colored or gradient backgrounds | White backgrounds only for data |
| New logo treatment, variant, or custom lockup requested | Logo cannot be modified without Design |
| Public-facing asset not built on an approved template | External materials require approved templates |
| Request with unclear audience or unnamed external use | Ambiguous external use requires review |
| Co-brand or partner logo combination | Partner brand rules must be reviewed |
| Any request the requester describes as a "quick" external asset | One-offs become standards — all external needs review |

---

## How to Use This File

1. Open the asset you are reviewing or have just created.
2. Check for STOP triggers first — if any match, issue the STOP message and halt.
3. Work through each WARNING category below line by line.
4. Mark each item as ✓ (pass) or ⚠ (violation).
5. Fix all violations before delivering.
6. If generating output via Claude — this check runs automatically on every response.

---

## Warning Reporting Format

```
⚠ BRAND VIOLATION — [Category]
   Found:    [what was used]
   Rule:     [what the rule says]
   Fix:      [what to replace it with]
```

If everything passes:
```
✓ Brand police check passed — all systems go.
```

---

## Category Checks

---

### 1. COLOR

| Check | Rule | Fail condition |
|-------|------|----------------|
| All colors are on-palette | Only approved hex values from ds-brand-design.md §2 | Any color not in the palette |
| No off-brand hex values | No custom, approximate, or "close enough" colors | e.g. `#0255E0` instead of `#0266F7` |
| Electric Blue is CTA color | `#0266F7` on CTA buttons, links, and interactive states | Off-palette colors on primary actions |
| Gradient used intentionally | Gradient on hero, cover, dividers, closing only | Gradient as default background or on content slides/sections |
| Cool greys used for structure | Cards, panels, and table rows use `#F8F9FB` or `#CDEDFD` | Off-palette greys, beige, warm tones |
| White is the default background | Pages, slides, and sections default to white | Any non-approved background color used without clear intent |

**Approved palette quick reference:**

```
Navy Blue      #061947     Navy Light    #0A2A8F
Electric Blue  #0266F7     Baby Blue     #CDEDFD
Red Orange     #F40356

Dark Grey      #1E293B     Medium Grey   #64748B
Light Grey     #F8F9FB     White         #FFFFFF

Gradient    linear-gradient(to right, #061947, #0266F7)
```
*Official values from 25-DS-BrandGuide-General.pdf*

---

### 2. TYPOGRAPHY

| Check | Rule | Fail condition |
|-------|------|----------------|
| Heading font is Poppins | H1–H5, display, titles | Any other font on headings |
| Body font is Inter | Body copy, UI labels, captions | Any other font on body text |
| No third-party fonts | Only Poppins and Inter permitted | Montserrat, Lato, Open Sans, etc. |
| Sizes follow the defined scale | See ds-brand-design.md §3.2 | Random or off-scale sizes |
| Heading weights correct | Poppins SemiBold (600) for all headings H1–H5 | Light, regular, or Bold (700) weights on headings |
| No italic for emphasis | Use bold instead | Italic used for emphasis in body text |
| Line length for reading | 55–80 characters per line for long-form copy | Very wide or very narrow text columns |

---

### 3. ALIGNMENT

| Check | Rule | Fail condition |
|-------|------|----------------|
| Default alignment is left | Body copy, bullets, subheadings, card text, labels | Center or right-aligned body text without clear reason |
| Center used selectively | Hero H1, title slide headline, single stat callouts only | Centered body paragraphs, centered bullets, centered subheadings |
| No right-aligned body text | Right-align for numbers in tables only | Right-aligned paragraph text |

---

### 4. ICONS

| Check | Rule | Fail condition |
|-------|------|----------------|
| Library is Material Symbols Rounded | https://fonts.google.com/icons?icon.style=Rounded | Font Awesome, Heroicons, Feather, Lucide, or any other library |
| Style is Rounded only | Never Outlined, Sharp, or Two-tone variants | Any non-Rounded Material icon |
| Icon color is Navy or Blue | `#05195F` or `#0066FC` | Pink icons, grey icons, off-palette colors |
| Icon size is proportional | Matches surrounding text; common: 20, 24, 32, 48px | Oversized decorative icons, undersized unreadable icons |
| Fill state used correctly | `FILL=0` default; `FILL=1` for active/selected states only | Filled icons used decoratively |

---

### 5. SPACING & LAYOUT

| Check | Rule | Fail condition |
|-------|------|----------------|
| Whitespace is generous | More than feels safe — if it feels tight, add more | Cramped, cluttered, or content-dense layouts |
| One focal point per view | One hero message or visual per slide/screen/page | Multiple competing focal points |
| Related items are grouped | Tight grouping within sections; generous gaps between sections | Uniform spacing that blurs section hierarchy |
| Cards have correct padding | 24px padding inside cards (web); proportional in slides/docs | Tight or inconsistent card padding |

---

### 6. CARDS & PANELS

| Check | Rule | Fail condition |
|-------|------|----------------|
| Border radius is 10px | All cards, panels, image masks use 10px radius (web) / ~0.15" (slides) | Sharp corners, excessive rounding (>16px), inconsistent radius |
| Card background is correct | White `#FFFFFF` default; Light Grey `#F8F9FB` alternate | Off-palette card backgrounds |
| Shadow is subtle | `0 2px 40px rgba(0,0,0,0.10)` — soft and low | Heavy drop shadows, colored shadows, no shadow where one is needed |
| Images use rounded masks | All photos cropped in rounded rectangles, same radius as cards | Square-cropped or circle-cropped photos |

---

### 7. BUTTONS & CTAs

| Check | Rule | Fail condition |
|-------|------|----------------|
| Primary CTA is Electric Blue pill | Background `#0266F7`, white text, 100px radius, Poppins 600 | Any other color, shape, or font on a primary CTA |
| Secondary CTA is blue outline | Transparent bg, `#0266F7` border, blue text, 100px radius | Solid secondary buttons, navy grey secondary buttons |
| No off-palette CTAs in marketing | Electric Blue is the CTA color in decks, docs, web | Navy, grey, or off-palette marketing CTAs |
| UI buttons are compact | 8px radius, no pill, shadcn-style — for product/internal UI only | Pill buttons in product UI |

---

### 8. TABLES & DATA

| Check | Rule | Fail condition |
|-------|------|----------------|
| Header row is navy | Navy background `#05195F`, white bold text | Colored, grey, or white header rows |
| Body rows alternate correctly | White and Blue Light `#E8F2FF` alternating | Non-alternating rows, off-palette alternating colors |
| Totals row is navy | Navy background, white bold text | Plain or unstyled totals rows |
| Borders are minimal | Light grey `#E5E7EB` only | Heavy black borders, colored borders |

---

### 9. CHARTS

| Check | Rule | Fail condition |
|-------|------|----------------|
| Color order is correct | Navy → Blue → Medium Grey → Dark Grey | Random colors, brand colors out of order |
| Charts are on white | White background with generous margins | Charts on colored or gradient backgrounds |
| Gridlines are minimal | Few, light gridlines; direct labels preferred | Heavy gridlines, excessive tick marks |
| Color meaning is consistent | Navy = our data, grey = benchmark (maintain across the deck/doc) | Same color used for different meanings across visuals |

---

### 10. ACCESSIBILITY

| Check | Rule | Fail condition |
|-------|------|----------------|
| Text contrast meets AA | WCAG 2.1 AA minimum (4.5:1 for body, 3:1 for large text) | Light grey text on white, yellow text, low-contrast combos |
| Color is not the only signal | State/meaning communicated by more than color | Red = error with no icon or label; color-only data encoding |
| Focus states exist (web) | Visible focus outlines on interactive elements | `outline: none` without a replacement |
| Semantic structure (web/docs) | Real heading tags, button elements, label associations | Visual headings styled as paragraphs; divs used as buttons |

---

### 11. SEO (Web pages only)

| Check | Rule | Fail condition |
|-------|------|----------------|
| Unique title tag | 50–60 chars, keyword-first, ends with `— DemandScience` | Missing, duplicate, or over 60 chars |
| Meta description | 150–160 chars, unique, active voice | Missing, duplicate, or truncated |
| Canonical tag | Present and pointing to the correct URL | Missing or self-referencing incorrectly |
| One H1 per page | Single H1 containing the primary keyword | Multiple H1s or H1 missing |
| Heading hierarchy | H1 → H2 → H3, no levels skipped | H1 jumping to H3, decorative divs used as headings |
| All images have alt text | Descriptive alt on content images; `alt=""` on decorative | Missing alt attributes |
| Images have width + height | Declared dimensions on every `<img>` | Undeclared dimensions (causes layout shift) |
| Open Graph tags complete | og:title, og:description, og:image, og:url all present | Any OG tag missing |
| Twitter Card tags complete | twitter:card, twitter:title, twitter:description, twitter:image | Any Twitter tag missing |
| Structured data present | JSON-LD with Organization + WebPage minimum | No structured data |
| Images are WebP or AVIF | Modern formats for all photos | JPG/PNG without WebP fallback |
| Lazy loading on images | `loading="lazy"` below fold; `loading="eager"` on hero | All images lazy or all eager |
| Internal links use descriptive anchor text | `Learn about intent data` not `click here` | Generic anchor text like "here", "read more", "click" |
| URL is clean | Lowercase, hyphens, no parameters | Uppercase, underscores, query strings without canonical |

---

### 12. CHANNEL-SPECIFIC SPOT CHECKS

**Slides (Google Slides / PPTX):**
- [ ] **All** slide backgrounds are white `#FFFFFF` — every slide without exception
- [ ] **All** text is left-aligned — no centered text on any slide
- [ ] H1/Title is Poppins Bold 32pt, Navy `#061947`
- [ ] Body copy is Inter Regular 12–14pt, Dark Grey `#1E293B`
- [ ] Gradient and navy appear only in the footer bar — never as a slide background
- [ ] Every slide has a navy footer bar with "Confidential", logo, and page number
- [ ] CTA buttons use Electric Blue `#0266F7` pill — not navy, grey, or off-palette

**Web:**
- [ ] Page background is white
- [ ] Gradient appears only in hero/divider/closing bands
- [ ] Hero is left-aligned H1 with visual on the right
- [ ] Navigation has Electric Blue pill CTA

**Docs & PDFs:**
- [ ] 1" margins maintained
- [ ] No justified paragraphs
- [ ] Callout boxes use cool grey or blue-light backgrounds
- [ ] Page numbers and "Confidential" in footer

---

## Common Violations — Quick Reference

| Violation | Fix |
|-----------|-----|
| Off-palette CTA color used | Replace with `#0266F7` (Electric Blue) for all CTA buttons |
| Wrong font (Montserrat, Lato, etc.) | Replace with Poppins (headings) or Inter (body) |
| Centered body text | Left-align |
| Icon from Font Awesome / Heroicons | Replace with Google Material Symbols Rounded equivalent |
| Off-palette color (#333, #ccc, etc.) | Map to nearest approved neutral |
| Heavy card shadow | Replace with `0 2px 40px rgba(0,0,0,0.10)` |
| Sharp-cornered cards | Add 10px border radius |
| Navy-only or off-palette CTA button | Replace with Electric Blue `#0266F7` pill |
| Justified paragraph text | Set to left-align |
| White text on white or near-white | Darken background or use `#1E293B` text |
| Gradient as default background | Replace with white; reserve gradient for hero/dividers/closing |
| Old hex values (#05195F, #0066FC, #E8F2FF) | Update to official values: #061947, #0266F7, #CDEDFD |
| Subject looking at camera in photo | Replace with authentic, candid professional photography |
| More than 4 UI elements in one illustration | Reduce to 3–4 max |

---

## Version History

| Version | Date       | Change                        |
|---------|------------|-------------------------------|
| 2.0     | 2026-03-25 | Removed CTA Red/Pink Light; updated CTA color to Electric Blue; Poppins weights to SemiBold 600 for H1–H5 |
| 1.0     | 2026-03-25 | Initial brand police document |
