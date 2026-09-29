---
aliases: [UI-UX for Developers - Day 09]
tags: [ui-ux-for-developers, term1, css]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 9: CSS Introduction & Relative Units

> The raw note's heading said "Day 7" but it lives in the Day 09 folder, and the slides don't say a day number — worth double-checking which is right.

**Today's focus:** start styling HTML with CSS — basic selectors, the three ways to add CSS, and relative units (`rem` and `%`) for scalable, responsive design.

## [[CSS]] Basics
CSS = Cascading Style Sheets — it's how we style our HTML. It tells the browser how things should look and how they should be laid out. Today we start applying layout, color, and spacing rules.

**Why use CSS?**
- HTML is for content and structure; CSS is for presentation and visual hierarchy
- Consistency across pages
- Enables accessibility and responsive design (see [[Inclusive Design and WCAG]])

## Ways to Include CSS

| Method | Where it goes | Verdict |
|---|---|---|
| Inline | Inside the tag | Not recommended |
| Internal (embedded) | Inside `<style>` in the `<head>` | Not recommended |
| **External** | Separate `.css` file, linked in the `<head>` | **Best practice** |

> **Course rule: external stylesheets are the ONLY way we style in this class.** Inline and internal are shown for awareness only — don't use them in assignments.

### External Stylesheets
Link it inside the `<head>` (not `<header>`):
```html
<link rel="stylesheet" href="css/styles.css">
```
- `css/styles.css` is the path to the stylesheet in the `css` folder
- We **always** call this sheet `styles.css`
- Benefits: cleaner, easier to maintain, can style multiple pages at once

## Writing CSS: Select It to Affect It
```css
selector {
  property: value;
}
```
```css
p {
  color: red;
}
```

| Term | Meaning | In `p { color: red; }` |
|---|---|---|
| **Selector** | What you want to style | `p` |
| **Property** | What about it you want to change | `color` |
| **Value** | What you want it to be | `red` |
| **Declaration** | property + value | `color: red;` |

### Syntax Rules
- Declarations go inside `{ }` curly braces (this is the CSS syntax)
- Property and value are separated by `:`
- Each declaration ends with `;`
- A rule can have multiple declarations
- Forgetting the `;` is like not closing an HTML tag

## [[CSS Selectors]]

| Type | Syntax | Notes |
|---|---|---|
| Element | `p`, `h1`, `ul` | Targets every matching tag on the page |
| Multiple | `h1, h2` | Target more than one thing at once (comma-separated) |
| Descendant | `header nav ul li a` | Targets nested elements |
| Class | `.classname` | Reusable; **has to be declared in the HTML** |
| ID | `#idname` | Must be unique |

```css
p { font-size: 1rem; }              /* every <p> on the page */

h1,
h2 { font-family: 'Avenir', sans-serif; }

header nav ul li a { text-decoration: none; }

.red-text { color: red; }           /* apply in HTML: <p class="red-text">Hello!</p> */

#main-title { font-size: 2rem; }    /* apply in HTML: <h1 id="main-title">Welcome!</h1> */
```

## [[CSS Cascade and Specificity|The Cascade]]
"Cascading" means that when rules conflict, the **last one written usually wins** — but **specificity matters more**.

Specificity ranking (lowest → highest):
1. Element selectors (`p`, `h1`)
2. Descendant selectors (`ul li a`)
3. Class selectors (`.intro`)
4. ID selectors (`#jumbotron`)
5. `!important` declarations

## [[Relative Units]]
Relative units scale with their environment — more flexible than fixed `px`.

| Unit | Relative to |
|---|---|
| `%` | Parent |
| `em` | Parent font size |
| `rem` | Root font size |

**Focus on `rem` and `%`:**
- `rem` = "root em" — scales from the browser default (usually 16px), so `1rem` = 16px by default
- `%` = percentage of the parent, e.g. `width: 100%` = full width of the container
```css
body { font-size: 1rem; /* usually 16px */ }
h1   { font-size: 2rem; /* 32px */ }
```
**Why:** easier to scale text and layout across screen sizes, improves accessibility, avoids the limits of fixed `px`. This approach respects browser settings and user preferences.

## Font Properties (VS Code autocomplete)
What pops up when you type `font` inside a rule. The first five are the everyday ones.

| Property | What it does | Example |
|---|---|---|
| `font` | Shorthand — sets several font properties in one declaration (style, weight, size, family) | `font: italic bold 1rem 'Avenir', sans-serif;` |
| `font-family` | Which typeface to use; list fallbacks in order, ending with a generic family | `font-family: 'Avenir', sans-serif;` |
| `font-size` | How big the text is — use [[Relative Units]] like `rem` | `font-size: 1.25rem;` |
| `font-weight` | How thick/bold the text is (`normal`, `bold`, or 100–900) | `font-weight: 700;` |
| `font-style` | Normal, italic, or oblique text | `font-style: italic;` |
| `font-display` | Controls how a custom web font shows while it loads (`swap`, `block`, `fallback`…). Only used inside `@font-face`, not in regular rules | `font-display: swap;` |
| `font-variant` | Shorthand for alternate letterforms, e.g. small caps | `font-variant: small-caps;` |
| `font-feature-settings` | Low-level switch for specific OpenType features built into a font | `font-feature-settings: "liga" 1;` |
| `font-variation-settings` | Low-level control of axes in a *variable font* (e.g. weight, width) | `font-variation-settings: "wght" 600;` |
| `font-variant-ligatures` | Turns ligatures (letter pairs joined into one glyph, like "fi") on or off | `font-variant-ligatures: none;` |
| `font-variant-numeric` | Number styling: lining vs old-style figures, tabular (fixed-width) digits, fractions | `font-variant-numeric: tabular-nums;` |
| `font-optical-sizing` | Lets a variable font adjust its shapes automatically to the text size (`auto` / `none`) | `font-optical-sizing: auto;` |

> These descriptions are general CSS reference, not from the slides — the instructor only showed `font-family` and `font-size` so far.

## To Know
- How to add classes to sections using Emmet

## Homework
- Coding exercise: apply CSS and relative units
- Complete readings and watch videos

## Reflection
*What was the most surprising insight today?*
