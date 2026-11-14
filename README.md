# Verzekeringsnieuws

Gratis maandelijkse website met het belangrijkste verzekeringsnieuws uit Nederland en daarbuiten.
Statische HTML en CSS, geen build-stap. Live via GitHub Pages: https://verzekeringsnieuws.github.io/

## Structuur

```
index.html          homepage: nieuwste editie bovenaan, daaronder het archief
style.css           gedeelde opmaak
edities/YYYY-MM.html   één pagina per editie (bijv. edities/2026-10.html)
```

## Een nieuwe editie toevoegen (bijv. november 2026)

1. **Kopieer** `edities/2026-10.html` naar `edities/2026-11.html`.
2. **Pas in de nieuwe pagina aan:** `<title>`, de meta description, het kruimelpad, de regel "Editie ... gepubliceerd ...", de `<h1>` en de hele inhoud van `<article>`.
   Houd de opbouw aan: korte inleiding (`<p class="lead">`), `<h2>Nederland</h2>` (eerst, grootst), `<h2>Internationaal</h2>`, per onderwerp een `<h3>` met een korte alinea, en onderaan `<section class="bronnen">` met links naar alle bronnen.
3. **Homepage (`index.html`):**
   - Vervang in `<section class="latest">` de kop, de link, de inleiding en de twee onderwerplijsten door die van de nieuwe editie, en verwijs de links naar `edities/2026-11.html`.
   - Voeg in `<ul class="archive-list">` bovenaan een regel toe voor de nieuwe editie (nieuwste bovenaan). De oude editie blijft staan als archiefregel.
4. **Controleer lokaal:** open `index.html` in een browser, of draai `python3 -m http.server` in deze map en ga naar http://localhost:8000.
5. **Publiceer:**
   ```
   git add -A
   git commit -m "Editie november 2026"
   git push
   ```
   GitHub Pages bouwt automatisch vanaf `main` (root). Na ongeveer een minuut staat de editie live.

## Redactieregels

- Alleen nieuws uit de betreffende kalendermaand; elk feit moet in een bron staan die echt is geraadpleegd.
- Geen geruchten als feit, geen verzekeringsadvies, geen verzonnen cijfers of citaten.
- Richtlijn: 1000 tot 1500 woorden, 4 tot 6 onderwerpen Nederland, 2 tot 4 internationaal.
