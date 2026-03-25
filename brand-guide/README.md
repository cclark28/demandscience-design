---
name: Brand Guide Web Page
description: Living HTML brand guide page — how to maintain and update it when the brand changes.
---

# Brand Guide Web Page

`index.html` is the public-facing (or internal) brand guide page. It is a single self-contained HTML file that showcases the full DemandScience design system and provides asset downloads.

---

## How to Update When the Brand Changes

When any brand element changes, update BOTH the source `.md` files AND this HTML page.

### Color change
1. Update `assets/colors.css` and `ds-brand-design.md`
2. In `index.html`, find the relevant color swatch block and update:
   - The `style="background:#XXXXXX"` on the `.color-swatch-block` div
   - The `onclick="copyColor('#XXXXXX', this)"` on the `.color-swatch`
   - The `.color-swatch-hex` text
   - The `.color-swatch-name` and `.color-swatch-usage` if the role changed
3. Update the `:root` CSS variables at the top of `index.html`
4. Update the version number and date in the update banner and footer
5. Log the change in `CHANGELOG.md`

### Typography change
1. Update `assets/type-scale.css` and `ds-brand-design.md`
2. In `index.html`, find the `.type-row` for that level and update the inline styles
3. Update version and log in `CHANGELOG.md`

### New component
1. Add it to `ds-brand-design.md` first
2. Add a demo block in the `#components` section of `index.html`
3. Add CSS in the `<style>` block following existing naming conventions
4. Update version and log in `CHANGELOG.md`

### New downloadable asset
1. Add the file to the `brand-guide/assets/` subfolder
2. Add a `.download-file` link in the correct `.download-card` in `index.html`
3. Update version and log in `CHANGELOG.md`

---

## Update Banner

The yellow banner at the very top of the page shows the current version and date.
Update this line whenever anything changes:

```html
<div class="update-banner">
  <strong>Brand Guide v1.1</strong> — Last updated March 25, 2026 &nbsp;·&nbsp; Questions? Contact the Brand Team
</div>
```

Also update the footer version line:
```html
<span>Brand Guide v1.1 · Updated March 25, 2026</span>
```

---

## Asset Folder Structure

```
brand-guide/
├── index.html              ← the page
├── README.md               ← this file
└── assets/
    ├── logos/              ← SVG and PNG logo files
    ├── colors/             ← ASE and Figma JSON color files
    ├── fonts/              ← font import snippets
    ├── templates/          ← PPTX and DOCX templates
    └── ds-brand-guidelines.pdf
```

---

## Hosting

This page can be:
- Opened locally in any browser (drag `index.html` into Chrome/Safari)
- Hosted on an internal server or Notion embed
- Deployed to a simple static host (Netlify, GitHub Pages, Vercel) for team-wide access

When hosted publicly, update the `<meta name="robots">` tag from `noindex, nofollow` to `index, follow`.
