---
name: Brand Enforcement & Governance
description: Stop rules, escalation protocol, and design approval requirements. Any request that triggers a STOP must be reviewed by the Design team before work proceeds.
version: 1.1
last-updated: 2026-03-25
---

# DemandScience Brand Enforcement

This document defines what Claude and any team member must do when a design request violates brand standards or requires design approval before it can be built, shared, or published.

**This is not optional guidance. It is a governance requirement.**

---

## The STOP Message

When a request triggers a STOP condition, work halts completely. The following message is issued:

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

## STOP Conditions — Full Block (No Exceptions)

Work **cannot proceed** under any circumstances without Design team approval when any of the following are present:

### 1. Icon Violations
- Requesting icons from any library other than Google Material Symbols Rounded
- Using Font Awesome, Heroicons, Feather, Lucide, Flaticon, or any third-party icon set
- Creating custom icon designs not sourced from the approved library
- Using icons in off-brand colors (anything other than Navy `#061947` or Electric Blue `#0266F7`)
- Using Outlined, Sharp, or Two-tone Material icon variants

### 2. Color Violations
- Using any hex value not in the approved palette
- Using the gradient as a full slide or page background
- Using warm greys, beige, brown, or any off-palette neutral
- Using competitor brand colors in any DemandScience-branded asset
- Applying colors from memory or "approximately matching" without using exact hex values

### 3. Typography Violations
- Using any font other than Poppins or Inter
- Using Montserrat, Lato, Open Sans, Roboto, or any other typeface
- Mixing more than two font families in a single asset
- Centering body text or bullet points on slides or documents
- Using italic for general emphasis (bold only)

### 4. Public-Facing Assets Without Template
- Creating any external-facing presentation, document, or graphic that:
  - Does not use an approved DemandScience template
  - Has not been reviewed by the Design team
  - Includes new visual styles, layouts, or components not in this design system
- Publishing or sharing anything described as "for clients", "for prospects", or "for the public" that was not built on an approved template

### 5. Unauthorized Brand Extensions
- Creating new logo variants, logo lockups, or logo treatments
- Modifying or recreating the DemandScience logo in any way
- Creating sub-brand logos, event logos, or product logos without Design approval
- Combining the DemandScience brand with partner or sponsor brands without approval

### 6. Off-System Chart & Data Visualization Requests
- Building charts or data visuals that use colors outside the approved chart order:
  `Navy #061947 → Electric Blue #0266F7 → Medium Grey #64748B → Dark Grey #1E293B`
- Charts with colored or gradient backgrounds (white only)
- Data visuals that use random, default tool colors (Google Sheets default palette, Excel default palette, etc.)
- Infographics that use non-brand colors or non-brand fonts

### 7. Sensitive or Ambiguous Context
- Any request to create materials where the intended use is unclear or unspecified
- Materials that include client data, financial data, or confidential information without explicit authorization
- Any asset described as "quick", "informal", or "just for now" that appears destined for external sharing
- Materials for channels or audiences not covered by an existing channel guide

---

## WARNING Conditions — Flag and Correct Before Proceeding

These issues are flagged with a `⚠ BRAND WARNING` but work can continue if the issue is corrected:

```
⚠ BRAND WARNING — [Category]
   Issue:    [what was found]
   Rule:     [what the standard says]
   Fix:      [what to change]
   Status:   Corrected before proceeding ✓
```

| Warning trigger | What to do |
|-----------------|-----------|
| Minor spacing off the 8px grid | Correct to nearest 8px multiple |
| Body text slightly off type scale | Correct to defined scale |
| Caption size inconsistent | Correct to 9pt / 12px |
| Image without rounded corners | Apply 10px radius |
| Missing footer on a slide | Add the navy footer bar |
| Alt text missing on web image | Add descriptive alt text |
| Soft shadow slightly too heavy | Correct to `0 2px 40px rgba(0,0,0,0.10)` |

---

## What Does NOT Require Design Approval

The following can be created freely using the existing system without escalation:

- ✅ Presentations using the approved slide template with standard layouts
- ✅ Documents using the approved typography, colors, and margins
- ✅ Charts and data visuals using the approved chart color order on white backgrounds
- ✅ Icons selected from Google Material Symbols Rounded in Navy or Electric Blue
- ✅ Internal assets (briefs, reports, trackers) using the approved color and type system
- ✅ Web pages built using the approved component library and design tokens
- ✅ Email content using the approved email template structure

---

## Escalation Protocol

When a STOP is triggered:

### Step 1 — Stop all work
Do not proceed with the design task. Do not share partial work.

### Step 2 — Document the request
Record exactly what was requested and what rule it violated.

### Step 3 — Contact Design
| Channel | Contact |
|---------|---------|
| Email | Marketing@demandscience.com |
| Slack | #design-team |
| Urgent | Tag the Design Lead directly in Slack |

### Step 4 — Wait for written approval
Design will respond with one of:
- **Approved** — proceed using the approved direction provided
- **Approved with modifications** — proceed using the specific changes noted
- **Rejected** — do not proceed; Design will provide an alternative approach
- **Escalated** — requires additional stakeholder review before decision

### Step 5 — Document the outcome
Log the approval or rejection in the asset's changelog or brief.

---

## Who Enforces This

| Role | Responsibility |
|------|---------------|
| **Claude** | Issues STOP messages automatically on any STOP-condition request. Does not complete work until resolved. |
| **Design team** | Reviews escalated requests. Issues written approvals. |
| **All team members** | Responsible for submitting requests through proper channels. Not permitted to override STOP conditions. |
| **Marketing** | Final authority on brand decisions when Design escalates. |

---

## Version History

| Version | Date | Change |
|---------|------|--------|
| 1.1 | 2026-03-25 | Removed CTA Red references; updated chart color order; synced with v2.6 |
| 1.0 | 2026-03-25 | Initial brand enforcement document |
