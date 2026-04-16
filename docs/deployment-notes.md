# Deployment Notes

## Vercel Deployment

1. Connect this repository to a Vercel project.
2. Set the **Output Directory** to `public`.
3. No build step required — this is a static presentation project.
4. Every push to `main` triggers a new deployment automatically.

## Local Preview

```bash
npm run dev
# or
npx serve public
```

## Folder Responsibilities

| Folder | Purpose |
|--------|---------|
| `public/` | Deployable static output — what Vercel serves |
| `public/assets/` | Shared images, icons, logos |
| `src/content/` | Raw source materials (notes, briefs, data) |
| `src/outlines/` | Structured slide plans from the Presentation Strategist |
| `src/working/` | Scratch work and draft notes |
| `docs/` | Deployment and maintenance notes |

## Git Workflow

```bash
git add <files>
git commit -m "feat: describe what you added"
git push origin main
```
