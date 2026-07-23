# The Kortz Center — Secondary Targets Tracker

A standalone HTML page (no build step, no dependencies) for exploring and sorting the secondary targets list from The Kortz Center heist (GTA Online). Search, sort, filter by category (click again to deselect), toggle hard mode (+10%), and preview item images — all in one `.html` file you can open offline in any browser.

Everything — CSS, JS, and preview images (base64-encoded) — is inline in the single HTML file. To add a new image: base64-encode it, add `const IMG_NAME = "data:image/jpeg;base64,...";` above the `DATA` array, then add `img:IMG_NAME` to that target's entry.

**Status:** active — images being added as in-game captures become available.
