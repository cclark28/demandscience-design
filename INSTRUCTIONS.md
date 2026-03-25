---
name: Design System Instructions
description: How to use, update, and communicate changes in the DemandScience design system folder.
---

# DemandScience Design System — Instructions

This folder is the single source of truth for all DemandScience visual design. These instructions explain how to use it, how to update it, and how to work with Claude.

---

## Folder Structure

```
demandscience-design/
│
├── INSTRUCTIONS.md             ← you are here
├── CHANGELOG.md                ← log every update here
├── ds-brand-design.md          ← master brand rules (colors, type, layout, components)
├── ds-brand-police.md          ← mandatory validator — runs on every output
│
├── assets/
│   ├── colors.css              ← all CSS color variables
│   ├── type-scale.css          ← all typography classes
│   ├── icons-reference.md      ← icon library rules and approved icon list
│   ├── motion-guide.md         ← animation principles, easing tokens, duration scale
│   └── grid-system.md          ← layout grid, spacing system, breakpoints
│
├── channel-guides/
│   ├── google-slides.md        ← rules specific to Google Slides / PPTX
│   ├── web.md                  ← rules specific to web and landing pages
│   ├── docs.md                 ← rules specific to docs and PDFs
│   └── seo.md                  ← SEO requirements for web pages
│
├── content/
│   └── voice-and-tone.md       ← brand voice, tone, messaging, elevator pitches
│
├── governance/
│   ├── brand-enforcement.md    ← STOP rules and escalation protocol
│   ├── design-review-process.md← how design reviews work
│   └── approved-use-cases.md   ← what can be created without design approval
│
└── templates/
    ├── google-slides/          ← drop reference deck screenshots or PDFs here
    ├── docs/                   ← drop reference doc examples here
    └── web/                    ← drop reference web page screenshots here
```

---

## How Claude Uses This Folder

At the start of every DemandScience task, Claude:

1. Reads `ds-brand-design.md` — the master rules
2. Reads `ds-brand-police.md` — the validation checklist
3. Reads the relevant channel guide (slides, web, or docs)
4. Checks the `templates/` folder for any reference files you have added
5. Runs the brand police check against every output before delivering it

Every output will include either:
```
✓ Brand police check passed — all systems go.
```
or:
```
⚠ BRAND VIOLATION — [Category]
   Found:    [what was used]
   Rule:     [what the rule says]
   Fix:      [what to replace it with]
```

---

## How to Update the Design System

### Option 1 — Tell Claude in plain English (fastest)
Just describe the change in the chat:
> *"Change the primary button radius from 100px to 48px"*
> *"Add a new neutral color — Slate #475569"*
> *"Update the H1 size from 50px to 44px"*

Claude will edit the correct files, bump the version number, and log the change in `CHANGELOG.md`.

### Option 2 — Edit the files directly
1. Open the relevant file and make your changes
2. Bump the version in the file's frontmatter (e.g. `version: 1.0` → `version: 1.1`)
3. Add an entry to `CHANGELOG.md` (see format below)
4. At the start of your next Claude session, say: *"I've updated the design system"* — Claude will re-read everything before starting work

---

## How to Log Changes (CHANGELOG.md)

Every update — no matter how small — should be logged:

```
## [v1.1] — YYYY-MM-DD
**Changed:** what was updated
**Why:** reason for the change
**Files affected:** which files were edited
```

---

## How to Add Reference Material

Drop files into the relevant `templates/` subfolder:

| What you're adding | Where to drop it |
|--------------------|------------------|
| Approved Google Slides deck (PDF or screenshots) | `templates/google-slides/` |
| Approved doc or one-pager (PDF) | `templates/docs/` |
| Web page screenshots | `templates/web/` |

**Naming convention:** `descriptor_slide-type.png`
Examples: `q1-deck_cover.png`, `sales-one-pager_full.pdf`, `homepage_hero.png`

After dropping a file, tell Claude:
> *"I've added a reference deck to templates/google-slides — please read it and update the channel guide."*

---

## Governance & Stop Rules

Design requests that violate brand standards are **blocked**. A full STOP message is issued and work does not proceed until the Design team reviews and approves.

**STOP triggers include:** Non-approved icon libraries · Off-palette colors · Non-brand fonts · CTA Red used decoratively · Charts with default tool colors · New logo treatments · Public-facing assets without approved templates · Unclear or ambiguous external-use requests.

**To get approval:** Email Marketing@demandscience.com or post in #design-team on Slack.

Full governance rules: `governance/brand-enforcement.md`
Approval process: `governance/design-review-process.md`
What's approved without review: `governance/approved-use-cases.md`

---

## Rules for Everyone

- **Never add colors outside the approved palette.** If a new color is needed, propose it and update `assets/colors.css` and `ds-brand-design.md` together.
- **Never use fonts other than Poppins and Inter.** No exceptions.
- **Never use icons outside Google Material Symbols Rounded.** No other libraries.
- **Red Orange `#F40356` is for hero and major nav CTAs only. Electric Blue `#0266F7` is for all other CTAs, links, and interactive states.**
- **When in doubt, left-align it.**
- **When in doubt, add more whitespace.**

---

## Quick Reference — Who to Ask

| Question | File to check |
|----------|---------------|
| What color do I use? | `ds-brand-design.md` §2 or `assets/colors.css` |
| What font size? | `ds-brand-design.md` §3 or `assets/type-scale.css` |
| Which icon? | `assets/icons-reference.md` |
| How do I lay out a slide? | `channel-guides/google-slides.md` |
| How do I build a web section? | `channel-guides/web.md` |
| How do I format a doc? | `channel-guides/docs.md` |
| Is this design on-brand? | `ds-brand-police.md` |
| What changed recently? | `CHANGELOG.md` |
