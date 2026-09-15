# Day 5

## Topic: Sections

Headings (<h1>–<h6>) communicate hierarch

Search engines use HTML structure to understand what a page
is about.
• A well-structured page with clear headings and meaningful
sections ranks better.
• <main>, <header>, <nav>, <article>, and <footer> help bots
index your page more effectively

HTML5 Outliner - 
What it does:
• Displays how your document is structured by headings
	and sectioning elements
• Shows where headings are missing
• Flags untitled section


What is a section:
- Use <section> to group content
that belongs together

- Every section must include a
heading

- Avoid using <section> as a
generic wrapper — use <div>
for that


Article Vs Section
- Use <article> when content is standalone and could be
syndicated (like a blog post or product feature

- Use <section> when content is related and contributes to
the page's topic

<aside>
• Pull quotes
• Related links
• Definitions
• Ads or widgets
It can have a heading, but it
doesn’t require one.


 Explicit: Created using semantic elements (<section>,
<article>, etc.)
• Implicit: Created only using headings (<h1> to <h6>)
Semantic structure allows browsers and assistive tech to
interpret pages more clearly.

Nesting:
- You can nest sections inside other Sections (Big DEAL)
- Every nested section still needs a header

<nav>
	<ul>
		<li><anchor></li>
		<li><anchor></li>
		<li><anchor></li>
		<li><anchor></li>
	</ul>
</nav>

Navigator is also used in social media links near footer

NAVIGATION TIPS
✅ Always use relative links between pages when working
locally
✅ Test your links before uploading
✅ Use meaningful link text (no "click here")

DOM Structure Example

- Hierarchy:
	- <body> is the parent
	- <header>, <main>, <footer> are siblings
	- <main> has children: <h2> and <p>



## Homework

## Key Terms

HTML structure - is the semantic outline of a webpage—how
elements like headings, paragraphs, images, navigation, and
sections are organized and nested.

<section>, <article>, <nav> define logical regions of content


HTML5 Outliner - tool that will help you find your nesting mistakes



<header> — Intro and page title
<main> — Main content
<footer> — Closing info and contact
Today we add:
✅ <nav> – Groups navigational links
✅ <section> – Thematic grouping of content
✅ <article> – Standalone, reusable content
✅ <aside> – Side content that supports the main area

Explicit Outlines - Created using semantic elements (<section>,
<article>, etc.)

Implicit outlines - Created only using headings (<h1> to <h6>)


<nav> - to group site navigation link
