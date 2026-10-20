---
aliases: [UI-UX for Developers - Day 14]
tags: [ui-ux-for-developers, term1, lecture-notes, css, flexbox, responsive]
course: "[[UI-UX for Developers]]"
day: 14
---

# UI-UX for Developers — Day 14: Flexbox Part II

**Today's focus:** `flex-direction`, `flex-wrap`, `gap`, `calc()` for layout maths, and making images responsive. Follows [[Flexbox Introduction]]; quick lookup in [[Flexbox Reference Sheet]]. Concept page: [[Flexbox]].

## Recap (Day 13)
- `display: flex` on the container turns its children into flex items
- `align-items` aligns items on the cross axis

## flex-direction
Controls the direction of the **main axis**:

| Value | Direction |
|---|---|
| `row` (default) | left → right |
| `row-reverse` | right → left |
| `column` | top → bottom |
| `column-reverse` | bottom → top |

## flex-wrap
By default flexbox tries to fit everything on **one line**, even if items end up squished. `flex-wrap` says what to do on overflow:

| Value | Behaviour |
|---|---|
| `nowrap` (default) | all items stay on one line |
| `wrap` | items wrap onto more lines if needed |
| `wrap-reverse` | like `wrap`, but lines stack in the opposite direction |

Use `wrap` when you want items to behave responsively — especially on small screens.

## gap
Even spacing between items inside a flex container — horizontally and vertically when wrapped. No more margin hacks.
```css
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
```
- `column-gap` — space between columns
- `row-gap` — space between rows
- Shorthand: `gap: <row-gap> <column-gap>;` (e.g. `gap: 1rem 2rem;`)

## calc()
Do maths directly in CSS — handy for layouts that are flexible *and* consistent.

Four cards per row, 1rem gaps:
```css
.card {
  width: calc((100% - 3rem) / 4);
}
```
- Container is 100% wide; 4 cards per row → 3 gaps × 1rem = **3rem** of gap space
- Subtract the gap space from the full width, then divide what's left equally among the 4 cards
- Fluid and responsive, no hard-coded pixel sizes

Mixing units inside `calc()` is the point (`%` with `rem`, `px`…). Put spaces around `+` and `-`. See [[Relative Units]] and [[CSS calc() Reference Sheet]].

## Responsive Images
```css
.card img {
  width: 100%;
  height: auto;
}
```
- `width: 100%` — fills the width of its parent (the `.card`)
- `height: auto` — keeps the proportions, no stretching or squishing

**Don't** set `width`/`height` attributes on the `<img>` in HTML (e.g. `<img width="400" height="300">`). Those are pixel values that override your CSS and stop the image from resizing. Leave the size out of the HTML and control it with CSS only.

## To Know
- `flex-direction` sets the main axis (`row` default, `column` for vertical)
- `flex-wrap: wrap` stops items squishing and lets them flow onto new lines
- `gap` / `row-gap` / `column-gap` replace margin hacks for spacing
- `calc((100% - total gaps) / n)` gives n equal-width items with gaps
- Responsive images: `width: 100%; height: auto;`, no size attributes in the HTML

## Homework
- Coding exercise: create a fully responsive layout using Flexbox
- Practice with Flexbox Games

## Reflection
- What is one key takeaway about advanced Flexbox properties?
- How will you use Flexbox in responsive design?
