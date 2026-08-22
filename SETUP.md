# Setting up the profile README

GitHub shows a README on your profile page only when it lives in a repository
**named exactly like your username**, on the default branch.

## 1. Create the repo

Repo name must be `AunZulfiqar` (same as the username, case-insensitive), public,
**without** an auto-generated README.

```bash
gh repo create AunZulfiqar --public --description "Profile README"
```

## 2. Push these files

From this folder:

```bash
git init -b main
git add .
git commit -m "feat: profile README"
git remote add origin https://github.com/AunZulfiqar/AunZulfiqar.git
git push -u origin main
```

## 3. Turn on the snake

`.github/workflows/snake.yml` renders the contribution snake and pushes it to an
`output` branch. It runs automatically on push, then twice a day.

If the workflow fails with a permissions error, enable write access for Actions:
**Settings → Actions → General → Workflow permissions → Read and write permissions**.

The snake image 404s until the first successful run finishes. That is expected.

## 4. Fill in the placeholders

| Where | What to change |
|---|---|
| `README.md` line ~29 | `https://linkedin.com/in/YOUR-LINKEDIN` → your real LinkedIn URL |
| `README.md` projects table | Add rows as you publish repos; link the ones that are public |
| `README.md` `git log --experience` | Add real roles, employers, and dates when you have them |

If you don't want the LinkedIn badge at all, delete that one `<a>` line.

## 5. Pin your repos

The README does a lot, but pinned repos sit right under it. Pin
`Insider-Threat-Detection-System` first — it's the strongest thing on the profile.
Go to your profile → **Customize your pins**.

## Notes on the hero

`hero.svg` is hand-written and animated (scan line, pulsing nodes, blinking cursor).
It uses system fonts only, because SVGs loaded through `<img>` cannot fetch webfonts.

To change the name, role, or the stack chips, edit the `<text>` elements near the
bottom of the file — they're plain text, no tooling required.

GitHub caches images through its Camo proxy, so an updated `hero.svg` can take a
few minutes to appear. A hard refresh usually clears it.

## Known provider issues (as of first push)

`github-readme-stats.vercel.app` — the service behind the "GitHub stats" and
"top languages" cards on most profile READMEs — is currently returning
`DEPLOYMENT_PAUSED`. Public mirrors are paused too, or run without an API token
and render an error box instead of a card.

Both cards are therefore commented out in `README.md`, with the exact markup kept
inline so you can paste them back the moment the service recovers. Check with:

```bash
curl -s "https://github-readme-stats.vercel.app/api?username=AunZulfiqar" | head -5
```

The activity-graph image is commented out for a different reason: with a sparse
contribution history it draws a flat line with one spike. Re-enable it when the
graph has some shape to it — the markup is in the same comment block.
