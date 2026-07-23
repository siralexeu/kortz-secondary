# The Kortz Center — Secondary Targets Tracker

O pagină HTML de sine stătătoare (fără build, fără dependențe) pentru a explora și sorta lista de secondary targets din heist-ul **The Kortz Center** (GTA Online).

## Ce face

- Afișează toate cele 65 de secondary targets, organizate pe categorii (Painting, Gemstone, Venus Statue, Fertility Statue, Skull Statue, Bracelet, Rings, Ornamental Egg, Necklace, Horse Statue, Crate, Meteorite).
- **Căutare** live după nume sau categorie.
- **Sortare** din dropdown sau prin click pe capul de coloană (min, max, step, weight, nume, categorie).
- **Filtre pe categorie** — selecție unică (click pe un tab activează doar categoria respectivă; "All targets" resetează).
- **Hard mode** — un toggle care adaugă automat 10% la toate sumele afișate.
- **Preview de imagine** — la câteva rânduri (tablouri, statui, bijuterii), o iconiță de ochi arată o previzualizare la hover și o versiune full-screen la click (închidere prin click în afara imaginii sau tasta Escape).
- **Deposit boxes** — secțiune separată cu distribuția de probabilități a plăților.

## Sursa datelor

Valorile de payout sunt preluate din tabelul comunității de pe [GTAWeb.eu](https://www.gtaweb.eu/) și reprezintă intervalul (min–max) pentru dificultatea **easy**, cu increment egal cu valoarea din coloana **Step**.

## Structura fișierului

Totul stă într-un singur fișier: `kortz-center-secondary-targets.html`.

- **CSS** inline în `<style>` — temă vizuală GTA (paletă verde-bani/auriu/negru, fonturi Anton + Roboto Condensed).
- **JavaScript** inline în `<script>`:
  - `DATA` — array cu toate target-urile (tip, nume, min, max, step, weight, și opțional `img` — imaginea codată base64 pentru preview).
  - `DEPOSIT` — array cu distribuția de payout pentru deposit boxes.
  - Logica de randare, sortare, filtrare și lightbox.
- Imaginile de preview sunt încorporate direct ca `data:image/jpeg;base64,...` — nu există fișiere externe, deci pagina funcționează offline și poate fi deschisă direct din orice browser.

## Cum îl folosești

Deschizi fișierul `.html` direct într-un browser (dublu-click) sau îl publici printr-un serviciu de hosting static (ex. GitHub Pages, Netlify, Vercel).

## Adăugarea unei imagini noi pentru un target

1. Decupezi/convertești imaginea în JPEG.
2. O encodezi în base64.
3. Adaugi o linie `const IMG_NUME = "data:image/jpeg;base64,...";` înainte de array-ul `DATA`.
4. Adaugi câmpul `img:IMG_NUME` la rândul corespunzător din `DATA`.

## Status

Proiect activ — imagini adăugate progresiv pe măsură ce sunt disponibile capturi din joc pentru fiecare target.
