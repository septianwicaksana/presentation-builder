---
name: html-presentation-builder
description: Build a complete browser-ready HTML slide deck with embedded CSS, JavaScript, sidebar navigation, and keyboard controls
---

# HTML Presentation Builder

A production skill for creating a complete HTML slide deck with embedded CSS and JavaScript.

## Purpose
Turn presentation content into a browser-ready slide deck optimized for:
- fullscreen display
- recording
- internal company presentations
- external business presentations
- static deployment on Vercel

This skill is universal and does not depend on YouTube notes.
It should work from materials such as:
- product specifications
- company profile notes
- training materials
- technical documentation
- reports
- raw bullet points
- structured outlines
- approved slide plans

## Use this skill when
- the slide outline is already approved or mostly ready
- the user wants a single HTML presentation file
- the user wants a static deck deployable on Vercel
- the user wants a clean browser presentation with keyboard navigation
- the user wants a visual-first presentation instead of a text-heavy deck

## Core objective
Generate a complete HTML file containing:
- all slides
- embedded CSS
- embedded JavaScript
- keyboard navigation
- chapter sidebar navigation
- slide counter
- smooth transitions
- responsive widescreen layout

## Presentation style requirements
- minimal text on each slide
- strong visual hierarchy
- large readable typography
- dark background with light text by default unless the user asks otherwise
- high contrast for recording and presenting
- plenty of whitespace
- clean and modern styling
- one visual message per slide

## Content handling rules
- Build from source materials provided by the user.
- Do not depend on YouTube transcripts unless explicitly given.
- Start directly with meaningful content unless a title slide is clearly needed.
- Turn raw notes into a structured flow before rendering HTML.
- Give each major point its own slide.
- Keep text minimal:
  - short title
  - key phrase
  - important number
  - compact supporting label if needed
- Prioritize visuals over paragraphs.

## Default content flow
Unless the user requests another structure, organize content into:
1. Context / Background
2. Problem / Need / Opportunity
3. Solution / Product / Offering
4. Features / Capabilities
5. Evidence / Data / Specifications
6. Benefits / Use Cases / Impact
7. Summary
8. Closing / Call to Action

For product knowledge decks, likely sections include:
- Application Context
- Product Overview
- Key Features
- Technical Specifications
- Benefits
- Compatibility / Workflow
- Quality / Compliance
- Summary

For company decks, likely sections include:
- Company Overview
- Market Need
- Products / Services
- Capabilities
- Process / Operations
- Quality / Compliance
- Customer Value
- Results / Metrics
- Closing

## Visual design rules
Use CSS to create simple but effective visuals such as:
- metric cards
- process flows
- feature grids
- timelines
- comparison panels
- specification blocks
- bar charts
- line charts
- diagram-like layouts
- icon circles or visual markers

Prefer:
- cards instead of dense text blocks
- highlighted numbers instead of paragraphs
- chart-like visuals instead of tables
- big statements instead of small bullets

Avoid:
- paragraphs
- clutter
- tiny text
- unnecessary decoration
- excessive branding noise
- distracting animations

## Technical requirements
Create a single HTML file with embedded CSS and JavaScript.

The presentation must include:
- keyboard navigation
  - Left Arrow = previous slide
  - Right Arrow = next slide
- current slide number and total slide count in the top-right corner
- chapter navigation sidebar on the left
- clickable chapter navigation
- current chapter highlight
- logical grouping of slides under chapters
- smooth transitions between slides
- fullscreen-friendly layout for recording
- responsive widescreen design

## Interaction rules
- Slides must be navigable with keyboard arrows.
- Clicking a chapter in the sidebar must jump to the first slide of that section.
- The sidebar must reflect the active chapter.
- The slide counter must update on every slide change.
- Navigation must feel smooth and stable.

## HTML structure expectations
The generated HTML should generally include:
- a root presentation container
- a fixed left sidebar for chapters
- a main slide viewport
- one section or container per slide
- a top-right slide counter
- an embedded style block
- an embedded script block

## JavaScript responsibilities
The embedded JavaScript should:
- track the current slide index
- move forward and backward through slides
- update visible slide state
- update the slide counter
- determine the current chapter from slide position
- highlight the active chapter in the sidebar
- support click-to-jump chapter behavior

## Slide design rules
- one idea per slide
- one dominant visual message per slide
- conclusion-led titles when possible
- minimal supporting text
- strong spacing and alignment consistency
- repeatable layout system across slides

## Data visualization rules
- prefer bar charts for comparison
- prefer line charts for trends
- use pie charts only for simple proportions
- use bold numeric slides when one number is the key message
- use layout-based diagrams when concept clarity matters more than precision

## Output location rules
- Default output file: `public/index.html`
- If a deck name is provided: `public/decks/<deck-name>/index.html`
- Put deck-specific assets in the matching `assets/` folder when needed
- Keep source materials out of `public/`

## Output rules
The final output should be the complete HTML file only unless the user explicitly asks for explanation.
The file must be ready to save and open directly in a browser.

## Quality standard
The output should look like a professional company presentation:
- visually clean
- easy to read
- logically structured
- suitable for screen recording
- suitable for internal or external use

## Decision rules
- If the source is raw and messy, organize it before rendering.
- If the content is highly technical, simplify the wording visually while preserving accuracy.
- If information is incomplete, create a sensible structure without inventing unsupported claims.
- If exact figures are provided, highlight them prominently.
- If no brand style is provided, use a restrained modern design with one accent color.

## Pitfalls to avoid
- do not create cramped slides
- do not use long paragraphs
- do not rely on filler text
- do not add distracting animations
- do not bury important points in small text
- do not use tables when a visual summary works better
