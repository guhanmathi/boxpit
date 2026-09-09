# Boxpit website

Static site for the Boxpit app — a landing page (`index.html`) and the
**privacy policy** (`privacy.html`) that Google Play requires.

No build step. Plain HTML + one CSS file + images in `assets/`.

## Live URLs

Repo: <https://github.com/guhanmathi/boxpit> · deployed via GitHub Pages.

| Page | URL |
|---|---|
| Landing page | <https://guhanmathi.github.io/boxpit/> |
| Privacy policy | <https://guhanmathi.github.io/boxpit/privacy.html> |

## What Play Console needs

| Console field | URL to paste |
|---|---|
| Store listing → **Privacy policy** | `https://guhanmathi.github.io/boxpit/privacy.html` |
| Store listing → **Website** (optional) | `https://guhanmathi.github.io/boxpit/` |

## Deploy to GitHub Pages — pick one

### Option A — dedicated repo (cleanest URL: `…github.io/boxpit/`)
```bash
# from a fresh clone/copy of just this folder
cd website
git init -b main
git add .
git commit -m "Boxpit site"
gh repo create boxpit --public --source=. --push     # or create the repo in the GitHub UI and push
```
Then GitHub → repo **Settings → Pages → Build and deployment → Source: Deploy from a branch →
`main` / `/ (root)`** → Save. Live in ~1 min at `https://<user>.github.io/boxpit/`.

### Option B — subfolder of your existing `<user>.github.io` repo
Copy this `website/` folder into that repo as `boxpit/`, push. It serves at
`https://<user>.github.io/boxpit/` with Pages already enabled there.

### Option C — subfolder of this app repo (if you make this repo public + enable Pages)
Settings → Pages → Source: `boxpit-rebuild` branch, `/website` folder. URL would be
`https://<user>.github.io/<repo>/`.

## After deploying

1. Open `privacy.html` in a browser, confirm it loads and the contact email is right.
2. Paste the two URLs into Play Console (table above).
3. If you change the app's data handling later, update `privacy.html` and its
   "Last updated" date.

## Editing

- Contact email is `mguhan89@gmail.com` in both HTML files — change in both if it moves.
- Colours/spacing: `style.css` (`--red`, `--carbon`, etc.).
- The privacy text mirrors the app's actual code (no accounts / SDKs; feeds + `api.jolpi.ca`
  + publisher image CDNs as the only network destinations). Keep it truthful if the app
  changes — it is a legal document and must match the Data Safety form in Play Console.
