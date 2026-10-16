---
aliases: [UI-UX for Developers - Day 12]
tags: [ui-ux-for-developers, term1, lecture-notes, css, box-model, responsive]
course: "[[UI-UX for Developers]]"
day: 12
---

# UI-UX for Developers — Day 12: Box Model and Max-width

**Today's focus:** how the CSS box model affects layout, padding/border/margin, `box-sizing`, why we use a reset file, and centering content with `max-width` + `margin`. Concept page: [[CSS Box Model]].

## The Box Model
Every element is treated as a rectangular box — even if it doesn't look like one. Four layers, inside out:

| Layer | What it is | Sized with |
|---|---|---|
| **Content** | Where your content shows | `width`, `height`, `inline-size`, `block-size` |
| **Padding** | Space between content and border | `padding` |
| **Border** | Wraps content + padding | `border` |
| **Margin** | Outermost; space *between* boxes | `margin` |

### Worked example
`width: 200px; padding: 20px; border: 4px; margin: 30px;`
- Content: 200px
- Padding: 20px each side → +40px
- Border: 4px each side → +8px
- Total box width = 200 + 40 + 8 = **248px**
- Margin (30px) sits *outside* the box — it doesn't count toward the box's size, it creates space around it

### Why it matters
- Affects layout and alignment — forget padding and content can overflow or look off-centre
- Borders and margins both add space, but in different ways (border is part of the box, margin is outside it)
- You have to calculate total size: width + padding + border

## Margin, Padding and Border
```css
/* shorthand: 1 value = all sides */
margin: 20px;
/* 2 values = top/bottom  left/right */
margin: 10px 20px;
/* 3 values = top  left/right  bottom */
margin: 10px 20px 30px;
/* 4 values = top right bottom left (clockwise) */
margin: 10px 20px 30px 40px;
```
`padding` uses the same shorthand. Border needs a **width** and a **style** (a colour is optional):
```css
border: 4px solid #333;
border-width: 4px;
border-style: solid;   /* none, solid, dashed, dotted, double... */
```

## box-sizing
By default `width` is the **content** width, so padding and border get *added on top* (the 248px example).

`box-sizing: border-box` lets you set one overall width for the element: the browser **subtracts padding and border from the content space**, so the total size stays consistent.

- Margins are still calculated separately (they're outside the box) — adding left/right margin to a centred container can break the centring
- Apply it universally, including pseudo-elements (`::before`, `::after` do **not** inherit `box-sizing` by default):
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```
This is the modern standard and goes in the reset file.

## CSS Resets
A reset is a stylesheet (usually its own `.css` file) that removes default browser styles. Every browser ships its own defaults for headings, margins, padding, buttons, so the same HTML looks slightly different in each — remember Day 1 when text looked different per browser.

**Why:** consistency across browsers, a clean starting point, full control over layout/spacing/fonts. Without one, an `<h1>` may have a 32px top margin in one browser and 40px in another, `<ul>` brings bullets and padding, `<button>` looks different on Mac vs Windows.

| Type | Notes |
|---|---|
| **Modern reset** (Piccalilli) | Lightweight; removes default margins from only some elements; adds `box-sizing: border-box`. **We use a modified version of this.** |
| **Normalize** | Keeps useful defaults (typographic structure), fixes browser-specific bugs, uses vendor prefixes (`-webkit-`, `-moz-`) |
| **Bootstrap Reboot** | Built on Normalize, adds its own styles so pages look modern from the start; part of Bootstrap (later in the course) |

Browser compatibility has improved, so heavy-handed resets are often unnecessary — a lighter modern reset is more practical.

## max-width and Responsiveness
`max-width` sets the **maximum** width an element may have: it can shrink and grow, but never get wider than that value. That keeps layouts fluid without breaking on different screens — unlike a fixed `width`, which doesn't give.

**Viewport** = the visible area of the browser window (what you see without scrolling). It changes with device (desktop/tablet/phone), window size and zoom. "Full viewport width" = edge to edge.

### The `.inner-container` pattern
```css
.inner-container {
  max-width: 960px;
  margin: 0 auto;
}
```
- `max-width: 960px` — content never gets wider than 960px, even on a huge monitor
- `margin: 0 auto` — centres the container horizontally inside the full-width element

Use it to get a **full-width background** with **centred, readable content**: e.g. a `<header>` with a full-viewport green background and an `.inner-container` inside it.

**Placement matters:** put `.inner-container` *inside* the section (`<header>`, `<main>`, `<footer>`…). Don't wrap the `<header>` in it, or you lose the full-width background.

## To Know
- Box = content + padding + border (+ margin outside); total width = width + padding + border
- Margin doesn't count toward box size but creates space between boxes
- `box-sizing: border-box` on `*, *::before, *::after` keeps total size = the width you set
- A reset gives consistent, predictable starting styles across browsers; we use a modified Piccalilli modern reset
- `max-width` + `margin: 0 auto` centres content and keeps it responsive
- `.inner-container` goes *inside* full-width sections

## Homework
- Hands-on CSS Box Model implementation exercise
- Practice with Diner Game

## Reflection
- What is one key takeaway about the Box Model?
- How does `max-width` improve responsive layouts?
