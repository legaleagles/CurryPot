# CurryPot

Daily menu board + WhatsApp pickup booking for a local curry-point business.

## How it works
- `index.html` — the site. No build step, plain HTML/CSS/JS.
- `menu-today.json` — the day's menu. Edit this file each morning; the site reads it live.
- `images/` — dish photos, referenced by `menu-today.json`.

## Updating the menu each day
1. Open `menu-today.json` in GitHub (or the GitHub mobile app).
2. Edit the `date`, `chefPick` (must match an item `id`), and the `breakfast` / `lunch` arrays:
   - `available: false` shows the item greyed out with a "Sold out" tag instead of removing it.
   - `price` is a plain number (rupees, no symbol).
   - `img` points to a file in `images/`.
3. Commit the change directly on the `main` branch — GitHub Pages redeploys automatically in under a minute.

## Photos
The site automatically shows a matching stock photo for common dishes (idly, vada, dosa, biryani, sambar, etc.) when `img` is left as `""` — so it looks good from day one even with no photos uploaded.

To use your own photo instead: upload the image file into `images/` (GitHub → Add file → Upload files), then set that item's `img` in `menu-today.json` to `images/yourfile.jpg`. If that file is ever missing or fails to load, the site quietly falls back to the stock photo instead of showing a broken image.

## Setting the WhatsApp number
Edit `phoneWhatsApp` in `menu-today.json` — country code, no `+` or spaces (e.g. `919876543210`).

## Enabling GitHub Pages
Settings → Pages → Source: `main` branch, `/ (root)` folder → Save.
The live site will appear at `https://legaleagles.github.io/CurryPot/`.

## Next steps (not yet built)
- Auto-switch breakfast/lunch board based on time of day.
- Move orders from WhatsApp-only to a Google Sheet via a simple form backend.
