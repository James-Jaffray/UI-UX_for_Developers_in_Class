---
aliases: [calc() Reference Sheet, CSS calc Reference, calc Reference Sheet]
tags: [ui-ux-for-developers, term1, reference-sheet, css, calc, layout, reference]
course: "[[UI-UX for Developers]]"
day: 15
---

# CSS `calc()` Reference Sheet

`calc()` does math inside CSS values. It's the main way to **mix units** (like `%` and `px`) in one value. First used for equal-width flex cards in [[Flexbox Part II|Day 14]]. Related: [[Relative Units]], [[Flexbox]], [[CSS Box Model]].

```css
width: calc(100% - 40px);
```

## Rules (these trip everyone up)

| Rule | Example |
|---|---|
| `+` and `-` **must have spaces** around them | `calc(100% - 20px)` ✅ / `calc(100%-20px)` ❌ |
| `*` and `/` don't require spaces (but use them anyway) | `calc(10px * 3)` |
| For `*`, at least one side must be a plain number | `calc(10px * 3)` ✅ / `calc(10px * 3px)` ❌ |
| For `/`, the right side must be a plain number | `calc(100px / 4)` ✅ |
| You can nest `calc()` or just use parentheses | `calc((100% - 40px) / 3)` |
| Works anywhere a length, percentage, time, angle, or number is allowed | `width`, `margin`, `font-size`, `rotate`, etc. |

---

## 1. Mixing Different Units

The #1 use case. You can't do this any other way in CSS.

```css
/* Full width minus fixed sidebar */
.main { width: calc(100% - 250px); }

/* Full viewport height minus a fixed header */
.content { height: calc(100vh - 64px); }

/* Margin that's partly relative, partly fixed */
.box { margin-left: calc(5% + 10px); }
```

## 2. Layout Columns & Gutters

```css
/* Three equal columns with 20px gaps */
.col { width: calc((100% - 40px) / 3); }

/* Two columns with a gap */
.half { width: calc(50% - 10px); }

/* Sidebar + content without flex/grid */
.sidebar { width: 300px; }
.content { width: calc(100% - 300px); }
```

## 3. Full-Height Sections (Sticky Header/Footer)

```css
.page-body {
  min-height: calc(100vh - var(--header-h) - var(--footer-h));
}
```

## 4. Centering & Positioning

```css
/* Center an element of known width */
.modal {
  position: absolute;
  left: calc(50% - 150px); /* half of a 300px width */
  top: calc(50% - 100px);  /* half of a 200px height */
}

/* Offset from the right edge */
.badge { left: calc(100% - 30px); }
```

> Modern note: `transform: translate(-50%, -50%)` or [[Flexbox]] centering is usually cleaner now (see [[Flexbox Reference Sheet]]).

## 5. Spacing with Custom Properties (Variables)

`calc()` + `var()` is where it gets powerful. Build a spacing system from one base value.

```css
:root {
  --space: 8px;
}

.card {
  padding: calc(var(--space) * 2);   /* 16px */
  margin-bottom: calc(var(--space) * 3); /* 24px */
}

.tight { gap: calc(var(--space) / 2); } /* 4px */
```

Change `--space` once and everything scales.

## 6. Fluid Typography

Font size that scales with the viewport but has a floor.

```css
/* Base 16px, grows 1px per 100px of viewport width */
h1 { font-size: calc(16px + 1vw); }

/* Classic fluid type formula */
h1 { font-size: calc(1rem + 2vw); }
```

> Better modern version: `clamp(1rem, 1rem + 2vw, 3rem)` (calc often lives inside `clamp()`).

## 7. Negative Values

You can't put `-` directly before a variable, so use calc:

```css
.pull-up { margin-top: calc(var(--space) * -1); }
.shift { transform: translateX(calc(var(--offset) * -1)); }
```

## 8. Aspect Ratio / Proportional Sizing (Legacy)

```css
/* 16:9 box via padding trick */
.video-wrap { padding-top: calc(9 / 16 * 100%); }
```

> Modern replacement: `aspect-ratio: 16 / 9;`

## 9. Combining with Other Functions

`calc()` works with `min()`, `max()`, `clamp()`, and `var()`.

```css
/* Cap width, with side padding */
.container { width: min(1200px, calc(100% - 2rem)); }

/* Never smaller than 300px */
.panel { width: max(300px, calc(50% - 20px)); }

/* Inside clamp */
.title { font-size: clamp(1.5rem, calc(1rem + 3vw), 4rem); }
```

> Quick fact: inside `min()`, `max()`, and `clamp()` you often don't need `calc()` at all. `min(100% - 2rem, 1200px)` works directly.

## 10. Grid & Flexbox Helpers

```css
.grid {
  display: grid;
  grid-template-columns: calc(25% - 10px) 1fr;
}

.item { flex-basis: calc(33.333% - 1rem); }
```

## 11. Transforms, Angles & Time

```css
/* Angles */
.spin { transform: rotate(calc(var(--i) * 30deg)); }

/* Staggered animation delays */
.item { animation-delay: calc(var(--i) * 0.1s); }
```

Great for staggered animations: set `--i` per element (`style="--i: 3"`) and let calc do the rest.

## 12. Border & Outline Tricks

```css
/* Keep total size constant when adding a border */
.btn { padding: calc(1rem - 2px); border: 2px solid; }
```

## 13. Dynamic Scroll Offsets

```css
/* Anchor links don't hide under a sticky header */
section { scroll-margin-top: calc(var(--header-h) + 16px); }
```

## 14. Using `env()` (Notches / Safe Areas on Phones)

```css
.footer { padding-bottom: calc(16px + env(safe-area-inset-bottom)); }
```

## 15. Math with Unitless Numbers

```css
.box { line-height: calc(1.2 + 0.3); }   /* 1.5 */
.x   { flex-grow: calc(2 * 3); }          /* 6 */
.z   { z-index: calc(var(--layer) + 1); }
```

## 16. Color Channels (Modern CSS)

```css
/* Relative color syntax: tweak a channel */
.btn { background: hsl(from var(--brand) h s calc(l + 10)); }

/* Classic HSL with a variable hue */
.item { background: hsl(calc(var(--i) * 40), 70%, 50%); }
```

---

## Where `calc()` Does NOT Work

- **Media query conditions** in older browsers (`@media (min-width: calc(...))` has limited/inconsistent support)
- **Mixing things that can't be added**: `calc(10px + 2s)` is invalid (length + time)
- **Division by a length**: `calc(100px / 2px)` is invalid (older spec; newer CSS typed arithmetic is partly supported)
- **Property names or selectors**: only values

---

## Common Mistakes

| Mistake | Fix |
|---|---|
| `calc(100%-20px)` | `calc(100% - 20px)` (spaces!) |
| `calc(10px * 5px)` | `calc(10px * 5)` |
| `calc(100px / 2px)` | `calc(100px / 2)` |
| `-var(--x)` | `calc(var(--x) * -1)` |
| Forgetting `var()` units | `--space: 8` then `calc(var(--space) * 1px)` |
| Using `calc()` inside `min/max/clamp` unnecessarily | Skip it: `min(100% - 2rem, 600px)` |

---

## When to Reach for `calc()` vs. Alternatives

| Situation | Use |
|---|---|
| Mixing `%` and `px`/`rem` | `calc()` |
| Equal columns/spacing | `grid` / `flex` + `gap` (often better, see [[Flexbox Part II]]) |
| Fluid font size with limits | `clamp()` |
| Constraining a width | `min()` / `max()` |
| Centering | flex / grid / `transform` |
| Scaling a design system from a base | `calc()` + `var()` |
| Aspect ratio | `aspect-ratio` |

---

## Debug Checklist
- [ ] Spaces around `+` and `-`
- [ ] For `*` and `/`, one side is a plain number (and the right side of `/` is always a number)
- [ ] Units are compatible (length with length, time with time)
- [ ] Inside `min()`, `max()` and `clamp()` you may not need `calc()` at all
- [ ] Variable holds a bare number? Multiply by a unit: `calc(var(--space) * 1px)`

---

## Quick Memory Hook

> **`calc()` = "I need to mix units or do math with a variable."** If you're not doing either, there's probably a simpler property.
