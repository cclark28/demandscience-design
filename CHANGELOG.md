# DemandScience Design System — Changelog

Log every update here when you change colors, typography, components, rules, or structure.
Claude reads this file to understand what changed and why.

---

## Format

```
## [vX.X] — YYYY-MM-DD
**Changed:** what was updated
**Why:** reason for the change
**Files affected:** which files were edited
```

---

## [v2.5] — 2026-03-25
**Changed:** CTA Red and Pink Light removed from system · Gradient variants added · Hero animated gradient + entrance animations · Logo corrected to DS-Logo-White.svg · Footer redesigned · Poppins H1–H5 weight standardized to SemiBold (600)
**Color removals:**
  - `--ds-pink: #D42F5B` (CTA Red) — removed from all CSS, docs, components, and checks
  - `--ds-pink-light: #FDF2F4` — removed from all CSS, docs, and components
  - CTA color is now Electric Blue `#0266F7` across all channels
**Gradient additions:**
  - `--ds-gradient-135`, `--ds-gradient-45`, `--ds-gradient-radial`, `--ds-gradient-animated`
  - `@keyframes gradientShift` added to `colors.css`
**Brand site changes:**
  - Hero: slow animated gradient (12s loop) + staggered entrance animations (badge → h1 → p → buttons → stats)
  - Logo: replaced DS icon + text with `DS-Logo-White.svg` in nav and footer
  - Footer: comprehensive redesign — logo, office locations (Burlington MA · London · Singapore), Get in Touch, nav links, back-to-top, copyright
  - All heading weights: 800/700 → SemiBold 600 throughout
  - All button/badge/CTA colors: pink → Electric Blue
  - Brand System version badge updated to v2.5
**Typography:**
  - Poppins H1 and H2: `font-weight: 700` → `font-weight: 600` in `type-scale.css`, brand site, and all channel guides
  - `ds-ui-page-title`: `700` → `600`
**Files affected:** assets/colors.css, assets/type-scale.css, brand-guide/brand-site.html, ds-brand-design.md, ds-brand-police.md, channel-guides/google-slides.md, channel-guides/web.md, channel-guides/docs.md, CHANGELOG.md

---

## [v2.4] — 2026-03-25
**Changed:** Brand site fully redesigned · Capabilities deck ingested
**New brand-site.html features:**
  - Sticky sidebar navigation (Dropbox brand site-inspired structure)
  - DS System 4-pillar section: Gather / Resonate / Orchestrate / Win (from capabilities deck)
  - Live stats from deck: 207K+ intent topics, 247M+ contacts, 51B+ behaviors, <3% ad fraud
  - Scroll reveal animations, copy-to-clipboard swatches, motion playback demos
  - Full governance terminal block, contact strip, responsive layout
**Ingested:** `26-DemandScience-Global-Capabilities-Deck.pptx` — 127 slides; product messaging, stats, and system framing added to brand site and voice content
**Pushed live:** https://github.com/cclark28/demandscience-design
**Files affected:** brand-guide/brand-site.html, CHANGELOG.md

---

## [v2.3] — 2026-03-25
**Changed:** Brand governance and enforcement system added
**New files:**
  - governance/brand-enforcement.md — STOP triggers, STOP message format, escalation protocol
  - governance/design-review-process.md — how to submit for design review and what to expect
  - governance/approved-use-cases.md — quick reference for what needs approval vs. what doesn't
**Updated:** ds-brand-police.md — STOP message block added at the top · STOP trigger table added · Two-tier enforcement (STOP vs. WARNING) formalized
**Updated:** INSTRUCTIONS.md — governance section added
**Behavior:** Claude now checks for STOP conditions before starting any DemandScience design task. Work halts completely on any STOP trigger until Design approves.

---

## [v2.2] — 2026-03-25
**Changed:** Grid system added · HTML slide template created · Google Sheets CSV files created
**New files:**
  - assets/grid-system.md — 8px base unit grid spec for slides, web, and docs
  - templates/google-slides/ds-slide-template.html — 14-slide HTML template (open in browser, print to PDF)
  - templates/google-sheets/ds-colors.csv — import into Google Sheets
  - templates/google-sheets/ds-fonts.csv — import into Google Sheets
  - templates/google-sheets/ds-icons.csv — import into Google Sheets
**Slide template includes:** Cover · Instructions · Grid reference · Colors · Typography · Icons · Agenda · Section divider · Full-width text · Two-column · Stats · Card grid · Quote · Closing
**Files affected:** INSTRUCTIONS.md updated to reference new files

---

## [v2.1] — 2026-03-25
**Changed:** Slide-specific rules updated
**Rules:**
  - All slide backgrounds are white `#FFFFFF` — every slide, no exceptions
  - All text on slides is left-aligned — no centered text anywhere
  - H1/Title: Poppins Bold 32pt (was 38pt)
  - Body copy: Inter Regular 12–14pt (was 14pt fixed)
  - Gradient and navy restricted to footer bar only — never a slide background
**Files affected:** channel-guides/google-slides.md, ds-brand-design.md, ds-brand-police.md

---

## [v2.0] — 2026-03-25
**Changed:** Major update — synced all files with official 25-DS-BrandGuide-General.pdf
**Why:** Official brand guide PDF contained authoritative hex values and brand content that differed from initial setup
**Color corrections:**
  - Navy: `#05195F` → `#061947` (PDF: Navy Blue)
  - Electric Blue: `#0066FC` → `#0266F7` (PDF: Electric Blue)
  - Baby Blue: `#E8F2FF` → `#CDEDFD` (PDF: Baby Blue)
  - CTA: `#D52C5A` → `#D42F5B` (PDF: Red)
  - Gradient: updated to use corrected navy + blue
**Slide type sizes corrected:** Title 38pt, Headlines 24pt, Subheadings 18pt, Body 14pt
**New content added from PDF:** Mission, Vision, Tone of Voice, Core Brand Message, Elevator Pitches, Design Do's & Don'ts, Illustrations & UI Elements rules
**New file:** `content/voice-and-tone.md`
**Files affected:** ds-brand-design.md, assets/colors.css, assets/type-scale.css, channel-guides/google-slides.md, ds-brand-police.md, brand-guide/index.html

---

## [v1.2] — 2026-03-25
**Changed:** Added brand guide web page
**Why:** Living HTML page for internal teams and partners to access brand standards and download assets
**Files affected:** brand-guide/index.html (new), brand-guide/README.md (new)

---

## [v1.1] — 2026-03-25
**Changed:** Added complete SEO standards guide
**Why:** All DemandScience web pages must meet modern SEO requirements — technical, on-page, performance, and structured data
**Files affected:** channel-guides/seo.md (new), channel-guides/web.md (SEO reference added), ds-brand-police.md (SEO check category added)

---

## [v1.0] — 2026-03-25
**Changed:** Initial design system created
**Why:** Establish single source of truth for all DemandScience brand assets
**Files affected:** ds-brand-design.md, ds-brand-police.md, assets/colors.css, assets/type-scale.css, assets/icons-reference.md, channel-guides/google-slides.md, channel-guides/web.md, channel-guides/docs.md
