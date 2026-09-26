# HTML/CSS-oefeningen — Generatie-ontwerp (spec)

> Datum: 2026-09-26
> Status: ter review
> Bron: `alle_oefeningen.md` (Rogier van der Linde, 8 lessen)
> Doel: de gedeelde conventies vastleggen die gelden voor álle 32 oefeningen, zodat de
> generatie deterministisch en consistent verloopt, thema per thema.

---

## 1. Scope & doel

Een volledige VS Code-oefeningenmap genereren voor een HTML-cursus: **8 thema's × 4 oefeningen
= 32 oefenmappen**, plus een overzichts-`index.html` en een `README.md`.

- **Voor wie:** studenten die **extra** willen oefenen — volledig **optioneel**, niet verplicht,
  en **zonder nakijker**. `oplossing.html` dient enkel als zelf-check-referentie.
- **Taalregel:** alle *gegenereerde inhoud* (HTML-commentaar, `info.md`, teksten op de pagina,
  `alt`-teksten, `title`-attributen) is **Nederlands**. Technische notatie (tags, attributen,
  bestandsnamen) blijft uiteraard Engels.
- **Lesbron:** https://rogiervdl.github.io/HTML-course/ — elke oefening mag/moet vanaf les 2
  ook elementen uit eerdere lessen hergebruiken (cumulatief).
- **Student rol:** de student bouwt de inhoud grotendeels zelf; CSS wordt als *service* geleverd
  zodat de focus op HTML ligt.

---

## 2. Mapstructuur (definitief)

```
html-cursus-oefeningen/          ← root = deze repository
├── index.html                   (overzichtspagina, links naar alle oefeningen)
├── README.md                    (uitleg mappen + gebruik)
├── 01-syntax/
│   ├── oefening1-mijn-eerste-pagina/
│   │   ├── index.html           (startbestand — student vult aan)
│   │   ├── oplossing.html       (afgewerkte versie)
│   │   ├── styles.css
│   │   ├── info.md              (instructies student)
│   │   └── img/                 (enkel waar afbeeldingen nodig)
│   ├── oefening2-code-opschonen/
│   ├── oefening3-metadata-en-links/
│   └── oefening4-menukaart/
├── 02-tekst/   … (oefening1-receptpagina, oefening2-persoonlijk-profiel,
│                    oefening3-faq-accordeon, oefening4-wetenschappelijk-artikel)
├── 03-links/   … (oefening1-interne-navigatie, oefening2-contactpagina,
│                    oefening3-faq-inhoudsopgave, oefening4-portfolio-linkoverzicht)
├── 04-tabellen/… (oefening1-klasoverzicht, oefening2-lesrooster,
│                    oefening3-prijzentabel-hotel, oefening4-resultatenoverzicht)
├── 05-media/   … (oefening1-foto-bijschrift, oefening2-stappenplan-in-beeld,
│                    oefening3-video-kaart-embedden, oefening4-responsieve-afbeelding)
├── 06-formulieren/… (oefening1-login, oefening2-contactformulier,
│                    oefening3-enquete-inschrijving, oefening4-webshop-bestelformulier)
├── 07-structureren/… (oefening1-basis-pagina-skelet, oefening2-blogartikel-zijbalk,
│                    oefening3-van-div-soep, oefening4-nieuwssite-layout)
└── 08-samenvatting/… (oefening1-debug, oefening2-persoonlijk-cv,
                        oefening3-mini-website-hobby, oefening4-eindproject-website)
```

**Naamconventie:** lowercase, koppeltekens, `oefening<n>-<korte-titel>`. De definitieve naam uit
`alle_oefeningen.md` geldt (`oefening3-metadata-en-links`, niet `metadata-links`). In de tekst
hieronder worden de exacte titels per oefening overgenomen uit de tabel in `alle_oefeningen.md`.

---

## 3. Huisregels (geldt voor élke oefening, én voor de `oplossing.html`)

De oplossing én het startbestand volgen dezelfde huisregels:

- Volledige basisstructuur: `<!DOCTYPE html>`, `<html lang="nl">`, `<head>` met
  `<meta charset="utf-8">`, `<meta name="viewport" content="width=device-width, initial-scale=1">`,
  `<title>`, en `<link rel="stylesheet" href="styles.css">`.
- Kleine letters voor tags/attributen; dubbele quotes rond attribuutwaarden; consequente
  inspringing (tabs óf spaties, geen mix — nooit beide door elkaar).
- Geldige nesting: geen blocklevel in inline, geen `<p>` rond blocklevel, blocklevel kan meestal
  geen blocklevel bevatten waar de bron dat verbiedt.
- Geen `<b>`/`<i>` (gebruik `<strong>`/`<em>`), geen layout-tabellen, geen `<div>`/`<span>`
  waar een semantisch element past.
- Speciale karakters gecodeerd waar nodig (`&amp;`, `&lt;`, `&gt;`, `&copy;`, …).
- Elke `<img>` heeft een relevant `alt`-attribuut.
- Correcte titelhiërarchie: max één `<h1>` per pagina.
- Minstens één HTML-commentaar.

---

## 4. Bestandsconventies per oefening

### 4.1 `index.html` (startbestand)

Twee varianten:

**(A) Normale oefening** — bovenaan een commentaarblok met de opdracht, daaronder enkel de
correcte basisstructuur met een grotendeels leeg `<body>`:

```html
<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>…</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Vul hier je HTML verder aan -->

</body>
</html>
```

Het commentaarblok bovenaan bevat telkens: **oefening** (bv. "02.1"), **titel**, **thema**,
**moeilijkheidsgraad**, **opdracht** (1–3 zinnen), en optioneel **tips**. Stuur-commentaren in de
`<body>` (`<!-- Plaats hier je navigatielijst (ul) -->`) enkel waar houvast gewenst is — géén
invul-oefeningen, géén voorgedrukt stappenplan.

**(B) Fout-herstellende oefening** — enkel bij **01.2 (Code opschonen)**, **07.3 (Van div-soep)**,
**08.1 (Debug-oefening)**. Hier bevat `index.html` wél de te verbeteren ("foute") HTML, omdat de
student die moet opsporen en corrigeren. De opdracht staat nog steeds als commentaarblok bovenaan.

### 4.2 `oplossing.html`

Afgewerkte, volledige versie die aan álle vereisten uit `info.md` voldoet, met dezelfde
`styles.css`. Is een **zelf-check-referentie voor de student** (er is geen nakijker). Bij
fout-herstellende oefeningen is `oplossing.html` de *gecorrigeerde* versie.

### 4.3 `styles.css`

Zie §5. Eén bestand per oefening, kort en overzichtelijk.

### 4.4 `info.md`

Zie §6.

### 4.5 `img/`

Enkel waar afbeeldingen nodig zijn (zie `alle_oefeningen.md`, "Benodigde afbeeldingen"). We
**downloaden** de open-source afbeeldingen (Wikimedia Commons) naar `img/` zodat de map
self-contained is. Bestandsnaam: beschrijvende kebab-case, bv. `joshua-tree.jpg`. Verwijzing in
HTML gebeurt met relatief pad `img/<bestand>`.

### 4.6 `referentie.png`

We genereren **geen** screenshots (geen browser beschikbaar). Bij de 13 "aanbevolen" oefeningen
komt er een duidelijk gemarkeerde regel in `info.md` dat hier optioneel een full-page screenshot
als visueel voorbeeld kan worden toegevoegd. De lijst staat in `alle_oefeningen.md` ("Waar is een
referentie-screenshot aanbevolen?").

---

## 5. CSS-huisstijl (geldt voor elke `styles.css`)

Elke `styles.css` deelt dezelfde basis, met één accentkleur per thema.

### 5.1 Vaste basis (alle thema's)

- Reset: `* { box-sizing: border-box; margin: 0; padding: 0; }`
- Font: `font-family: "Segoe UI", system-ui, -apple-system, sans-serif;`
- Achtergrond: rustige neutrale tint; inhoud in een witte "kaart" met `max-width: 720px`,
  gecentreerd (`margin: 0 auto`), zachte radius + subtiele schaduw, padding.
- Typografie: `line-height: 1.6`; zachte tekstkleur (`#333`/dark-equivalent); koppen groter en
  vetter; kleuren met voldoende contrast (WCAG AA).
- **Light + dark mode** via `prefers-color-scheme`, tokens op `:root` (light) en
  `@media (prefers-color-scheme: dark)`; body krijgt expliciete achtergrondkleur.

### 5.2 Accentkleuren per thema (primair + lichte tint)

| Les | Naam | Primair | Lichte tint (achtergrond/accent-light) |
|-----|------|---------|----------------------------------------|
| 01 | Syntax | `#5b6b7a` (blauw-grijs) | `#eef1f4` |
| 02 | Tekst | `#2f855a` (groen) | `#e6f4ec` |
| 03 | Links | `#4f46e5` (indigo) | `#eae8fb` |
| 04 | Tabellen | `#c2410c` (oranje) | `#fdece2` |
| 05 | Media | `#db2777` (roze) | `#fce7f0` |
| 06 | Formulieren | `#0d9488` (teal) | `#e0f5f2` |
| 07 | Structureren | `#7c3aed` (paars) | `#efe9fd` |
| 08 | Samenvatting | `#2563eb` (blauw) | `#e8f0fe` |

Gebruik: koppen/randen/links/knoppen in primair; subtiele achtergronden/`mark`/`thead` in de
lichte tint. Accentkleur mag niet de HTML-huisregels omzeilen.

### 5.3 Extra styling per les (bovenop de basis)

| Les | Extra CSS |
|-----|-----------|
| 01 | body/typografie; `header`, `nav`, `footer`, menu-lijsten |
| 02 | `h1`–`h6`, `blockquote`, `address`, `ul`/`ol`/`dl`, `details`/`summary`, `abbr`, `mark` |
| 03 | linkkleuren + `:hover`, menu/secties, `scroll-behavior: smooth` |
| 04 | tabellen: randen, zebra (`tbody tr:nth-child(even)`), `caption`, `thead`-achtergrond |
| 05 | `figure`/`figcaption`, `img`/`iframe` `max-width:100%`, responsive embeds |
| 06 | `fieldset`/`legend`, label+control-layout, focus-ring, knoppen |
| 07 | `header`/`main`/`footer`/`nav`, `article`, `aside`, `section` (ruimte, scheiding) |
| 08 | combinatie van alles; nadruk op samenhangende, verzorgde lay-out |

**CSS-regels:** puur presentatie; semantische selectors (tag/class), geen overbodige
wrapper-`<div>`'s; kort en overzichtelijk; de student hoeft ze niet te begrijpen maar mag kijken.

---

## 6. `info.md`-template

Elke `info.md` volgt dit vaste stramien (Nederlands):

```markdown
# Oefening <les>.<nr> — <Titel>

- **Thema:** <thema>
- **Moeilijkheidsgraad:** <makkelijk|gemiddeld|moeilijk|…>
- **Bestanden:** `index.html` (start), `oplossing.html` (voorbeeld), `styles.css` (styling)

## Opdracht
<1–3 zinnen: wat de student moet bouwen>

## Vereisten
- [ ] <concrete vereiste 1>  (checklist, afgeleid uit "Wat moet sowieso in de oefeningen komen")
- [ ] <vereiste 2>
- …

## Tips
- <optioneel: huisregel of valkuil om op te letten>

## Afbeeldingen
- <welke afbeelding(en) in `img/`, of "eigen foto mag", of "geen lokale afbeeldingen">
```

Bij de 13 "aanbevolen"-oefeningen komt extra de regel:

```markdown
## Referentie
> 📷 **Optioneel voorbeeld:** hier kan een full-page screenshot (`referentie.png`) van het
> afgewerkte resultaat worden toegevoegd.
```

---

## 7. Afbeeldingen: bronnen & aanpak

- We downloaden de open-source afbeeldingen uit `alle_oefeningen.md` (§ "Afbeeldingsbronnen")
  naar de `img/`-map van de betreffende oefening (via curl/PowerShell).
- Als een download faalt (netwerk/URL), valt de oefening terug op een placeholder-opmerking in
  `info.md` ("voeg zelf een afbeelding toe") en een `<img>` met leeg/aan te vullen `src` in
  `index.html` — nooit een gebroken remote-URL.
- Oefeningen die "eigen foto mag" zijn, krijgen in `info.md` de keuze: eigen foto meebrengen óf
  de voorziene afbeelding gebruiken.
- Oefeningen met video/kaart (05.3) en icon fonts (02.4) hebben géén lokale afbeeldingen nodig;
  die gebruiken resp. `<iframe>`-embeds en een iconfont-CDN.

---

## 8. Validatie-aanpak

- Elke `oplossing.html` en `index.html` wordt handmatig nageleefd op de huisregels uit §3
  (nesting, quotes, lowercase, `alt`, geen `<b>`/`<i>`, titelhiërarchie, geldige tabel/form).
- Voor de fout-herstellende oefeningen (01.2, 07.3, 08.1) worden de opzettelijke fouten
  expliciet genoteerd in een apart intern lijstje (niet in de student-`info.md`).
- De W3C-validator (https://validator.w3.org/#validate_by_input) wordt in `info.md` als
  controlestap vermeld waar `alle_oefeningen.md` dat vereist (les 08).

---

## 9. Generatie-volgorde (thema per thema)

1. **01 Syntax** → review → genereren → 2. **02 Tekst** → … t/m **08 Samenvatting**.
2. Per thema: eerst de 4 oefeningen concreet voorleggen (startbestand-inhoud, oplossing-inhoud,
   accentkleur, vereisten-checklist), goedkeuren, dan genereren.
3. Als laatste: root-`index.html` (overzicht met links naar alle oefeningen) + `README.md`.
