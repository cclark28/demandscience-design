---
name: DemandScience Icon Reference
description: Approved icon library, import method, and common icon name list for all DS materials.
---

# DemandScience Icon Reference

## Library

**Google Material Symbols — Rounded style only.**

All DemandScience assets (public and internal) use this exclusively.
No other icon libraries (Font Awesome, Heroicons, Feather, etc.) are permitted.

Browse: https://fonts.google.com/icons?icon.style=Rounded

---

## Web Import

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
```

## Usage

```html
<span class="material-symbols-rounded">arrow_forward</span>
```

---

## Styling Rules

| Property   | Rule                                                                 |
|------------|----------------------------------------------------------------------|
| Style      | Rounded **only**                                                     |
| Color      | Navy `#05195F` or Blue `#0066FC`; avoid pink and off-palette tones  |
| Size       | Match surrounding text; common sizes: 20px, 24px, 32px, 48px       |
| Fill       | `FILL=0` default; `FILL=1` for active/selected states only          |
| Weight     | 400 default; 300 for small/compact layouts                          |
| Background | On white: small cool grey or blue-light circle when anchoring needed |

---

## Common Icons — Add to this list as the system grows

Add icon names here as they get approved and used across materials.
Format: `icon_name` — use case

### Navigation & UI
- `arrow_forward` — CTAs, next steps
- `arrow_back` — back navigation
- `close` — dismiss/close
- `menu` — mobile nav
- `expand_more` — dropdowns, accordions
- `chevron_right` — list items, breadcrumbs
- `open_in_new` — external links

### Data & Analytics
- `bar_chart` — charts, reporting
- `trending_up` — growth, performance
- `analytics` — dashboards
- `insights` — data insights
- `query_stats` — statistics

### Business & People
- `groups` — team, audience
- `handshake` — partnerships
- `business_center` — enterprise
- `person` — individual user
- `badge` — identity, credentials

### Actions
- `download` — file downloads
- `upload` — file uploads
- `share` — sharing
- `edit` — editing
- `delete` — remove (use `--ds-red-orange` for destructive)
- `search` — search
- `filter_list` — filtering

### Status & Feedback
- `check_circle` — success
- `error` — error/critical (use `--ds-red-orange`)
- `warning` — warning
- `info` — informational
- `notifications` — alerts

---

## Adding New Icons

When you identify a new icon needed across materials:
1. Find the Rounded version at https://fonts.google.com/icons?icon.style=Rounded
2. Add it to the relevant section above with its use case
3. Note if a specific color or fill treatment applies
