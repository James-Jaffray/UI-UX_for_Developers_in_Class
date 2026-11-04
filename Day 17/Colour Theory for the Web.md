---
aliases: [UI-UX for Developers - Day 17]
tags: [ui-ux-for-developers, term1, lecture-notes, colour, accessibility, wcag, images, css]
course: "[[UI-UX for Developers]]"
day: 17
---

# UI-UX for Developers — Day 17: Colour Theory for the Web

**Today's focus:** colour psychology, analogous and complementary schemes, contrast and WCAG ratios, web image formats, and CSS background images. Accessibility links back to [[Inclusive Design and WCAG]]; type choices are in [[Web Typography]].

## Colour Psychology
- **Warm** (red, orange, yellow): energy, enthusiasm
- **Cool** (blue, green, purple): calm, relaxation

Meanings shift with culture, age and context, so treat them as starting points, not rules.

### Design Rules of Thumb
- **Designer ≠ client.** Design for the audience's needs, not your taste. Stakeholders have colour biases too
- When opinions clash, **user test**. Data beats "the CEO's granddaughter loves neon pink" for a banking CTA button
- **Limit the palette.** Too many colours cause confusion and cognitive overload; use each one with a purpose, like seasoning

### Individual Colours
| Colour | Feels like | Typical use |
|---|---|---|
| **Red** | passion, energy; also anger, danger | urgency, key elements, alerts |
| **Orange** | energetic, playful, warm | food and drink, uplifting designs |
| **Yellow** | joy, optimism; also caution | highlights, warnings |
| **Blue** | trust, loyalty, stability, calm; sometimes sadness | health, finance, tech |
| **Green** | growth, harmony, balance, nature | finance, eco brands, "go" |
| **Purple** | luxury, creativity, wisdom; can seem mysterious | cosmetics, fashion, exclusivity |

## Colour Schemes
### Analogous: neighbours on the colour wheel
- Unified, calm, cohesive (blue + green, or red + orange + yellow)
- **Low contrast between colours**, so watch readability and accessibility
- Good for dashboards: mood/habit trackers, income (warm) vs expenses (cool), engagement levels
- Examples: Trello (blues), Asana (orange/yellow), Pinterest Analytics (red/pink), Salesforce (blue/turquoise)

### Complementary: opposites on the wheel
- Red/green, blue/orange, yellow/purple. Dynamic, high contrast, memorable
- Builds **visual hierarchy**: important items in one colour, secondary in the other
- Balance it: use neutrals or dial back the intensity of the dominant colour
- Examples: Airbnb (dark turquoise + coral), Slack (purple + yellow), Netflix (red + green on dark gray)

## Contrast and Accessibility
Contrast is the visual difference between colours. It drives readability and hierarchy and guides the eye through the interface.
- Strong warm/cool contrast feels lively; soft transitions feel calm
- Design for **colour blindness**: enough contrast, test with tools, and **never use colour as the only signal**. Add text labels or symbols too

### WCAG Contrast (Criterion 1.4.3)
| Text | Minimum ratio |
|---|---|
| Normal text | **4.5 : 1** |
| Large text (18pt, or 14pt bold, and up) | **3 : 1** |
| UI components (WCAG 2.1) | **3 : 1** |

- Ratio = relative luminance of the lighter colour ÷ the darker colour
- Conformance levels **A, AA, AAA**. **AA** is the usual target; AAA isn't always achievable
- Check with the **WebAIM Contrast Checker** or Figma accessibility plugins

Real-world examples from the deck: Apple Health (green as the main colour for growth, blue for rest, small red accents for goals to improve), Google Analytics (calm blue plus lots of negative space so charts stand out), Spotify (green brand colour, light text on dark background, album-art colours for context).

## Image Formats
| Format | Type | Notes |
|---|---|---|
| **JPG / JPEG** | raster | photos; compressed (small, lower quality); always rectangular; no transparency or animation |
| **PNG** | raster | higher quality, bigger files; transparency; icons, UI elements, odd shapes |
| **SVG** | vector | code-based, scales infinitely with no pixelation; transparency; logos and icons |
| **GIF** | raster | animation, transparency, only 256 colours; short looping graphics |
| **WebP** | raster | modern replacement for JPG/PNG: smaller files, good quality, transparency. Figma can't export it |

See [[Images and Figures]] for `<img>` and `<figure>`.

## CSS Background Images
```css
header {
  background-image: url(../img/banner.jpg);   /* path is relative to the CSS file */
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```
- `background-image` puts an image behind the content
- `background-repeat`: tiles by default; control the axis or stop it (`repeat-x`, `no-repeat`)
- `background-position`: first value horizontal, second vertical
- `background-size`: `cover` fills the box, `contain` fits the whole image
- Layer **multiple backgrounds** with comma-separated values
- **Accessibility:** screen readers don't announce background images. Never use them for content people need to read or understand. Use `<img>` or semantic tags instead

## To Know
- [ ] Warm vs cool, and what red / blue / green / yellow usually signal
- [ ] Analogous = neighbours (calm, low contrast); complementary = opposites (bold, strong hierarchy)
- [ ] Keep the palette small, and test with users rather than trusting taste
- [ ] WCAG AA: 4.5:1 normal text, 3:1 large text; colour is never the only signal
- [ ] JPG for photos, PNG for transparency, SVG for logos/icons, WebP for small files, GIF for animation
- [ ] Background images are decoration only; the four properties: image, repeat, position, size

## Homework
- Complete the homework exercise

## Reflection
- What is one key takeaway about colour contrast?
- How will you ensure your designs are accessible?
