---
aliases: [Pseudo-Classes Reference, CSS pseudo-class cheat sheet]
tags: [ui-ux-for-developers, term1, css, reference]
course: "[[UI-UX for Developers]]"
---

# Pseudo-Classes Reference

A **pseudo-class** styles an element based on its *state* or *position* — things you can't target with a class in the HTML. It's written with **one colon** after a selector: `selector:pseudo-class { ... }`. Concept summary: [[CSS Pseudo-Classes]]. From [[UI-UX for Developers - Day 10]].

★ = covered in class

## Quick Reference

| Pseudo-class | Applies when… | Typical use |
|---|---|---|
| `:hover` ★ | Mouse pointer is over the element | Link/button feedback |
| `:focus` ★ | Element has focus (clicked or tabbed into) | Form fields, keyboard users |
| `:focus-visible` | Focused *and* the browser decides a focus ring is needed (mostly keyboard) | Focus rings without showing on mouse clicks |
| `:active` | Element is being pressed (mouse down) | "Pressed" button effect |
| `:link` | Unvisited link | Base link colour |
| `:visited` | Link already visited | Visited link colour |
| `:disabled` | Form control is disabled | Greyed-out buttons |
| `:checked` | Checkbox / radio is checked | Custom selected style |
| `:first-child` | Element is the first child of its parent | Remove top margin on first item |
| `:last-child` | Element is the last child of its parent | Remove bottom border on last item |
| `:nth-child(n)` | Element is the nth child | Zebra-striped rows |

## Hover & Focus (the two from class)

### `:hover` ★
Fires when the mouse is over the element. Use it on links and buttons to signal **"this is interactive."**
```css
a:hover {
  text-decoration: underline;
}
```
> Touch screens have no real hover, so never hide essential info behind it.

### `:focus` ★
Fires when the element is focused — clicked into, or reached with the **Tab** key. Essential for **keyboard users**, who rely on it to see where they are on the page.
```css
input:focus {
  outline: 2px solid dodgerblue;
}
```

> [!warning] Accessibility rules (see [[Inclusive Design and WCAG]])
> - **Never remove `:focus` styles** (`outline: none`) without adding your own
> - **Don't signal state with colour alone** — add an underline, size change, or icon

### Putting them together ★
```css
a {
  color: navy;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}
a:focus {
  outline: 2px dashed orange;
}
```
Visible, interactive, and accessible links.

## Link States
```css
a:link    { color: navy; }       /* unvisited */
a:visited { color: purple; }     /* already visited */
a:hover   { color: royalblue; }  /* mouse over */
a:active  { color: crimson; }    /* being clicked */
```
> **Order matters: L-V-H-A** (`:link` → `:visited` → `:hover` → `:active`). They have equal specificity, so the *later* rule wins ([[CSS Cascade and Specificity]]). Mnemonic: **L**o**V**e **HA**te.

## Focus Variants
| Pseudo-class | Difference |
|---|---|
| `:focus` | Any focus, including mouse clicks |
| `:focus-visible` | Only when a focus ring is useful (keyboard navigation) |
| `:focus-within` | Parent matches when *any child* has focus |

```css
button:focus-visible {
  outline: 3px solid orange;
}
form:focus-within {
  background-color: #f5f9ff;   /* highlights the whole form while typing in it */
}
```

## Form States
```css
input:disabled {
  background-color: #eee;
  cursor: not-allowed;
}
input:checked + label {
  font-weight: bold;
}
input:required {
  border-left: 4px solid crimson;
}
input:invalid {
  border-color: crimson;
}
```
| Pseudo-class | Matches |
|---|---|
| `:disabled` / `:enabled` | Controls that can't / can be used |
| `:checked` | Checked checkboxes and radio buttons |
| `:required` / `:optional` | Fields with / without the `required` attribute |
| `:valid` / `:invalid` | Fields whose value passes / fails validation |
| `:placeholder-shown` | Inputs currently showing placeholder text |

## Position-Based (Structural)
Target elements by where they sit among their siblings.
```css
li:first-child { font-weight: bold; }
li:last-child  { border-bottom: none; }

tr:nth-child(even) { background-color: #f2f2f2; }   /* zebra stripes */
tr:nth-child(3)    { color: crimson; }              /* exactly the 3rd */
li:nth-child(3n)   { color: gray; }                 /* every 3rd */
```
- `even` / `odd` are shortcuts for `2n` / `2n+1`
- Handy with tables ([[HTML Tables]]) and lists ([[HTML Lists]])

## Negation: `:not()`
Select everything *except* a match.
```css
li:not(:last-child) {
  border-bottom: 1px solid #ccc;   /* divider between items, none after the last */
}
```

## Pseudo-Class vs Pseudo-Element
| | Pseudo-class | Pseudo-element |
|---|---|---|
| Colons | One: `a:hover` | Two: `p::first-line` |
| Targets | An element in a certain *state* | A *part* of an element |
| Examples | `:hover`, `:focus`, `:nth-child()` | `::before`, `::after`, `::first-letter` |

## Specificity
A pseudo-class counts like a **class** (weight **10**), so `a:hover` = 1 + 10 = **11**. Details: [[CSS Cascade and Specificity]].

## Quick Checklist
- [ ] One colon, no space: `a:hover`, not `a :hover`
- [ ] Keep link states in **L-V-H-A** order
- [ ] Style `:focus` whenever you style `:hover`
- [ ] Never remove focus outlines without a replacement
- [ ] Don't rely on colour alone for state
