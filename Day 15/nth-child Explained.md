---
aliases: [nth-child, :nth-child(), nth-child explained]
tags: [ui-ux-for-developers, term1, css, pseudo-classes, selectors, reference-sheet]
course: "[[UI-UX for Developers]]"
day: 15
---

# `:nth-child()` Explained

Selects an element **based on its position among its siblings** (the elements sharing the same parent). Introduced in [[Styling Text and Typography|Day 15]]. Part of [[CSS Pseudo-Classes]]; the full list is in [[Pseudo-Classes Reference]].

```css
li:nth-child(3) { color: crimson; }
```
Read it as: "select any `li` that is **the 3rd child** of its parent."

## How it counts
- Counting starts at **1**, not 0
- It counts **every child** of the parent, whatever its tag
- The element must match **both** parts: the selector before the colon *and* the position

```html
<section>
  <h3>Title</h3>   <!-- child 1 -->
  <p>One</p>       <!-- child 2 -->
  <p>Two</p>       <!-- child 3 -->
  <p>Three</p>     <!-- child 4 -->
</section>
```
```css
p:nth-child(3) { }   /* "Two": it's a <p> AND the 3rd child */
p:nth-child(1) { }   /* matches nothing: child 1 is the <h3> */
```
This is the classic trap: the `<h3>` takes up position 1, so the "first paragraph" is child 2.

## Keywords
| Value | Selects | Example |
|---|---|---|
| `3` | Exactly the 3rd child | `tr:nth-child(3)` |
| `odd` | 1st, 3rd, 5th… | `li:nth-child(odd)` |
| `even` | 2nd, 4th, 6th… | `tr:nth-child(even)` (zebra stripes) |

## The formula `an + b`
`n` is a counter that runs 0, 1, 2, 3… The browser plugs each value in and selects every child whose position comes out.

| Formula | Selects (positions) | Plain English |
|---|---|---|
| `n` | 1, 2, 3, 4… | Every child |
| `2n` | 2, 4, 6… | Same as `even` |
| `2n + 1` | 1, 3, 5… | Same as `odd` |
| `3n` | 3, 6, 9… | Every 3rd |
| `4n` | 4, 8, 12… | Every 4th (the Day 15 slide example) |
| `n + 3` | 3, 4, 5… | Third child onward |
| `-n + 3` | 3, 2, 1 | **First three** only |
| `3n + 1` | 1, 4, 7… | Every 3rd, starting with the 1st |

- `a` = the step size (how often it repeats)
- `b` = the offset (where it starts)
- Positions below 1 are ignored, which is why `-n + 3` stops at 3

## Common uses
```css
/* Zebra-striped table */
tr:nth-child(even) { background-color: #f2f2f2; }

/* Remove margin from the last card in each row of 3 */
.card:nth-child(3n) { margin-right: 0; }

/* Highlight only the first three list items */
li:nth-child(-n + 3) { font-weight: bold; }
```

## Related selectors
| Selector | Same as |
|---|---|
| `:first-child` | `:nth-child(1)` |
| `:last-child` | the final child, however many there are |
| `:only-child` | an element with no siblings |
| `:nth-last-child(n)` | like `:nth-child`, counting from the **end** |
| `:nth-of-type(n)` | counts only siblings of the **same tag** |

`:nth-of-type` fixes the trap above: `p:nth-of-type(1)` is the first `<p>` even with an `<h3>` before it.

## Debug Checklist
- [ ] Counting from 1, and counting **all** siblings (headings, images, everything)
- [ ] The tag in front of the colon actually is the child at that position
- [ ] Spaces around `+` and `-` in the formula: `2n + 1`, not `2n+1` (some browsers are fussy)
- [ ] Wrong element selected? Try `:nth-of-type()` instead
- [ ] Check in DevTools: select the parent and count its children in the Elements panel

## Quick Memory Hook
> **`:nth-child(an + b)`** = "every `a`-th child, starting at position `b`." No formula needed? Use `odd`, `even`, or a plain number.
