---
name: vercel-git-repo-bootstrapper
description: Setup repo structure, Vercel config, and Git workflow for presentation projects
---

# Vercel Git Repo Bootstrapper

A repository setup and deployment bootstrap skill for creating presentation projects that are ready for Vercel deployment and Git-based collaboration from the start.

## Purpose
Set up a clean project structure that is:
- ready to deploy on Vercel
- easy to maintain in Git
- suitable for presentation workflows
- compatible with the Presentation Strategist and HTML Presentation Builder skills

## Use this skill when
- the user wants a new repository for presentations
- the user wants a folder structure that is ready for Vercel
- the user wants Git-friendly project scaffolding
- the user wants a company presentation project that can hold multiple decks
- the user wants source materials separated from deployable output

## Default mode
Default to **static-presentation** mode unless the user explicitly asks for dynamic application behavior.

Supported modes:
1. **static-presentation**
   - one primary HTML deck
2. **multi-deck-static**
   - multiple decks in one static Vercel project
3. **app-mode**
   - only when the user explicitly needs dynamic routes, authentication, CMS, dashboards, or app logic

## Core instructions
1. Determine the project mode.
2. Create a simple, predictable, production-friendly structure.
3. Keep raw source materials separate from deployable files.
4. Keep Vercel configuration minimal.
5. Keep Git workflow clean and honest.
6. Do not invent remotes, credentials, or branch names.
7. Do not claim a push or deployment succeeded unless it actually did.

## Recommended folder structure
For **static-presentation** mode, use:

```text
project-root/
  .claude/
    skills/
      01-vercel-git-repo-bootstrapper.md
      02-presentation-strategist.md
      03-html-presentation-builder.md
  public/
    index.html
    assets/
      images/
      icons/
      logos/
  src/
    content/
      source-notes.md
      source-data.json
    outlines/
      deck-outline.md
    working/
      scratchpad.md
  docs/
    deployment-notes.md
  vercel.json
  package.json
  README.md
  .gitignore
```

For **multi-deck-static** mode, use:

```text
project-root/
  .claude/
    skills/
      01-vercel-git-repo-bootstrapper.md
      02-presentation-strategist.md
      03-html-presentation-builder.md
  public/
    index.html
    decks/
      emerald-pedicle-screw/
        index.html
        assets/
      company-profile/
        index.html
        assets/
      product-training/
        index.html
        assets/
    assets/
      images/
      icons/
      logos/
  src/
    content/
    outlines/
    working/
  docs/
  vercel.json
  package.json
  README.md
  .gitignore
```

## Directory responsibilities
- `.claude/skills/`
  - stores reusable project skills
- `public/`
  - stores deployable static output
- `public/assets/`
  - shared assets across decks
- `public/decks/<deck-name>/`
  - deck-specific output for multi-deck projects
- `src/content/`
  - raw source materials from the user
- `src/outlines/`
  - structured slide plans and approved outlines
- `src/working/`
  - temporary drafting notes and scratch work
- `docs/`
  - deployment notes, maintenance notes, usage notes

## Bootstrap files to create
Create these files when missing:

### `vercel.json`
Keep it minimal for static presentation projects.
Only add configuration when needed for:
- rewrites
- redirects
- clean routes
- headers
- project-specific behavior

A minimal static example is acceptable:

```json
{
  "$schema": "https://openapi.vercel.sh/vercel.json"
}
```

### `package.json`
Use a lightweight package file for identification and optional scripts.
Do not force a build step for static presentation projects.

Recommended baseline:

```json
{
  "name": "company-presentation-deck",
  "private": true,
  "version": "1.0.0",
  "scripts": {
    "dev": "npx serve public",
    "start": "npx serve public"
  }
}
```

### `README.md`
Explain:
- project purpose
- folder structure
- where source materials go
- where generated HTML goes
- how to preview locally
- how to deploy with Vercel
- how to use Git for commit and push

### `.gitignore`
Ignore:
- `node_modules/`
- `.vercel/`
- `.DS_Store`
- temporary local files
- editor-specific cache files when useful

## Git workflow rules
When execution access is available:
- initialize Git if missing
- stage files
- create a clear first commit
- add a remote only if the user provides one
- push only when remote and authentication are available

When remote or auth is missing:
- do not pretend push succeeded
- provide exact commands instead

Use clear commit messages such as:
- `chore: bootstrap vercel presentation repo`
- `feat: add presentation strategist skill`
- `feat: add html presentation builder`
- `feat: add emerald pedicle screw deck`
- `docs: update deployment instructions`

## Output location rules
- Default final deck location: `public/index.html`
- If a deck name is provided: `public/decks/<deck-name>/index.html`
- Put deck-specific assets beside the deck when appropriate
- Keep source content out of `public/`

## Decision rules
- default to static output
- choose app-mode only when explicitly required
- prefer simplicity over cleverness
- separate input, outline, and final output
- keep naming consistent and predictable
- keep deployable files easy to find

## Output expectations
When asked to bootstrap a project, produce:
- the final folder structure
- the list of files created
- the content of important bootstrap files
- Git commands executed or recommended
- deployment assumptions
- the next best step

## Pitfalls to avoid
- do not mix source files with deployable files
- do not overengineer the structure
- do not assume framework mode when static output is enough
- do not claim push or deploy worked when it did not
- do not bury the final presentation in an unclear location
