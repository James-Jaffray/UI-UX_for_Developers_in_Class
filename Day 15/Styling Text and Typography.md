---
aliases: [UI-UX for Developers - Day 15, Web Typography Lecture]
tags: [ui-ux-for-developers, term1, lecture-notes, css, typography, fonts, pseudo-classes]
course: "[[UI-UX for Developers]]"
day: 15
---

# UI-UX for Developers — Day 15: Styling Text and Typography

**Today's focus:** typography terms, font sizing with `rem`, `line-height` and `letter-spacing`, font classifications, text formatting rules, then the structural pseudo-classes `:nth-child()`, `:first-child`, `:last-child` and `:only-child`. Concept page: [[Web Typography]]. Builds on [[Relative Units]] (Day 09) and [[CSS Pseudo-Classes]] (Day 10). Quick lookup for layout maths: [[CSS calc() Reference Sheet]].

## Why Typography Matters
**Typography** = the design of text using fonts, symbols and signs. Headings, body text, buttons, forms and captions are all typography, so it's part of every web project.
- **Communication:** text carries ideas, offers and brand values, and often says what one image can't
- **Aesthetic:** type choices give the page a style and reinforce the brand identity
- **Hierarchy:** type shows what's main vs. secondary and puts emphasis on the important blocks

## Terminology
| Term | Meaning | Example |
|---|---|---|
| **Letter** | The basic unit; each one has its own internal structure | `A` |
| **Typeface** | A set of letters/symbols sharing a design (what people usually *call* a font) | Arial, Helvetica, Roboto |
| **Font** | One style/weight/size within a typeface | Helvetica Light, Roboto Bold |

`font-family` sets the typeface(s). List fallbacks, ending with a generic family:
```css
p { font-family: georgia, garamond, serif; }
```

## Key Measurements
- **Font size:** the vertical size of the letters
- **Leading:** distance between the **baselines** of adjacent lines. Not the same as line spacing (baseline to the top of the lowercase letters on the next line)

### px vs. rem (accessibility)
```css
font-size: 16px;   /* fixed unit: pixels */
font-size: 1rem;   /* relative unit: 1rem = 16px if the browser default is unchanged */
```
If a user with low vision raises their browser's default font size, `px` text stays small, but `rem` or `%` text grows with their setting.

| Fixed (`px`) | Relative (`rem`, `em`, `%`) |
|---|---|
| Exact, unchanging size | Scales with user/device settings |
| Doesn't respect browser zoom | Respects user zoom preferences |
| Can harm accessibility | Better readability across screens |

**Best practice:** use `rem` for font sizing (based on the root element). Only use `px` for things that shouldn't scale, like borders or precise layouts. See [[Relative Units]] and [[Inclusive Design and WCAG]].

## line-height
Space between lines of text in a block.
```css
p {
  font-size: 1rem;
  line-height: 1.5;   /* 150% of the font size */
}
```
- Use a **unitless** value like `1.5`, not `px`, so it scales with the font size
- Too tight is hard to read; too loose feels disconnected. Body text especially benefits from good `line-height`

## letter-spacing
Horizontal space between characters.
```css
h1 { letter-spacing: 0.05rem; }
```
- Slightly **increase** for all-caps text and display fonts
- **Tighten** for large headlines or design-focused elements

## Other Font and Text Properties
| Property | Values |
|---|---|
| `font-style` | `normal` · `italic` · `oblique` |
| `font-variant` | `normal` · `small-caps` |
| `font-weight` | `normal` · `bold` · `bolder` · `lighter` · numeric `100`–`900` |
| `text-transform` | `uppercase` · `lowercase` · `capitalize` |
| `text-align` | `left` · `center` · `right` |
| `font-stretch` | `ultra-condensed` → `ultra-expanded` (only works if the font supports it) |

## Font Classifications
| Type | Feel | Good for |
|---|---|---|
| **Serif** | Elegant, high status, trust, intelligence | Law firms, insurance, banks, translation agencies |
| **Slab serif** | Bold, massive square serifs, clear but original | Conservative brands willing to try something non-standard |
| **Sans-serif** | Neat, simple, minimalist, universal; doesn't overload the interface | Most UI and minimalist projects |
| **Handwritten** | Decorative, creative, hard to fit in; can overload a design | Small doses only |
| **Modern** | Versatile, new, often futuristic | Tech, IT, education |
| **Decorative** | Maximum decoration; competes with everything else | Very sparingly: youth, creative and art projects |

## Rules of Text Formatting
- **Hierarchy and structure:** order content by importance. A page needs a heading and main text, plus smaller subheadings and hint text. Use size, colour, scale, frames and lines to highlight headings, subheadings and buttons. One font alone isn't enough
- **Alignment:** left-aligned text is easiest to read. Centre headings/subheadings only occasionally. Right alignment isn't used for text (except numbers in tables)
- **Limit line length:** **45–70 characters** per line keeps concentration and navigation comfortable (this is what `max-width` is for, see [[Box Model and Max-width]])
- **Prefer standard fonts:** users are used to them, and custom fonts are harder to read. Use custom fonts only when needed. Keep to **3 fonts or fewer** per site, and make sure text stays readable at any size

### Web-safe fonts vs. web fonts
- **Web-safe fonts** are pre-installed on most operating systems. Reference sites: *Common Fonts for Windows/Mac* and *CSS Font Stack*
- **Hosted web fonts** (e.g. Google Fonts):
  1. Choose a font
  2. Preview it
  3. Choose styles and copy the `<link>` or `@import` code
  4. Paste it inside your `<head>`
  5. Copy the matching `font-family` rule into `styles.css`

## Structural Pseudo-Classes
Select elements by their **position among siblings**. Full list in [[Pseudo-Classes Reference]], concept in [[CSS Pseudo-Classes]]. Deeper dive on the formulas: [[nth-child Explained]].

| Selector | Selects | Example |
|---|---|---|
| `:nth-child(n)` | The nth element in a list of siblings | `section p:nth-child(3)` is the third paragraph in a section |
| `:nth-child(4n)` | Every 4th sibling (formulas work) | `li:nth-child(4n)` is every fourth list item |
| `:nth-child(even)` / `(odd)` | Every even/odd sibling | `tr:nth-child(even)` is every even table row (starting with the 2nd) |
| `:first-child` | The first sibling | `section p:first-child` is the first paragraph in any section |
| `:last-child` | The last sibling | `li:last-child` is the last list item |
| `:only-child` | An element with **no siblings** | see below |

```html
<div>
  <div>I'm the first sibling.</div>
  <div>I'm the second sibling.</div>
  <div>I'm the third sibling,
    <div>but I'm an only child</div>.
  </div>
</div>
```
```css
div:only-child {
  color: chartreuse;
}
```
Only the innermost `<div>` matches: it's the sole child of its parent.

## Demo Setup
The demo page sets the base font on `body` so everything else scales from it:
```css
body {
  font-size: 100%;   /* = 1rem = 16px */
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
```

## To Know
- Typeface = the family (Roboto); font = one style of it (Roboto Bold)
- Size text in `rem`, not `px`, so it respects the user's browser settings
- `line-height` goes **unitless** (`1.5`), roughly 150% for body text
- `letter-spacing`: more for all-caps, less for big headlines
- Keep lines to **45–70 characters**, left-aligned, with **3 fonts max** and a clear heading/body hierarchy
- Web-safe fonts need nothing extra; hosted web fonts need a `<link>`/`@import` in `<head>` plus a `font-family` rule
- `:nth-child()`, `:first-child`, `:last-child`, `:only-child` select by position among siblings

## Homework
- Explore Google Fonts and try different font pairings on a practice web page
- Complete the Day 15 homework exercise

## Reflection
- What typography techniques will you apply in your web projects?
