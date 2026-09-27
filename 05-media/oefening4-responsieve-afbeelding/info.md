# Oefening 05.4 — Responsieve afbeelding

- **Thema:** Media
- **Moeilijkheidsgraad:** Moeilijk
- **Bestanden:** `index.html` (start), `oplossing.html` (voorbeeld), `styles.css` (styling)

## Opdracht

Bouw een hero-afbeelding met het `<picture>`-element. Toon een andere afbeeldingsvariant per
schermbreedte (`img/landschap-500.jpg`, `-960.jpg` en `-1280.jpg`) en gebruik een `<img>` als
fallback. Beargumenteer in een commentaar waarom je voor jpg kiest (en niet png, svg of webp).

## Vereisten

- [ ] Volledige basisstructuur: `<!DOCTYPE html>`, `<html lang="nl">`, `<head>` met
      `meta charset` en `meta viewport`, en een `<body>`
- [ ] Eén `<h1>` als hoofdtitel van de pagina
- [ ] Een `<picture>` met meerdere `<source media="...">`-varianten
- [ ] Een `<img>` als fallback binnen het `<picture>`
- [ ] De varianten wisselen op basis van schermbreedte (500 / 960 / 1280)
- [ ] Een commentaar waarin je het bestandsformaat beargumenteert (jpg vs png vs svg vs webp)
- [ ] Minstens één HTML-commentaar (`<!-- -->`)

## Tips

- De volgorde van `<source>` telt: de browser neemt de eerste die aan de `media`-voorwaarde voldoet.
- Het `alt`-attribuut staat op het `<img>`-element, niet op de `<source>`-elementen.

## Afbeeldingen

- `img/landschap-500.jpg`, `img/landschap-960.jpg` en `img/landschap-1280.jpg`
  (dezelfde foto in drie breedtes)
