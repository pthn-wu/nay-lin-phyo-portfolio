# Nay Lin Phyo — Portfolio

A single-page portfolio/speaker site implemented from the Claude Design file
`Nay Lin Phyo Portfolio.dc.html`. The `x-dc` template directives (`sc-if`, `sc-for`,
`{{ }}` bindings and the `DCLogic` component script) have been resolved into a
standalone, responsive `index.html` — no build step, no dependencies.

Open `index.html` directly in a browser, or serve the folder over HTTP.

## Design
- Brutalist grid layout with hairline (1.5px) dividers.
- Palette: `#f2f1ee` paper, `#0a0a0a` ink, `#e4341f` red accent.
- Type: Archivo + Archivo Black (Google Fonts).
- Fluid typography via `clamp()`; layout collapses to single column on tablet/mobile.

## Images / `uploads/`
All image assets are in place. A built-in fallback still applies: if any file is ever
missing, that slot shows an on-brand placeholder (a monogram panel for portraits, a text
label for logos) instead of a broken image.

| File in `uploads/`               | Used for                          |
|----------------------------------|-----------------------------------|
| `pasted-1784608569643-0.png`     | Hero portrait                     |
| `pasted-1784298654421-0.png`     | About / on-stage photo            |
| `pasted-1784608820450-0.png`     | Retailer logo — John Lewis        |
| `pasted-1784608850177-0.png`     | Retailer logo — Marks & Spencer   |
| `co-op.svg`                      | Retailer logo — Co-op             |
| `Capital-Logo.png`               | Retailer logo — Capital           |
| `G&G-Logo.png`                   | Retailer logo — Grab & Go         |

To swap any image later, just replace the file of the same name (or, for a new format,
update the one `<img src>` in `index.html`).

The YouTube thumbnail and video links are loaded live from YouTube and need no local file.

## Deploy to Vercel
This is a static site — no build step. `vercel.json` sets clean URLs and asset caching.

**Option A — Vercel CLI (from this folder):**
```bash
npm i -g vercel      # once
vercel               # preview deploy (follow the prompts)
vercel --prod        # production deploy
```
When asked, accept the defaults: framework **Other**, no build command, output = project root.

**Option B — Git + Vercel dashboard:**
1. Push this folder to a GitHub/GitLab/Bitbucket repo.
2. In the Vercel dashboard: **Add New → Project → Import** the repo.
3. Framework preset **Other**, leave Build & Output settings empty, **Deploy**.

Either way the site is live in ~seconds. Remember to add the real images to `uploads/`
(see the table above) so they replace the placeholders on the deployed site.

