---
aliases: [UI-UX for Developers - Day 05]
tags: [ui-ux-for-developers, term1, html]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 5: HTML Sections

**Today's focus:** use semantic sectioning elements to give a page a clear, SEO-friendly outline.

## [[Semantic HTML|HTML Structure]]
The semantic outline of a webpage — how elements like headings, paragraphs, images, navigation, and sections are organized and nested. Headings (`<h1>`–`<h6>`) communicate hierarchy.

**Why it matters (SEO):** search engines use HTML structure to understand what a page is about. A well-structured page with clear headings and meaningful sections ranks better, and `<main>`, `<header>`, `<nav>`, `<article>`, and `<footer>` help bots index the page more effectively. Semantic structure also lets browsers and assistive tech interpret pages more clearly (see [[Inclusive Design and WCAG]]).

## Elements
Already known: `<header>` (intro and page title), `<main>` (main content), `<footer>` (closing info and contact).

New today:

| Element | Use |
|---|---|
| `<nav>` | Groups navigational links |
| `<section>` | Thematic grouping of content that belongs together. **Every section must include a heading.** Don't use it as a generic wrapper — use `<div>` for that |
| `<article>` | Standalone, reusable content that could be syndicated (e.g. a blog post or product feature) |
| `<aside>` | Side content that supports the main area: pull quotes, related links, definitions, ads or widgets. Can have a heading, doesn't require one |

**Article vs Section:** use `<article>` when the content is standalone; use `<section>` when the content is related and contributes to the page's topic.

**Nesting:** sections can be nested inside other sections (big deal) — every nested section still needs a heading.

### Outlines
- **Explicit** — created using semantic elements (`<section>`, `<article>`, etc.)
- **Implicit** — created only using headings (`<h1>`–`<h6>`)

**HTML5 Outliner** — a tool that shows how your document is structured by headings and sectioning elements, where headings are missing, and flags untitled sections. Use it to find nesting mistakes.

## Navigation
```html
<nav>
  <ul>
    <li><a href="...">...</a></li>
    <li><a href="...">...</a></li>
    <li><a href="...">...</a></li>
    <li><a href="...">...</a></li>
  </ul>
</nav>
```
`<nav>` is also used for social media links near the footer.

**Tips**
- Always use relative links between pages when working locally
- Test your links before uploading
- Use meaningful link text (no "click here")

## [[Document Object Model|DOM]] Structure Example
- `<body>` is the parent
- `<header>`, `<main>`, `<footer>` are siblings
- `<main>` has children: `<h2>` and `<p>`

## To Know
- Every `<section>` needs a heading; use `<div>` for generic wrapping
- Run pages through the HTML5 Outliner to catch nesting mistakes

## Homework
- Lesson 6 homework: multi-page site (`index.html` + `services.html`) — see the `HOMEWORK` folder

## Reflection
*What was the most surprising insight today?*
