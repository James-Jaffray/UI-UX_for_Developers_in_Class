---
aliases: [UI-UX for Developers - Day 02]
tags: [ui-ux-for-developers, term1, html]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 2: HTML Markup Basics

**Today's focus:** mark up plain body copy with semantic HTML — page structure, headings, paragraphs, images, and links.

## [[HTML Document Structure]]
- Start every page with Emmet: type `!` + Tab in VS Code for the boilerplate
- Layout regions: `<header>` (title/intro), `<main>` (content), `<footer>` (closing info) — see [[Semantic HTML]]
- Indent nested elements so the structure is readable

## Elements Used
| Element | Use |
|---|---|
| `<h1>` | Main page title (one per page) |
| `<h2>` / `<h3>` | Major sections / subsections (e.g. character names) |
| `<p>` | Every paragraph of body copy |
| `<img>` | Images — always fill in `src` and `alt` |
| `<a>` | Links; `target="_blank"` opens external links in a new tab |
| `<q>` | Inline quotation |
| `<hr>` | Thematic break (used above the footer in the demo) |
| `&copy;` | Copyright symbol entity |

## [[Images and Figures|Images]]
- Rename images to meaningful names (`link.jpg`, not `image_0000_Layer 3.jpg`)
- Keep all images in the `img/` folder
- `alt` text describes the image for screen readers (see [[Inclusive Design and WCAG]])

## To Know
- Validate your HTML with the W3C Markup Validation Service (validator.w3.org)

## Homework
- Zelda HTML exercise: mark up `zelda_body_copy.docx` using `layout.png` as the guide (`h1` title, `h2` sections, `h3` characters, renamed images with `alt`)

## Reflection
*What was the most surprising insight today?*
