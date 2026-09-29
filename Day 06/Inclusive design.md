---
aliases: [UI-UX for Developers - Day 06]
tags: [ui-ux-for-developers, term1, accessibility]
course: "[[UI-UX for Developers]]"
---

# UI-UX for Developers — Day 6: Inclusive Design

**Today's focus:** design for users with a wide range of abilities, using WCAG as the framework.

## [[Inclusive Design and WCAG|Types of User Limitations]]
- Visual impairments (blindness, low vision)
- Color blindness and dyslexia
- Hearing loss or deafness
- Motor or mobility challenges
- Cognitive, mental, or neurological conditions
- Aging-related impairments

## WCAG — Web Content Accessibility Guidelines
Four principles:

| Principle | Meaning |
|---|---|
| **Perceivable** | Content must be presented in ways users can perceive |
| **Operable** | Interface must be usable with various inputs (keyboard, voice). Users with physical disabilities may have difficulty pointing the cursor, so everything should be controllable by keyboard |
| **Understandable** | Users must understand how to use the site — each element and intended action should be clear (language switching, tooltips, clear separation of blocks) |
| **Robust** | Content must be compatible with assistive technologies. Developer principle: write clean code without extra lines and errors |

Each principle is tested at 3 levels:

| Level | Meaning |
|---|---|
| **A** | Minimum accessibility |
| **AA** | Mid-level (commonly required) |
| **AAA** | Highest standard, most inclusive |

## Design Considerations by Need

### Visual Impairments (Low Vision)
- Noticeable colour contrast: text should be brighter than the background
- Legible font, with the ability to increase it on the site up to 200%
- **Do not justify** the text
- Ability to change letter and line spacing
- Keyboard control (up/down keys, space bar, Tab)
- No captchas
- No time restrictions — a visually impaired visitor needs more time to explore
- Audio accompaniment to text: listen to the entire site, individual blocks, or transcripts of video
- Spell checking, plus hints on filling in fields
- Prominent call-to-action buttons

### Blindness
- Screen readers are programs that read out all text information on a website
- No captcha or audio version
- Clear page structure, with material divided into paragraphs, headings and subheadings so screen-reader users can find what they need
- Audio transcription of images and video fragments
- Hide unnecessary elements and tooltips from the screen reader's field of vision
- Arrange information so the user can easily perceive it by ear and clearly imagine the site's structure

### Color Blindness
- Avoid using color as the only way to convey information or a call to action
- Let the user customize background and text color
- **High contrast** so shades are distinguishable — *contrast is key*
- Text goes on a blank background
- Underline links or make them bold, to make them easier to perceive

### Dyslexia
- Legible font without serifs, italics, calligraphy or other letter decorations
- Simple, short, clear sentences
- Large indents between main blocks
- Customizable background color, text color and font size
- Illustrations to explain complex material
- No captcha — find other solutions for human recognition
- Avoid italics, underlines, and capital letters (confusing)
- Do not justify text

### Hearing Impairments
- Subtitles
- Transcripts
- *(list was cut off in the raw notes)*

### Motor Disabilities
- Touch control by voice or eye movement
- Ability to use the site without a mouse
- Keyboard control: commands should work with a single key, no complex combinations (includes scrolling)
- **Autofill: a must-have** — saves the user unnecessary movements
- Larger clickable buttons, with more distance between them

### Cognitive and Neurological Disabilities
- Avoid loud and sudden sounds; let the user turn off all audio accompaniment
- Avoid frequent frame changes and unexpected flashes
- An element must not change state more than 3 times per second (can cause an epileptic seizure)
- Simple, convenient navigation to streamline decision-making

### Autism Spectrum Disorders (ASD)
- Simple, clear language — no metaphors, complex structures or artistic images open to interpretation
- Avoid large amounts of information: short, concise text
- Eliminate flickering elements
- Add subtitles to help understanding
- Use breadcrumbs so the user can track their route

### Cognitive Impairment and Dementia
- Simple language without complex phraseological units
- Minimize the number of choices
- Clear, easy navigation without distracting elements
- Avoid long, complex blocks not separated by spaces and images
- Indicate the return path to the main page
- Use breadcrumbs
- Place the menu in the most visible place
- Highlight important information in bold
- Dilute text with illustrations that clearly explain the material

## Inclusive Design Strategies
- Plan for accessibility from the beginning
- Consider a diverse range of users and contexts
- Use plain language
- Create flexible layouts
- Use descriptive labels and tooltips
- Test with real users of various abilities

## Key Takeaways
- Inclusive design improves usability for all
- WCAG provides guidelines to structure efforts
- Consider a wide spectrum of abilities, not just disability

## To Know
- The four WCAG principles (Perceivable, Operable, Understandable, Robust) and levels A / AA / AAA

## Homework
- Revisit netify

## Reflection
*What was the most surprising insight today?*
