---
aliases: [UI-UX for Developers - Day 17 (User Flows)]
tags: [ui-ux-for-developers, term1, lecture-notes, ux, user-flow, information-architecture, prototyping]
course: "[[UI-UX for Developers]]"
day: 17
---

# UI-UX for Developers — Day 17: User Flows and Information Architecture

**Today's focus:** mapping what users do (user flows) and how content is organized (information architecture). Same symbols as [[Flowcharts]], now for people moving through a product. Next: [[Low-Fidelity Wireframes]].

## What Is a User Flow?
A flowchart of the steps a user takes from the **entry point** to their **goal** on a site or app.
- Consistency across channels builds trust; poor alignment causes confusion and drop-off
- Used in UX research, audits and service design
- Use it **before** the project (decide scenarios and features) and **during** (revise, add or drop features, find problem spots)
- Helps the whole team: designers (user-centred), developers (fewer logic questions, fewer rewrites), PMs (assign tasks), marketers (sales funnels), clients (saves time and money)

### Types
| Type | Shows |
|---|---|
| **Linear** | main steps only, no branching |
| **Conditional** | choices, with a reaction to each path |
| **Modular** | separate modules (individual features) combined in one diagram |
| **Parallel** | several actions happening at the same time |

### Symbols
| Shape | Meaning |
|---|---|
| Circle / oval | start and end of the scenario |
| Rectangle | an action the user takes |
| Diamond | a decision / choice |
| Parallelogram | input or output of information |
| Arrow | direction of movement (can loop back) |

### How to Build One
1. **Ask the client:** product goals, features, what users are expected to do
2. **Describe the user** with a **persona**: name, age, job, interests, goal, needs, problem, motivation, expectation
3. **Pick a scenario:** a realistic situation where they'd use the product
4. **Map the path from A to B:** find the **entry point** (search, social, ad, email, SMS), then each step the user takes, with choice points and connections
5. **Add secondary elements:** notifications, hints, pop-ups
6. **Find bottlenecks** and solve them in the flow (e.g. allergy note on a meal order)
7. **Draw it** in a tool

**Tools:** Miro, Figma / FigJam, Overflow, Flowmap, Lucidchart.

### Tips
- Name the flow so its purpose is obvious
- One flow = **one goal**; keep it moving one direction with minimal branching
- Include a **legend** for the shapes
- Plain language, restrained colour
- Align the flow with the business goals

## Information Architecture (IA)
The invisible **map** of a site: how content is structured so users reach their goal in few clicks. A well-organized site is IA done well; without it content is inaccessible and useless.

### Four Components
| Component | Question it answers |
|---|---|
| **Organization** | how is information structured? |
| **Labelling** | how is it presented / named? |
| **Navigation** | how do users move through it? |
| **Search** | how do users look for it? |

Goal: users always know **where they are, what they can do, and what to expect**.

### IA Design Process
1. **Collect and analyse data:** research, usability tests, audience interviews
2. **Reverse-engineer the navigation flow** from user goals, using key elements as anchor points
3. **Test and refine:** IA is drawn as a flowchart for developers and keeps changing as you learn

Tools: Lucidchart, OmniGraffle, diagrams.net, Figma, Adobe XD, InVision.

### Eight Principles
| # | Principle | Idea |
|---|---|---|
| 1 | **Objects** | treat content as living things with a life cycle and behaviour |
| 2 | **Choice** | too many options overwhelm; show the right ones at the right time (Target's icon menu) |
| 3 | **Disclosure** | reveal enough to guide without overload (REI's search/filters hide irrelevant classes) |
| 4 | **Samples** | show images/previews of what's behind a link (Etsy) |
| 5 | **Entrance doors** | many people don't land on the home page; every page must say where you are (breadcrumbs, persistent cart icon) |
| 6 | **Multiple classification** | offer several ways in: menus, search, filters (Amazon) |
| 7 | **Logical navigation** | stay consistent; a "Shop" dropdown holds only shop categories (Squarespace) |
| 8 | **Growth** | structure must scale; labels not too general, not too specific |

## To Know
- [ ] User flow = steps from entry point to goal; one flow per goal
- [ ] Four types: linear, conditional, modular, parallel
- [ ] Oval = start/end, rectangle = action, diamond = decision, parallelogram = input/output
- [ ] Persona → scenario → entry point → path → extras → bottlenecks → draw
- [ ] IA components: organization, labelling, navigation, search
- [ ] IA principles: objects, choice, disclosure, samples, entrance doors, multiple classification, logical navigation, growth

## Homework
- User flow exercise: pick a common digital task (e.g. booking a flight), map the flow, find pain points and suggest UX/UI improvements

## Reflection
*How can user flow help improve workflow?*
