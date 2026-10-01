---
aliases: [UI-UX for Developers - Day 10]
tags: [ui-ux-for-developers, term1, css]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 10: CSS Selectors and Properties (Part I)

**Today's focus:** how CSS decides which rule wins ([[CSS Cascade and Specificity|cascade & specificity]] and [[CSS Inheritance|inheritance]]), plus [[CSS Pseudo-Classes|pseudo-classes]] (`:hover`, `:focus`) and styling choices that keep a site usable.

**Demo:** [[Coffee Cup Demo Walkthrough]] · **Reference:** [[Pseudo-Classes Reference]]

## The Cascade (refresher)
"Cascading" = rules can overwrite each other. When several rules hit the same element:
1. **Later beats earlier** — but only if specificity is equal
2. **More specific beats less specific**
3. **`!important` beats everything** — avoid it

## Specificity
Every selector gets a **weight**; the higher score wins.

| Selector type | Example | Weight |
|---|---|---|
| Element | `p, h1, h2, ul, li` | **1** |
| Class | `.name` | **10** |
| Descendant | `ul li a` (read right to left; spaces between) | **3** (1 + 1 + 1) |
| Descendant + class | `ul.bullet li` (no space between `ul` and `.bullet`) | **12** (1 + 10 + 1) |
| ID | `#name` | **100** |
| `!important` | `p { color: red !important; }` | **101** |

**How to score one:** add up the parts. Each element = 1, each class = 10, each ID = 100.

```css
p     { color: blue; }
.card { color: red; }   /* overrides the blue: 10 > 1 */
```

> [!tip] Spaces matter
> `ul li` = a `<li>` *inside* a `<ul>`. `ul.bullet` = a `<ul>` that *has* the class `bullet`. No space = same element.

### Descendant selectors
Target elements by where they live in the HTML tree:
```css
main h2 {
  color: purple;   /* only <h2>s inside <main> */
}
```

## Inheritance — CSS passes down
Some properties flow from parent to child automatically.

**Inherited ✅**
- `color`
- `font-family`
- line height, visibility, letter spacing

```css
body {
  color: darkslategray;
  font-family: Arial;
}
/* every element on the page picks these up, unless something more specific overrides them */
```

**NOT inherited ❌** — set these directly with a class or selector
- `margin`, `padding`, `border`
- `width`, `height`, `background`
- `display`, `position`

> Rule of thumb: **text styles inherit, box/layout styles don't.**

## Pseudo-Classes
Style an element based on its *state*. Full list with examples: [[Pseudo-Classes Reference]].

| Pseudo-class | When it applies |
|---|---|
| `:hover` | Mouse is over the element |
| `:focus` | Element is focused (e.g. tabbed into a form field) |

```css
a:hover {
  text-decoration: underline;
}
input:focus {
  outline: 2px solid dodgerblue;
}
```

## Usability: Hover & Focus
- **`:hover`** → great for links and buttons; signals "this is interactive"
- **`:focus`** → essential for accessibility; keyboard users need a clear visual cue of where they are (see [[Inclusive Design and WCAG]])

**Do / Don't**
- [ ] **Never** remove `:focus` styles without adding your own
- [ ] **Don't use colour alone** to signal a state change — add an underline, size change, or icon

Putting it together:
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
Result: links that are visible, interactive, and accessible.

## To Know
- [ ] Specificity weights: element 1 · class 10 · ID 100 · `!important` 101
- [ ] Cascade order: specificity first, then later-beats-earlier
- [ ] Which properties inherit (`color`, `font-family`) and which don't (`margin`, `padding`, `width`, `display`…)
- [ ] `:hover` = mouse over, `:focus` = keyboard/selected
- [ ] Never remove `:focus` styling without a replacement

## Homework
- [ ] Experiment with different CSS selectors and style an HTML page
- [ ] Practice with the Diner Game

## Reflection
- What is one key takeaway about CSS selectors?
- How will you improve your CSS workflow?
