# Claude Skills Package for Vercel Presentation Projects

This package contains three reusable skills for a presentation workflow:

1. `01-vercel-git-repo-bootstrapper.md`
2. `02-presentation-strategist.md`
3. `03-html-presentation-builder.md`

## Recommended use order
1. **Vercel Git Repo Bootstrapper**
   - prepare folder structure, Vercel config, and Git workflow
2. **Presentation Strategist**
   - turn source material into a clear slide plan
3. **HTML Presentation Builder**
   - turn the outline into a browser-ready HTML deck

## Install into your repo
Copy the `.claude/skills/` folder into your repository root.

Recommended repository layout:

```text
project-root/
  .claude/
    skills/
  public/
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

## Suggested output locations
- Single main deck: `public/index.html`
- Named deck: `public/decks/<deck-name>/index.html`

## Included files
- `.claude/skills/01-vercel-git-repo-bootstrapper.md`
- `.claude/skills/02-presentation-strategist.md`
- `.claude/skills/03-html-presentation-builder.md`
