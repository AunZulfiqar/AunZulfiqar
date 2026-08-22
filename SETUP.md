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
