# aix-config — public config + site for AI Chat Exporter

This repo does two jobs for the AI Chat Exporter extension:

1. **Hot-fix config** — `selectors.json` is fetched by every installed extension
   (`https://raw.githubusercontent.com/MaqAnquor/aix-config/main/selectors.json`).
   Edit it to fix a platform's selectors and the fix reaches all users in minutes,
   with **no store review**. Source of truth lives in the private repo at
   `src/config/remote-selectors.json`; copy it here when changed.
2. **Website + legal pages** — served free via GitHub Pages:
   - `index.html` → `https://aix.adsit.work/` (landing page)
   - `privacy.html` → the privacy-policy URL used in the store listings
   - `uninstall.html` → the uninstall-feedback page

## One-time setup (founder)

```bash
# from this folder (aix-config-public/)
gh repo create MaqAnquor/aix-config --public --source=. --remote=origin --push
```

Then enable Pages:
**GitHub → repo Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / root → Save.**

Wait ~1 min, then confirm these load:
- https://aix.adsit.work/privacy.html
- https://aix.adsit.work/uninstall.html

Once `privacy.html` loads, paste that URL into the Chrome (and Edge) listing forms.

## Updating a selector later

Edit `selectors.json` (bump `version`, add the platform under `platforms`), commit,
push. Live for all users within minutes.
