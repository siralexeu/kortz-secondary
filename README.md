# The Kortz Center — Secondary Targets Tracker

A standalone HTML page (no build step, no dependencies) for exploring and sorting the secondary targets list from **The Kortz Center** heist (GTA Online).

## What it does

- Displays all 65 secondary targets, organized by category (Painting, Gemstone, Venus Statue, Fertility Statue, Skull Statue, Bracelet, Rings, Ornamental Egg, Necklace, Horse Statue, Crate, Meteorite).
- **Live search** by name or category.
- **Sorting** via dropdown or by clicking a column header (min, max, step, weight, name, category).
- **Category filters** — single-select tabs (clicking a tab activates only that category; clicking the active tab again deselects it and shows all targets; "All targets" resets).
- **Hard mode** — a toggle that automatically adds 10% to all displayed amounts.
- **Image preview** — on some rows (paintings, statues, jewelry), an eye icon shows a hover preview and a fullscreen version on click (closable by clicking outside the image or pressing Escape).
- **Deposit boxes** — a separate section showing the payout probability distribution.

## Data source

Payout values come from the community-compiled table on [GTAWeb.eu](https://www.gtaweb.eu/) and represent the range (min–max) for **easy** difficulty, moving in increments equal to the value in the **Step** column.

## File structure

Everything lives in a single file: `kortz-center-secondary-targets.html`.

- **CSS** inline in `<style>` — GTA-style visual theme (money-green/gold/black palette, Anton + Roboto Condensed fonts).
- **JavaScript** inline in `<script>`:
  - `DATA` — array with all the targets (type, name, min, max, step, weight, and optionally `img` — the base64-encoded image for the preview).
  - `DEPOSIT` — array with the payout distribution for deposit boxes.
  - Rendering, sorting, filtering, and lightbox logic.
- Preview images are embedded directly as `data:image/jpeg;base64,...` — there are no external files, so the page works offline and can be opened directly in any browser.

## How to use it

Open the `.html` file directly in a browser (double-click), or publish it through a static hosting service (e.g. GitHub Pages, Netlify, Vercel).

## Adding a new image for a target

1. Crop/convert the image to JPEG.
2. Encode it in base64.
3. Add a line `const IMG_NAME = "data:image/jpeg;base64,...";` before the `DATA` array.
4. Add the `img:IMG_NAME` field to the corresponding row in `DATA`.

## Status

Active project — images are being added progressively as in-game captures become available for each target.
