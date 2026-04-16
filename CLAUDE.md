# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is a **Claude Skills Package** for creating presentation projects deployable on Vercel. It contains three reusable skills that guide a structured workflow from project setup through content strategy to HTML production.

## Workflow

Always follow this order:

1. **`01-vercel-git-repo-bootstrapper`** — scaffold the repo structure and Vercel config
2. **`02-presentation-strategist`** — turn raw materials into a slide outline
3. **`03-html-presentation-builder`** — produce the final browser-ready HTML deck

## Local preview

```bash
npx serve public
```

## Output locations

- Single deck: `public/index.html`
- Named deck: `public/decks/<deck-name>/index.html`
- Source materials: `src/content/`
- Slide outlines: `src/outlines/`
- Scratch work: `src/working/`

## Skills summary

### 01 — Vercel Git Repo Bootstrapper
Sets up folder structure, `vercel.json`, `package.json`, `.gitignore`, and Git workflow. Defaults to **static-presentation** mode (single `public/index.html`) unless the user explicitly needs multi-deck or app behavior. Never claim a push or deploy succeeded unless it actually ran.

### 02 — Presentation Strategist
Turns raw notes, specs, or drafts into a structured slide plan. Uses the Minto Pyramid Principle (conclusion-led). Adapts tone for audience type: executives, sales, technical, training, or external partners. Always identifies audience, purpose, and core message before drafting.

### 03 — HTML Presentation Builder
Produces a single self-contained HTML file with embedded CSS and JavaScript. Required features: keyboard arrow navigation, chapter sidebar, slide counter, smooth transitions, widescreen layout. Default style: dark background, light text, minimal text per slide, one dominant visual per slide.

## Key constraints across all skills

- Keep source files (`src/`) separate from deployable files (`public/`).
- Do not mix content with output.
- Default to static output; choose app-mode only when explicitly required.
- Do not invent facts or claim operations succeeded when they did not.
