---
name: SEO Standards Guide
description: Complete modern SEO requirements for all DemandScience web properties — technical, on-page, performance, and structured data.
version: 1.0
last-updated: 2026-03-25
---

# DemandScience SEO Standards

Every web page and landing page produced for DemandScience must meet these standards. SEO is not an afterthought — it is built into the page structure from the first line of HTML.

Reference `channel-guides/web.md` for visual layout rules. This file governs everything search engines see.

---

## 1. Page `<head>` — Required Tags

Every page must include all of the following. No exceptions.

```html
<head>
  <!-- Character set and viewport (always first) -->
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- Primary SEO -->
  <title>Page Title — DemandScience</title>
  <meta name="description" content="150–160 character description of this specific page." />
  <link rel="canonical" href="https://www.demandscience.com/page-url/" />

  <!-- Robots -->
  <meta name="robots" content="index, follow" />

  <!-- Open Graph (social sharing — LinkedIn, Facebook, Slack previews) -->
  <meta property="og:type" content="website" />
  <meta property="og:title" content="Page Title — DemandScience" />
  <meta property="og:description" content="150–160 character description." />
  <meta property="og:url" content="https://www.demandscience.com/page-url/" />
  <meta property="og:image" content="https://www.demandscience.com/assets/og/page-og-image.png" />
  <meta property="og:image:width" content="1200" />
  <meta property="og:image:height" content="630" />
  <meta property="og:site_name" content="DemandScience" />
  <meta property="og:locale" content="en_US" />

  <!-- Twitter / X Card -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="Page Title — DemandScience" />
  <meta name="twitter:description" content="150–160 character description." />
  <meta name="twitter:image" content="https://www.demandscience.com/assets/og/page-og-image.png" />
  <meta name="twitter:site" content="@DemandScience" />

  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
  <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" />
  <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png" />

  <!-- Fonts (preconnect first for performance) -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet" />
</head>
```

---

## 2. Title Tags

| Rule | Detail |
|------|--------|
| Length | 50–60 characters |
| Format | `Primary Keyword — DemandScience` or `Page Topic \| DemandScience` |
| Uniqueness | Every page has a unique title — no duplicates across the site |
| Keywords | Lead with the most important keyword; brand name at the end |
| No keyword stuffing | One clear topic per title |

**Examples:**
- `B2B Demand Generation Solutions — DemandScience`
- `Intent Data for B2B Marketing \| DemandScience`
- `Content Syndication Platform — DemandScience`

---

## 3. Meta Descriptions

| Rule | Detail |
|------|--------|
| Length | 150–160 characters (Google truncates beyond this) |
| Uniqueness | Every page has a unique description |
| Tone | Active voice, outcome-focused, matches the page content |
| CTA | End with a soft call to action when appropriate |
| No keyword stuffing | Natural language only |

**Example:**
> `Reach in-market B2B buyers with DemandScience's intent-driven demand generation platform. Qualified leads, faster pipeline. See how it works.`

---

## 4. Heading Hierarchy

| Rule | Detail |
|------|--------|
| One H1 per page | The H1 is the page's primary topic — only one |
| H1 contains primary keyword | Naturally, not forced |
| H2s structure main sections | Each H2 targets a secondary keyword or subtopic |
| H3s for sub-sections | Never skip levels (H1 → H3 without H2 is wrong) |
| Headings are semantic | Use real `<h1>`–`<h6>` tags, never styled `<div>` or `<p>` |
| Poppins styling via CSS | Visual styling is CSS only — the HTML tag determines SEO value |

**Correct structure:**
```html
<h1>B2B Demand Generation Platform</h1>
  <h2>Intent-Driven Lead Generation</h2>
    <h3>How Intent Data Works</h3>
    <h3>Targeting In-Market Buyers</h3>
  <h2>Content Syndication</h2>
    <h3>Reach the Right Audience</h3>
```

---

## 5. URL Structure

| Rule | Detail |
|------|--------|
| Lowercase only | `/demand-generation/` not `/Demand-Generation/` |
| Hyphens, not underscores | `/intent-data/` not `/intent_data/` |
| Descriptive and concise | `/content-syndication/` not `/page?id=42` |
| No trailing parameters | Clean URLs; use canonical for dynamic parameters |
| Folder hierarchy reflects site structure | `/solutions/intent-data/` not `/solutions-intent-data/` |
| Canonical on every page | Prevent duplicate content from URL variants |

---

## 6. Image SEO

Every image on every page:

```html
<!-- Correct -->
<img
  src="/assets/images/intent-data-dashboard.webp"
  alt="DemandScience intent data dashboard showing in-market buyer signals"
  width="800"
  height="500"
  loading="lazy"
/>

<!-- Hero/above-fold images: use loading="eager" -->
<img
  src="/assets/images/hero-visual.webp"
  alt="B2B demand generation platform interface"
  width="640"
  height="480"
  loading="eager"
  fetchpriority="high"
/>
```

| Rule | Detail |
|------|--------|
| Alt text required | Every `<img>` has a descriptive `alt` attribute |
| Alt text is descriptive | Describes what is in the image; includes keyword when natural |
| Decorative images | Use `alt=""` (empty, not missing) |
| File names are descriptive | `intent-data-dashboard.webp` not `image-001.webp` |
| Format | WebP primary; AVIF where supported; PNG/JPG fallback |
| Dimensions declared | Always include `width` and `height` to prevent layout shift |
| Lazy loading | `loading="lazy"` on all below-fold images |
| Hero images | `loading="eager"` + `fetchpriority="high"` |
| OG images | 1200×630px, under 1MB, JPG or PNG |

---

## 7. Structured Data (Schema Markup)

Add JSON-LD structured data to every page. Minimum required schemas:

### Organization (site-wide, in `<head>` or before `</body>`)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "DemandScience",
  "url": "https://www.demandscience.com",
  "logo": "https://www.demandscience.com/assets/logo/ds-logo.svg",
  "sameAs": [
    "https://www.linkedin.com/company/demandscience",
    "https://twitter.com/DemandScience"
  ]
}
</script>
```

### WebPage (every page)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Page Title — DemandScience",
  "description": "Page meta description.",
  "url": "https://www.demandscience.com/page-url/",
  "publisher": {
    "@type": "Organization",
    "name": "DemandScience"
  }
}
</script>
```

### Additional schemas by page type

| Page type | Schema to add |
|-----------|--------------|
| Blog post / article | `Article` with `datePublished`, `dateModified`, `author` |
| FAQ section | `FAQPage` with `Question` + `Answer` pairs |
| Product / solution page | `Product` or `Service` |
| Event / webinar | `Event` with date, location, organizer |
| Breadcrumbs | `BreadcrumbList` on all interior pages |

---

## 8. Core Web Vitals & Performance

Google uses Core Web Vitals as a ranking signal. Every DS web page must target:

| Metric | Target | What it measures |
|--------|--------|-----------------|
| LCP (Largest Contentful Paint) | < 2.5s | How fast the main content loads |
| INP (Interaction to Next Paint) | < 200ms | How fast the page responds to interaction |
| CLS (Cumulative Layout Shift) | < 0.1 | How stable the layout is while loading |

**How to achieve these:**

- Declare `width` and `height` on all images and embeds (prevents CLS)
- Use `loading="lazy"` on below-fold images
- Preconnect to Google Fonts (already in head template above)
- Self-host critical CSS inline for above-fold content where possible
- Defer non-critical JavaScript (`defer` or `async` attributes)
- Compress and serve images in WebP/AVIF
- Use a CDN for static assets
- Avoid large layout shifts from fonts — use `font-display: swap`

---

## 9. Mobile-First

| Rule | Detail |
|------|--------|
| Viewport meta tag | Required on every page (in head template above) |
| Touch targets | Minimum 44×44px for all interactive elements |
| Font sizes | Minimum 16px body text on mobile (prevents iOS zoom) |
| No horizontal scroll | Content fits within viewport at all mobile sizes |
| Test on real devices | Chrome DevTools mobile emulation is not a substitute |

---

## 10. Internal Linking

| Rule | Detail |
|------|--------|
| Descriptive anchor text | `Learn about intent data` not `click here` or `read more` |
| Link to relevant pages | Every page links to at least 2–3 related internal pages |
| No orphan pages | Every page is reachable from at least one other page |
| Navigation links | Primary nav and footer cover top-level sections |
| Contextual links | In-body links to related solutions, resources, or blog posts |

---

## 11. Technical SEO Checklist

These must be in place at the site level:

- [ ] `sitemap.xml` exists and is submitted to Google Search Console
- [ ] `robots.txt` is correctly configured — no accidental blocking of key pages
- [ ] HTTPS on all pages — no mixed content warnings
- [ ] 301 redirects in place for any changed or removed URLs
- [ ] No duplicate content — canonical tags on all pages
- [ ] No broken internal links (404s)
- [ ] Hreflang tags if serving multiple languages/regions
- [ ] Google Search Console connected and monitoring

---

## 12. Content SEO Rules

| Rule | Detail |
|------|--------|
| One primary keyword per page | Each page owns one topic — no keyword cannibalization |
| Keyword in H1 | Naturally, not forced |
| Keyword in first 100 words | Establish topic early |
| Keyword in meta title and description | Match search intent |
| Plain language | Write for the reader first; search engines second |
| Minimum content length | Landing pages: 400+ words; blog posts: 800+ words |
| Avoid keyword stuffing | If it reads unnaturally, it is wrong |
| Update stale content | Pages older than 12 months should be reviewed and refreshed |

---

## 13. SEO Pre-Flight Checklist

Before any web page goes live:

- [ ] Unique, keyword-rich title tag (50–60 chars)
- [ ] Unique meta description (150–160 chars)
- [ ] Canonical tag present and correct
- [ ] One H1 with primary keyword
- [ ] Heading hierarchy is logical (H1 → H2 → H3, no skipping)
- [ ] All images have descriptive alt text and declared dimensions
- [ ] Images are WebP/AVIF, lazy loaded (except hero)
- [ ] Open Graph tags complete (title, description, image, URL)
- [ ] Twitter Card tags complete
- [ ] JSON-LD structured data present (Organization + WebPage minimum)
- [ ] Page loads in under 2.5s (test with PageSpeed Insights)
- [ ] No layout shift on load (CLS < 0.1)
- [ ] Mobile layout tested and functional
- [ ] At least 2 internal links with descriptive anchor text
- [ ] URL is lowercase, hyphenated, and descriptive
- [ ] No broken links on the page
