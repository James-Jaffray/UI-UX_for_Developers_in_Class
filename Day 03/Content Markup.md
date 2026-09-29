---
aliases: [UI-UX for Developers - Day 03]
tags: [ui-ux-for-developers, term1, html]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 3: Lists, Figures & Content Markup

**Today's focus:** mark up a recipe page using lists, `<figure>`/`<figcaption>`, and image links, guided by a wireframe.

## [[HTML Lists]]
| Element | Use | Recipe example |
|---|---|---|
| `<ul>` + `<li>` | Unordered list (order doesn't matter) | Ingredients |
| `<ol>` + `<li>` | Ordered list (steps in sequence) | Directions |
| `<dl>` + `<dt>` + `<dd>` | Description list: term + definition | Glossary of ingredient terms |

## [[Images and Figures|Figures]]
- `<figure>` groups related images under one caption; `<figcaption>` is that caption
- Wrap an `<img>` in `<a>` to make it a link; add `alt` and `title` attributes
- Use `<cite>` to credit borrowed content

## File & Link Conventions
- Image names: lowercase, hyphens instead of spaces, no CamelCase (`frying-beef.png`)
- All images live in `img/`
- External links use `target="_blank"`
- Check heading hierarchy (`h1` → `h2`) and validate before submitting

## To Know
- Use the wireframe to decide structure and image placement — ignore appearance, that's CSS later

## Homework
- Picadillo recipe markup exercise: mark up `copy.docx` with the semantic structure above, wrap the first image in a link to the original recipe

## Reflection
*What was the most surprising insight today?*
