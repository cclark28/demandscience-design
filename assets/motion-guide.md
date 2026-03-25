---
name: DS Motion Guide
description: DemandScience motion system — easing curves, duration tokens, transition patterns, and principles. Sourced from Material Design 3 motion spec and adapted for DemandScience brand.
version: 1.0
last-updated: 2026-03-25
---

# DemandScience Motion System

Motion is a communication tool, not decoration. Every animation at DemandScience must have a reason: revealing content, guiding attention, confirming an action, or expressing spatial relationships.

---

## Core Principles

### 1. Motion Has Meaning
Every animation communicates something. If removing an animation would make the product harder to understand, it earns its place. If it just looks cool — cut it.

### 2. Motion Is Responsive
UI reacts to input immediately. Feedback animations start within 100ms of the triggering event. Never make a user wait for an animation to finish before they can act.

### 3. Motion Is Natural
Animations follow physical world logic. Elements decelerate as they arrive (they don't snap). They accelerate as they leave (they don't linger). Nothing floats or bounces without purpose.

### 4. Motion Is Focused
One thing moves at a time. Simultaneous competing animations split attention and create cognitive noise. Choreograph sequences so the eye always knows where to look.

### 5. Motion Respects Users
Always honour `prefers-reduced-motion`. Non-essential animation must be disabled. Essential feedback (loading, error states) may use reduced forms.

---

## Easing Curves

Sourced from Material Design 3. All values are `cubic-bezier(x1, y1, x2, y2)`.

### Emphasized — Primary Brand Easing
Use for primary brand transitions: hero reveals, section entrances, modal opens, primary CTA interactions.

| Token | Curve | Use |
|-------|-------|-----|
| `--ease-emphasized`            | `cubic-bezier(0.2, 0, 0, 1.0)`    | General emphasized transitions |
| `--ease-emphasized-decelerate` | `cubic-bezier(0.05, 0.7, 0.1, 1.0)` | **Enter** — elements arriving into view |
| `--ease-emphasized-accelerate` | `cubic-bezier(0.3, 0, 0.8, 0.15)` | **Exit** — elements leaving view |

**Personality:** Dramatic, confident, brand-forward. The slight overshoot quality of `0, 0, 0, 1.0` gives the end state authority.

### Standard — UI Easing
Use for UI state changes: tab switches, menu opens, hover states, accordion toggles.

| Token | Curve | Use |
|-------|-------|-----|
| `--ease-standard`            | `cubic-bezier(0.2, 0, 0, 1)`   | General UI transitions |
| `--ease-standard-decelerate` | `cubic-bezier(0, 0, 0, 1)`     | **Enter** — UI element arriving |
| `--ease-standard-accelerate` | `cubic-bezier(0.3, 0, 1, 1)`   | **Exit** — UI element leaving |

**Personality:** Functional, clean, neutral. Does the job without drawing attention to itself.

### Linear — Special Cases Only
| Token | Curve | Use |
|-------|-------|-----|
| `--ease-linear` | `cubic-bezier(0, 0, 1, 1)` | Color/opacity crossfades where curve would look wrong. Loading progress bars. |

**Warning:** Never use linear easing for positional or scale transitions — it reads as mechanical and cheap.

---

## Duration Tokens

Aligned to Material Design 3 duration scale. Use CSS custom properties.

```css
/* Short — micro-interactions, hover states, icon changes */
--dur-short-1: 50ms;
--dur-short-2: 100ms;
--dur-short-3: 150ms;
--dur-short-4: 200ms;

/* Medium — component transitions, drawers, tooltips */
--dur-medium-1: 250ms;
--dur-medium-2: 300ms;
--dur-medium-3: 350ms;
--dur-medium-4: 400ms;

/* Long — page transitions, full-screen elements, complex sequences */
--dur-long-1: 450ms;
--dur-long-2: 500ms;
--dur-long-3: 550ms;
--dur-long-4: 600ms;

/* Extra Long — hero reveals, onboarding sequences, loaders */
--dur-xlong-1: 700ms;
--dur-xlong-2: 800ms;
--dur-xlong-3: 900ms;
--dur-xlong-4: 1000ms;
```

### When to Use Each Category

| Category | Duration Range | Examples |
|----------|---------------|----------|
| Short    | 50–200ms      | Button hover, icon swap, tooltip appear, focus ring |
| Medium   | 250–400ms     | Card hover lift, dropdown open, badge appear, nav highlight |
| Long     | 450–600ms     | Modal enter, panel slide, page section reveal |
| Extra Long | 700ms+      | Hero entrance, full-page transition, onboarding step |

**Rule:** Larger elements move slower. A button state change is 150ms. A full hero section reveal is 600–700ms. Scale duration with the visual weight of the element.

---

## Transition Patterns

### Fade Up (Primary Reveal)
Used for: section content reveals on scroll, card entrances.
```css
@keyframes ds-fade-up {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
/* Usage */
animation: ds-fade-up var(--dur-long-1) var(--ease-emphasized-decelerate) both;
```

### Scale In (Modal / Overlay Enter)
Used for: modals, tooltips, dropdown menus appearing.
```css
@keyframes ds-scale-in {
  from { opacity: 0; transform: scale(0.92); }
  to   { opacity: 1; transform: scale(1); }
}
animation: ds-scale-in var(--dur-medium-2) var(--ease-emphasized-decelerate) both;
```

### Slide In (Panel / Drawer Enter)
Used for: side panels, drawers, flyouts entering from edge.
```css
@keyframes ds-slide-in-right {
  from { opacity: 0; transform: translateX(20px); }
  to   { opacity: 1; transform: translateX(0); }
}
animation: ds-slide-in-right var(--dur-medium-3) var(--ease-emphasized-decelerate) both;
```

### Fade Through (Cross-Fade with Scale)
Used for: tab content swap, slide transitions, content replacement.
```css
/* Exit first, then enter — stagger by 50ms */
/* Exit: */  opacity: 1→0, scale: 1→0.96, dur: 100ms, ease: --ease-standard-accelerate
/* Enter: */ opacity: 0→1, scale: 0.96→1, dur: 300ms, ease: --ease-emphasized-decelerate
```

### Hover Lift (Cards and Buttons)
```css
transition: transform var(--dur-short-4) var(--ease-standard),
            box-shadow var(--dur-short-4) var(--ease-standard);
/* Hover */
transform: translateY(-3px);
box-shadow: 0 8px 32px rgba(0,0,0,.12);
```

---

## Stagger Rules

When multiple elements animate in sequence (card grids, list items), stagger by 40–60ms per item. Never stagger more than 6 items — after 6 the delay becomes tedious.

```css
/* Card grid stagger example */
.card:nth-child(1) { animation-delay: 0ms; }
.card:nth-child(2) { animation-delay: 50ms; }
.card:nth-child(3) { animation-delay: 100ms; }
.card:nth-child(4) { animation-delay: 150ms; }
/* Stop staggering after 4–6 items */
```

---

## Spatial Relationships

Motion communicates where things come from and go to. Use direction to teach the user your UI's spatial model:

| Navigation action | Motion direction |
|-------------------|-----------------|
| Go deeper / forward | Elements slide left |
| Go back | Elements slide right |
| Open overlay / modal | Scale in from center |
| Dismiss overlay | Scale out + fade |
| Expand / accordion open | Slide down |
| Collapse / accordion close | Slide up |

---

## What Never Moves

- Text never rotates, spins, or scales during reading
- Data tables never animate row reorder without user action
- Charts animate once on enter — never loop
- Error states appear instantly (≤100ms) — delay creates confusion
- Loading spinners are the only exception to the "no infinite loops" rule

---

## CSS Implementation

Add to every project's base CSS:

```css
:root {
  /* Easing — DemandScience Motion System */
  --ease-emphasized:            cubic-bezier(0.2, 0, 0, 1.0);
  --ease-emphasized-decelerate: cubic-bezier(0.05, 0.7, 0.1, 1.0);
  --ease-emphasized-accelerate: cubic-bezier(0.3, 0, 0.8, 0.15);
  --ease-standard:              cubic-bezier(0.2, 0, 0, 1);
  --ease-standard-decelerate:   cubic-bezier(0, 0, 0, 1);
  --ease-standard-accelerate:   cubic-bezier(0.3, 0, 1, 1);
  --ease-linear:                cubic-bezier(0, 0, 1, 1);

  /* Duration tokens */
  --dur-short-1: 50ms;   --dur-short-2: 100ms;
  --dur-short-3: 150ms;  --dur-short-4: 200ms;
  --dur-medium-1: 250ms; --dur-medium-2: 300ms;
  --dur-medium-3: 350ms; --dur-medium-4: 400ms;
  --dur-long-1: 450ms;   --dur-long-2: 500ms;
  --dur-long-3: 550ms;   --dur-long-4: 600ms;
  --dur-xlong-1: 700ms;  --dur-xlong-2: 800ms;
  --dur-xlong-3: 900ms;  --dur-xlong-4: 1000ms;
}

/* Reduce motion — always include */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Brand Police — Motion Checks

✓ Animation has a functional purpose (not purely decorative)
✓ Duration matches element size (small = short, large = long)
✓ Emphasized easing used for brand-forward transitions
✓ Standard easing used for UI state changes
✓ Linear easing used only for color/opacity crossfades
✓ No infinite loops except loading spinners
✓ No simultaneous competing animations
✓ prefers-reduced-motion respected
✓ Stagger ≤ 6 items, 40–60ms intervals
✓ Motion direction reflects spatial hierarchy

---

## Version History

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-03-25 | Initial — M3 motion spec adapted for DemandScience |
