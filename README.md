# Claude Skills Package for Vercel Presentation Projects

This package contains three reusable skills for a structured presentation workflow.

## Skill workflow

Run these in order:

1. **Vercel Git Repo Bootstrapper** — scaffold folder structure, `vercel.json`, and Git workflow
2. **Presentation Strategist** — turn source material into a structured slide outline
3. **HTML Presentation Builder** — produce a browser-ready HTML deck

## Install into your repo

Copy the `.claude/skills/` folder into your repository root. Each skill is a directory containing a `SKILL.md` file.

```text
.claude/
  skills/
    vercel-git-repo-bootstrapper/
      SKILL.md
    presentation-strategist/
      SKILL.md
    html-presentation-builder/
      SKILL.md
```

## Project structure

```text
project-root/
  .claude/
    skills/
  public/
    index.html
    assets/
      images/
      icons/
      logos/
  src/
    content/       ← raw source materials
    outlines/      ← approved slide plans
    working/       ← scratch notes
  docs/
    deployment-notes.md
  vercel.json
  package.json
  README.md
  .gitignore
```

## Output locations

- Single deck: `public/index.html`
- Named deck: `public/decks/<deck-name>/index.html`

## Local preview

```bash
npm run dev
# or
npx serve public
```

## Vercel deployment

Set **Output Directory** to `public`. No build step required.
