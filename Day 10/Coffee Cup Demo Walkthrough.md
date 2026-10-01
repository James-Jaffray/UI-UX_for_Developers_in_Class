---
aliases: [Day 10 Demo, Coffee Cup Demo]
tags: [ui-ux-for-developers, term1, css, demo]
course: "[[UI-UX for Developers]]"
---

# Day 10 Demo: The Coffee Cup Cascade

In-class demo for [[UI-UX for Developers - Day 10]]. One stylesheet (`css/styles.css`) styling the Coffee Cup page, built to show [[CSS Selectors|selector types]] and how [[CSS Cascade and Specificity|specificity]] settles conflicts.

## The Page Structure (what the selectors hit)
```
body
├── header
│   ├── h1, p
│   └── nav
│       └── ul.navigation
│           └── li > a   (x7)
├── main
│   └── section → h2, p (x4)
└── footer
    ├── h2
    └── ul → li > a   (Facebook, Twitter)
```
Two `<ul>`s exist: the nav one (has `class="navigation"`) and the footer one. That's why `ul` and `nav ul` behave differently.

## Highlights

### 1. Element selectors set the base look
```css
body {
    background-color: rgb(0, 0, 0);
    color: white;
    font-family: Arial, Helvetica, sans-serif;
}
```
- `color` and `font-family` on `body` are **inherited** by everything inside ([[CSS Inheritance]])
- `background-color` is **not** inherited, so `main`, `ul`, and `footer` each get their own
- `Arial, Helvetica, sans-serif` is a **font stack**: browser tries each in order, ending with a generic family as the fallback

### 2. `a` needs its own colour
```css
a {
    color: rgb(146, 55, 243);
    text-decoration: none;   /* underline is a text decoration, 'none' removes it */
}
```
Links ignore the inherited white from `body` because the browser has its own default link colour. To change links you have to target `a` directly.

### 3. Comma = multiple selectors
```css
h1,
h2,
p {
    color: rgb(145, 227, 227)
}
```
One rule for three elements. Each selector in the list is scored **separately** (each is weight 1).

### 4. Descendant selectors win the conflicts
```css
footer h2 { color: rgb(247, 80, 80) }
nav ul    { background-color: rgb(65, 100, 90); }
nav ul li { border-bottom: ... }
```

| Conflict | Competing rules | Winner |
|---|---|---|
| Footer heading colour | `h1, h2, p` = **1** vs `footer h2` = **2** | `footer h2` → red |
| Nav list background | `ul` = **1** vs `nav ul` = **2** | `nav ul` → green |
| Footer list background | only `ul` matches (not inside `nav`) | `ul` → translucent grey |

The `<h2>` in `main` has no descendant rule, so it stays light cyan. This is the cascade in action: the more specific rule beats the general one, **regardless of order**.

### 5. rgba() = colour + transparency
```css
background-color: rgba(55, 52, 52, 0.472);
```
The 4th value is **alpha**: `0` = invisible, `1` = solid. At `0.472` the grey is about 47% opaque, so what's behind it shows through.

### 6. Border shorthand
```css
border-bottom-width: 0.125rem;
border-bottom-style: dashed;
border-bottom-color: black;
border-bottom: .125 dashed black   /* condensed version */
```
Shorthand order: **width → style → colour**. Only the style is required.

## Spot the Bugs (beginner traps in this file)

> [!warning] Missing unit: `.125`
> `border-bottom: .125 dashed black` is **invalid**. A number needs a unit (`rem`, `px`...); only `0` is allowed without one. The browser silently ignores the line, and the three longhand lines above are the ones actually working. Fix: `border-bottom: 0.125rem dashed black;`

> [!warning] Missing semicolons
> `h1, h2, p { color: ... }` and `footer h2 { color: ... }` have no `;` on their last declaration. It works for one line, but the moment you add a second declaration underneath, it breaks. Habit: **always end with `;`**.

> [!warning] Purple links on the green nav are nearly unreadable
> Contrast ratio of `rgb(146, 55, 243)` on `rgb(65, 100, 90)` is about **1.3 : 1**. WCAG AA wants **4.5 : 1** for normal text ([[Inclusive Design and WCAG]]). Even on plain black it only reaches about 4.1 : 1. Plus, `text-decoration: none` means colour is the *only* thing marking these as links. Class rule: add a `:hover` underline and a `:focus` outline ([[CSS Pseudo-Classes]]), and pick a lighter link colour.

> [!warning] Black dashed border on a dark nav
> `black` on `rgb(65, 100, 90)` is only about 3.2 : 1, so the dashes are faint. Try a lighter colour.

## The Empty Sections (the rest of the demo)
The file has three placeholders. They match the next slide topics. Ideas to fill them:

```css
/* Pseudo Class Selector */
a:hover {
    text-decoration: underline;     /* weight 1 + 10 = 11 */
}
a:focus {
    outline: 2px dashed orange;
}

/* Class Selectors */
.navigation {
    border: 1px solid white;        /* weight 10 */
}

/* Descendant Combinator */
nav ul.navigation li {
    padding: 0.5rem;                /* weight 1 + 1 + 10 + 1 = 13 */
}
```
- `.navigation` (10) **beats** `nav ul` (2) if they set the same property
- `ul.navigation` has **no space**: a `<ul>` *with* that class. `ul .navigation` (space) would mean something inside a `ul`

## Beginner Tips

**Reading the file**
- **Hover a selector in VS Code** to see its specificity as three numbers `(IDs, classes, elements)`. For example `nav ul li` is `(0, 0, 3)`. This is what the demo's first comment is pointing at.
- Our weights (1 / 10 / 100) are a simplified way to read the same idea

**Debugging**
- **Browser DevTools** (right-click → Inspect, or `F12`): click an element and the *Styles* panel lists every rule that applies, with **overridden ones crossed out**. This is the fastest way to answer "why isn't my CSS working?"
- Typo in a property or an invalid value? The browser ignores it with no error. Look for it **not appearing** (or crossed out with a warning icon) in DevTools
- Edit the **CSS file**, save, then **refresh** the browser

**Writing**
- Group rules the way the demo does (element → multiple → descendant → class...) with comments marking each section
- Put shorthand **after** longhand if you use both, or just pick one. Mixing them (like the border above) is how confusing overrides sneak in
- Don't reach for `!important` when a rule isn't winning. Raise the specificity with a better selector instead
- Use `rem` for sizes like `0.125rem` ([[Relative Units]]) and keep a leading `0` for readability (`0.125`, not `.125`)
- Name classes by **purpose** (`.navigation`), not appearance (`.purple-text`)

**Quick experiment (5 minutes)**
- [ ] Swap the order of `ul` and `nav ul` in the file. Does the nav colour change? (It shouldn't. Specificity beats order.)
- [ ] Give `h2` and `.navigation` the same property and see who wins
- [ ] Remove the semicolon-less last declaration pattern: add a second property to `footer h2` and see what breaks
- [ ] Fix the `.125` border line and check it in DevTools
