---
aliases: [UI-UX for Developers - Day 13]
tags: [ui-ux-for-developers, term1, lecture-notes, css, flexbox]
course: "[[UI-UX for Developers]]"
day: 13
---

# UI-UX for Developers — Day 13: Flexbox Introduction

**Today's focus:** getting boxes to sit **side by side** with [[Flexbox]] — what it is, turning it on with `display: flex`, and lining items up with `justify-content`, `align-items`, and `gap`.

**Cheatsheet:** [[Flexbox Cheat Sheet|Flex Cheatsheet]]

## Why Flexbox?
- So far every page has been **one long column** of content, but real sites have multiple columns
- Most text elements are **block-level**, so each one takes its own row ([[Block and Inline Elements]])
- **Flexbox** lines those elements up in a tidy row (or column) and controls spacing and alignment
- It's a **one-dimensional** layout model: it handles a **row** *or* a **column** at a time
- Good at distributing space and aligning items inside a container

## How It Works
1. Decide which elements should sit side by side. These become the **flex items**
2. Find their **direct parent**. This becomes the **flex container**
3. No suitable parent? **Wrap the items in a `<div>`**

```css
.container {
  display: flex;      /* turns the parent into a flex container */
}
```

| Term | What it is |
|---|---|
| **Flex container** | The parent with `display: flex;` |
| **Flex items** | The container's **direct children** |

Before: `display: block` stacks items 1, 2, 3, 4 vertically. After: `display: flex` puts them in a row.

> [!tip] Only direct children
> Flexbox only affects the container's **immediate children**, not grandchildren. If nothing changes, check you put `display: flex` on the right element.

## Main Axis vs Cross Axis
Everything in Flexbox depends on two axes:

| | Main axis | Cross axis |
|---|---|---|
| Set by | `flex-direction` | Always **perpendicular** to the main axis |
| With `row` | Horizontal (→) | Vertical (↓) |
| With `column` | Vertical (↓) | Horizontal (→) |

```
flex-direction: row            flex-direction: column

  ┌──────────────────┐           ┌──────────┐
  │ [1] [2] [3] [4]  │ ← main    │   [1]    │ ↑
  └──────────────────┘           │   [2]    │ main
        ↕ cross                  │   [3]    │ ↓
                                 └──────────┘ ← cross
```

> [!important] Key idea
> `justify-content` → **main axis**. `align-items` → **cross axis**.
> Flip `flex-direction` and what each one controls **swaps** with it.

## The 5 Properties for Today

| Property | What it does |
|---|---|
| `display: flex;` | Makes the element a flex container |
| `flex-direction: row \| column;` | Sets the main axis (row is the default) |
| `justify-content` | Aligns items along the **main** axis |
| `align-items` | Aligns items along the **cross** axis |
| `gap` | Space **between** items |

### `flex-direction`
```css
.container {
  display: flex;
  flex-direction: column;   /* items stack vertically; main axis is now vertical */
}
```
- `row` (default): left to right
- `column`: top to bottom

### `justify-content` (main axis)
| Value | Result |
|---|---|
| `flex-start` | Items bunch at the **start** (default) |
| `flex-end` | Items bunch at the **end** |
| `center` | Items bunch in the **middle** |
| `space-between` | First item at the start, last at the end, equal space **between** |
| `space-around` | Equal space **around** each item (half-size gaps at the edges) |

```css
.container {
  display: flex;
  justify-content: space-between;
}
```
> Write the values with a hyphen: `space-between`, `space-around` (the slide shows them with a space).

### `align-items` (cross axis)
| Value | Result |
|---|---|
| `flex-start` | Items at the **start** of the cross axis (top, in a row) |
| `flex-end` | Items at the **end** of the cross axis (bottom, in a row) |
| `center` | Items **centred** on the cross axis |
| `stretch` | Items **stretch** to fill the container's height (default, if items have no set height) |
| `baseline` | Items line up by the **baseline of their text** |

```css
.container {
  display: flex;
  align-items: center;
}
```

### `gap`
```css
.container {
  display: flex;
  gap: 1rem;     /* space between items, none on the outer edges */
}
```
Use `gap` instead of adding margins to every item ([[Relative Units]] work here too).

### Centre on both axes
Combine the two to centre items on **both** axes:
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;   /* horizontal (main) */
  align-items: center;       /* vertical (cross) */
}
```
Switch to `flex-direction: column` and both still centre, but the roles of the two properties swap.

## Quick Reference
```css
.container {
  display: flex;
  flex-direction: row;          /* or column */
  justify-content: center;      /* main axis */
  align-items: center;          /* cross axis */
  gap: 1rem;                    /* space between */
}
```

## Beginner Tips
- **Container, not items:** all five of today's properties go on the **parent**
- **Can't see `align-items` working?** The container needs some height, so there's room on the cross axis
- **Stuck?** Open DevTools and click the element. Flex containers get a small **flex** badge you can click to overlay the layout
- **Mixed up?** Ask: which way is my main axis? Then `justify-content` is along it, `align-items` is across it

## To Know
- [ ] Flexbox is **one-dimensional** (a row or a column)
- [ ] Flex container = parent with `display: flex`; flex items = its direct children
- [ ] Main axis follows `flex-direction`; cross axis is perpendicular
- [ ] `justify-content` = main axis, `align-items` = cross axis
- [ ] `justify-content` values: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`
- [ ] `align-items` values: `flex-start`, `flex-end`, `center`, `stretch`, `baseline`
- [ ] `gap` spaces items apart

## Homework
- [ ] Coding exercise: implement a **responsive Flexbox-based layout**
- [ ] Practice with the **Diner Game**

## Reflection
- What is one key takeaway about Flexbox?
- How will you apply Flexbox in your future projects?
