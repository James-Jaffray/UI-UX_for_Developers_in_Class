---
aliases: [Flex Cheatsheet, Flexbox Cheat Sheet]
tags: [ui-ux-for-developers, term1, cheat-sheet, css, flexbox, reference]
course: "[[UI-UX for Developers]]"
day: 13
---

# Flexbox Cheatsheet

Quick lookup for [[Flexbox]]. Full explanation in [[Flexbox Introduction|Day 13]].

## The Setup
```css
.container {            /* the PARENT */
  display: flex;        /* children become flex items */
}
```
All the properties below go on the **container**. Only its **direct children** are affected.

## The Golden Rule
| Property | Controls | Axis |
|---|---|---|
| `justify-content` | Spacing / position **along** the line | **Main** |
| `align-items` | Position **across** the line | **Cross** |

`flex-direction: row` → main = horizontal, cross = vertical.
`flex-direction: column` → main = vertical, cross = horizontal.

## All Properties at a Glance
| Property | Values | Default |
|---|---|---|
| `display` | `flex` | `block` |
| `flex-direction` | `row` · `column` | `row` |
| `justify-content` | `flex-start` · `flex-end` · `center` · `space-between` · `space-around` | `flex-start` |
| `align-items` | `flex-start` · `flex-end` · `center` · `stretch` · `baseline` | `stretch` |
| `gap` | any length, e.g. `1rem` | `0` |

## `flex-direction`
```
row (default)               column
┌─────────────────┐         ┌───────┐
│ [1] [2] [3]     │         │ [1]   │
└─────────────────┘         │ [2]   │
                            │ [3]   │
                            └───────┘
```

## `justify-content` (main axis, shown with `row`)
```
flex-start     │[1][2][3]                  │
flex-end       │                  [1][2][3]│
center         │      [1][2][3]            │
space-between  │[1]       [2]          [3] │
space-around   │ [1]      [2]       [3]    │
```
- `space-between`: first and last touch the edges, equal gaps between
- `space-around`: equal space around each item, so edge gaps are half the size of the gaps between

## `align-items` (cross axis, shown with `row`)
```
flex-start     ┌────────────┐   flex-end     ┌────────────┐
               │[1][2][3]   │                │            │
               │            │                │[1][2][3]   │
               └────────────┘                └────────────┘

center         ┌────────────┐   stretch      ┌────────────┐
               │            │                │[1][2][3]   │
               │[1][2][3]   │                │[ ][ ][ ]   │  ← items grow to
               │            │                │[ ][ ][ ]   │    fill the height
               └────────────┘                └────────────┘
```
`baseline` lines items up by the baseline of their text, handy when items have different font sizes.

## Recipes

**Side-by-side boxes**
```css
.container {
  display: flex;
  gap: 1rem;
}
```

**Dead-centre anything**
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

**Nav bar: logo on the left, links on the right**
```css
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

**Vertical stack with even spacing**
```css
.container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
```

**Evenly spread menu items**
```css
nav ul {
  display: flex;
  justify-content: space-around;
}
```

## Debug Checklist
- [ ] `display: flex` is on the **parent**, not the items
- [ ] Items are **direct children** of the container (wrap them in a `<div>` if not)
- [ ] Values are spelled with hyphens: `flex-start`, `space-between`
- [ ] `align-items` not doing anything? The container needs **height** to have room on the cross axis
- [ ] Mixed up which property does what? Check `flex-direction` first, then main vs cross
- [ ] Open **DevTools** and click the **flex** badge next to the container to see the layout overlay

## Handy Extras (coming up)
Not covered yet, but likely useful for the responsive layout homework:
```css
.container { flex-wrap: wrap; }   /* items wrap onto a new line instead of squishing */
.item      { flex: 1; }           /* item grows to share the leftover space equally */
```
