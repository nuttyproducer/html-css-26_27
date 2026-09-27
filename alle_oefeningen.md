# HTML-cursus — Oefeningenplan

> Dit document is gebaseerd op de 8 lessen van de HTML-cursus van Rogier van der Linde
> (https://rogiervdl.github.io/HTML-course/). Per les vind je: een beknopte uitleg van de
> theorie, wat sowieso verplicht in de oefeningen moet terugkomen, en 4 concrete oefeningen
> (titel, thema, moeilijkheidsgraad, korte beschrijving).
>
> **Doel van dit document:** dit dient als bouwplan/prompt voor Claude Code om een volledige
> VS Code oefeningenmap te genereren (met per les een submap, per oefening een los HTML-bestand
> met opdracht in commentaar, en eventueel een oplossingsbestand).
>
> **Opbouw:** de oefeningen zijn cumulatief — vanaf les 2 mag/moet je ook elementen uit vorige
> lessen hergebruiken (basisdocument, correcte layout-regels, etc.). Moeilijkheidsgraad loopt
> per les op van makkelijk → moeilijk.

---

## Inhoudstafel

1. [01. Syntax](#01-syntax)
2. [02. Tekst](#02-tekst)
3. [03. Links](#03-links)
4. [04. Tabellen](#04-tabellen)
5. [05. Media](#05-media)
6. [06. Formulieren](#06-formulieren)
7. [07. Structureren](#07-structureren)
8. [08. Samenvatting](#08-samenvatting)

---

## 01. Syntax

**Link:** https://rogiervdl.github.io/HTML-course/01_syntax.html

### Beknopte uitleg
HTML geeft **structuur en betekenis** aan tekst via **tags**, **attributen** en **elementen**.
Browsers negeren witruimte/hoofdlettergebruik, maar in deze cursus gelden vaste **huisregels**:
kleine letters voor tags/attributen, dubbele quotes rond attribuutwaarden, consequente
inspringing (tabs óf spaties, geen mix). Elke pagina heeft een verplichte basisstructuur
(`<!DOCTYPE html>`, `<html lang="...">`, `<head>` met `<meta charset>` en `<title>`, `<body>`).
Belangrijke begrippen: tag/element/attribuut, leeg vs. niet-leeg element, blocklevel vs. inline,
nestingregels (blocklevel kan meestal geen blocklevel bevatten, inline geen blocklevel), en
HTML-commentaar `<!-- -->`.

### Wat moet sowieso in de oefeningen komen
- Volledige, geldige basisstructuur: `<!DOCTYPE html>`, `<html lang="nl">`, `<head>`
  (`meta charset="utf-8"`, `meta viewport`, `<title>`), `<body>`
- Correcte huisregels: kleine letters, dubbele quotes, consequente inspringing (Shift-Alt-F in
  VS Code)
- Minstens één HTML-commentaar
- Correct gebruik van lege vs. niet-lege elementen en geldige nesting (geen `<p>` in `<img>`,
  geen blocklevel in inline, ...)

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Mijn eerste pagina | Jezelf voorstellen | Heel makkelijk | Vanaf nul (of met `html5`+TAB snippet) een correcte basispagina bouwen met titel, één paragraaf tekst over jezelf en een afbeelding. Focus ligt volledig op de verplichte basisstructuur. |
| 2 | Code opschonen | Foute HTML-snippet herstellen | Makkelijk | Een kant-en-klare, "foute" HTML-pagina wordt gegeven (hoofdletters in tags, enkele quotes, geen quotes, inconsistente inspringing). De student moet ze herschrijven volgens de huisregels van deze cursus. |
| 3 | Metadata & links | Pagina over een hobby | Gemiddeld | Basispagina bouwen met extra metatags (`description`, `keywords`, `author`) en een `<link rel="icon">` + `<link rel="stylesheet">`. Test of de student het verschil tussen `<head>`-inhoud en `<body>`-inhoud begrijpt. |
| 4 | Menukaart met commentaar | Restaurantmenu | Gemiddeld–moeilijk | Een geneste structuur bouwen (bv. categorieën met content) waarbij de student zelf moet nadenken over correcte nesting (wat mag wel/niet in elkaar zitten) en een deel van de code tijdelijk "uitschakelen" met commentaar. |

[⬆ terug naar boven](#inhoudstafel)

---

## 02. Tekst

**Link:** https://rogiervdl.github.io/HTML-course/02_tekst.html

### Beknopte uitleg
Blocklevel tekstelementen structureren de inhoud: titels `<h1>`–`<h6>` (hiërarchisch, max één
`<h1>` per pagina, hoe belangrijker hoe lager het nummer), `<p>` voor doorlopende tekst,
`<blockquote>` voor citaten, `<address>` voor contactinfo (max één per pagina),
`<ul>`/`<ol>`/`<dl>` voor lijsten, `<details>`/`<summary>` voor uit-/inklapbare content (met
`name`-attribuut voor een accordeon/FAQ). Inline elementen geven betekenis binnen een zin:
`<strong>`/`<em>` (nooit als vervanging voor vet/schuin — dat is CSS), `<sub>`/`<sup>`,
`<mark>`, `<small>`, `<abbr title="...">`. `<b>` en `<i>` zijn **niet toegelaten** in deze
cursus. Speciale karakters moeten gecodeerd worden (`&lt;`, `&gt;`, `&amp;`), en UTF-8 laat ook
symbolen, emoji's en icon fonts (Google Icons, FontAwesome) toe.

### Wat moet sowieso in de oefeningen komen
- Correcte titelhiërarchie (max één `<h1>`, logische opbouw h2 → h3...)
- Minstens één van elk: `<p>`, `<ul>` of `<ol>`
- Correct/betekenisvol gebruik van `<strong>` en/of `<em>` (niet als opmaak, niet als hele zin)
- Geen gebruik van `<b>` of `<i>`
- Correcte codering van speciale karakters waar nodig (`&amp;`, `&lt;`, `&gt;`)

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Receptpagina | Kookrecept | Makkelijk | Titel, korte intro-paragraaf, ingrediëntenlijst (`<ul>`) en genummerde bereidingsstappen (`<ol>`). Test basis lijstjes + titelgebruik. |
| 2 | Persoonlijk profiel | Voorstelling van jezelf of een fictief personage | Gemiddeld | Titelhiërarchie (h1 naam, h2 secties zoals "over mij", "hobby's"), `<address>` met contactgegevens, een `<blockquote>` met favoriete quote, en correct gebruik van `<strong>`/`<em>`. |
| 3 | FAQ-accordeon | Veelgestelde vragen (vrij te kiezen onderwerp) | Gemiddeld | Minstens 4 vragen met `<details name="faq">` zodat het een accordeon vormt, plus een `<dl>` met een paar begrippen en hun definitie. |
| 4 | Wetenschappelijk of technisch artikel | Bv. scheikunde, wiskunde of een IT-blogpost | Moeilijk | Combineert `<sub>`/`<sup>` (formules), `<abbr>` (afkortingen met title), `<mark>` (belangrijke passages), karakterentiteiten (`&amp;`, `&copy;`, `&rarr;`...) en optioneel een icon font (Google Icons of FontAwesome) voor sociale-mediaknoppen onderaan. |

[⬆ terug naar boven](#inhoudstafel)

---

## 03. Links

**Link:** https://rogiervdl.github.io/HTML-course/03_links.html

### Beknopte uitleg
Een hyperlink (`<a href="...">`) verwijst naar een URL, die absoluut (externe bron), relatief
(interne bron t.o.v. de huidige map) of root-based kan zijn. Linktekst moet **relevant en
betekenisvol** zijn (niet "klik hier") — belangrijk voor blinden en zoekmachines. Het `title`-
attribuut geeft een tooltip/verduidelijking, `aria-label` is nodig bij gelinkte afbeeldingen/
iconen zonder zichtbare tekst. Speciale protocollen: `mailto:`, `tel:`, `sms:`. Ankers maken
interne links binnen dezelfde pagina mogelijk via een `id` en een `href="#id"`.

### Wat moet sowieso in de oefeningen komen
- Minstens één relatieve en één absolute URL (of uitleg waarom niet van toepassing)
- Betekenisvolle linkteksten (nooit "klik hier")
- Minstens één `title`-attribuut op een link
- Minstens één anker (interne link binnen dezelfde pagina)

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Interne navigatie | Eénpaginasite met secties (bv. "over mij / hobby's / contact") | Makkelijk | Een `<ul>`-menu bovenaan met ankers die linken naar secties verderop op dezelfde pagina (`id` + `href="#id"`). |
| 2 | Contactpagina | Persoonlijke of fictieve bedrijfscontactpagina | Gemiddeld | `<address>` met `mailto:`-, `tel:`- en eventueel `sms:`-links, elk met een duidelijke, betekenisvolle linktekst. |
| 3 | FAQ met inhoudsopgave | Veelgestelde vragen (mag hergebruikt worden uit les 2) | Gemiddeld | Bovenaan een lijst met links naar elke vraag (ankers), en onderaan elke vraag een "terug naar boven"-anker. |
| 4 | Portfolio / linkoverzicht | Verzameling van eigen werk, favoriete sites of bronnen | Moeilijk | Mix van relatieve links (naar andere fictieve pagina's), absolute externe links, een gelinkte afbeelding met `title` én `aria-label`, en correcte combinatie van alles uit les 2 en 3. |

[⬆ terug naar boven](#inhoudstafel)

---

## 04. Tabellen

**Link:** https://rogiervdl.github.io/HTML-course/04_tabellen.html

### Beknopte uitleg
Tabellen zijn **enkel voor tabulaire data** (spreadsheet-achtige gegevens), nooit voor layout.
Basiselementen: `<table>`, `<caption>` (bijschrift), `<tr>` (rij), `<th scope="col|row">`
(kopcel), `<td>` (gewone cel). Optioneel: `<thead>`/`<tbody>`/`<tfoot>` voor secties, en
`<colgroup>`/`<col>` om kolommen te groeperen. Met `colspan`/`rowspan` kunnen cellen meerdere
kolommen/rijen overspannen.

### Wat moet sowieso in de oefeningen komen
- Enkel gebruiken voor échte tabulaire data (nooit voor layout)
- Een `<caption>` die de tabel beschrijft
- Correct gebruik van `<th scope="col">` en/of `<th scope="row">`
- Minimaal een basisstructuur met `<tr>`/`<td>`, uitbreidend per oefening naar meer geavanceerde
  elementen

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Klasoverzicht | Scores van klasgenoten per vak | Makkelijk | Eenvoudige tabel met enkel `<table>`, `<tr>`, `<td>` (nog geen koppen), om het basisprincipe van rijen/kolommen te begrijpen. |
| 2 | Lesrooster | Weekschema of menukaart van de week | Gemiddeld | Tabel met `<caption>` en `<th scope="col">` voor de kolomkoppen (bv. dagen) en/of `<th scope="row">` voor de rijkoppen (bv. lesuren). |
| 3 | Prijzentabel hotel/reisorganisatie | Kamerprijzen per seizoen/type | Gemiddeld–moeilijk | Tabel waarbij `colspan` en `rowspan` nodig zijn (bv. een titel die over meerdere kolommen loopt, of een kamertype dat voor meerdere seizoenen dezelfde prijs heeft). |
| 4 | Volledig resultatenoverzicht | Examenresultaten of sportcompetitie-stand | Moeilijk | Volledige tabel met `<thead>`, `<tbody>`, `<tfoot>` (bv. gemiddelde/totaal in de footer) én `<colgroup>`/`<col>` om bepaalde kolommen visueel te groeperen. |

[⬆ terug naar boven](#inhoudstafel)

---

## 05. Media

**Link:** https://rogiervdl.github.io/HTML-course/05_media.html

### Beknopte uitleg
Vuistregel: **inhoud** hoort in HTML, **design** (achtergronden, grafische effecten) hoort in
CSS. Bestandsformaten hebben elk hun sterktes (jpg voor foto's, png/svg voor vlakken/logo's,
webp als modern alternatief, gif voor eenvoudige animatie). `<img src="..." alt="...">` — het
`alt`-attribuut is **verplicht**. `<figure>`/`<figcaption>` groepeert een afbeelding (of meerdere)
met een bijschrift. `<picture>` laat toe om per schermbreedte/situatie een andere afbeelding te
tonen. Audio/video wordt in de praktijk meestal **ge-embed** via een `<iframe>` (YouTube, Google
Maps...) in plaats van zelf gehost.

### Wat moet sowieso in de oefeningen komen
- Elke `<img>` heeft een verplicht en **relevant** `alt`-attribuut
- Bewust nadenken over content vs. design (uitleg/motivatie in commentaar mag gevraagd worden)
- Minstens één `<figure>`/`<figcaption>`-combinatie

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Foto met bijschrift | Favoriete foto/herinnering | Makkelijk | Eén `<figure>` met `<img alt="...">` en een `<figcaption>`. |
| 2 | Meerdere afbeeldingen | Bv. informatie over paarden / eigen onderwerp | Gemiddeld | Eén `<figure>` met meerdere `<img>`'s en één gemeenschappelijke `<figcaption>`, elk met een eigen, zinvolle `alt`-tekst. |
| 3 | Video & kaart embedden | Favoriete plek of evenement | Gemiddeld | Pagina met een ingesloten YouTube-video en een ingesloten Google Maps-locatie via `<iframe>`, gecombineerd met begeleidende tekst. |
| 4 | Responsieve afbeelding | Bv. een productpagina of hero-afbeelding | Moeilijk | `<picture>`-element met meerdere `<source media="...">`-varianten en een standaard `<img>` als fallback; student moet ook het juiste bestandsformaat beargumenteren (jpg vs. png vs. svg vs. webp). |

[⬆ terug naar boven](#inhoudstafel)

---

## 06. Formulieren

**Link:** https://rogiervdl.github.io/HTML-course/06_formulieren.html

### Beknopte uitleg
Formulieren bestaan uit `<form>`, eventueel `<fieldset>`/`<legend>` om te groeperen, en
combinaties van `<label>` + control (`<input>`, `<select>`, `<textarea>`). Elke control heeft
een `id`, en elk `<label for="...">` verwijst naar die `id` (of nest de control rechtstreeks in
het label — enkel gedaan bij radiobuttons/checkboxes). Het juiste `type` van `<input>`
(text/email/tel/url/password/number/date/color/range/file/checkbox/radio...) is belangrijk voor
toegankelijkheid, validatie (`required`) en mobiele toetsenborden. Elk formulier eindigt met een
`<button type="submit">`. Let op het verschil tussen een **button** (actie op het formulier) en
een **link** (navigatie).

### Wat moet sowieso in de oefeningen komen
- Elke control heeft een correct gelinkt `<label>` (via `for`/`id`, behalve bij
  radio/checkbox waar nesten ook mag)
- Correcte `type`-keuze per soort gegeven (email, tel, date, number...)
- Minstens één `required`-attribuut
- Een `<button type="submit">` (en eventueel `type="reset"`)
- Structuur met één `<div>` (of `<p>`) per label/control-paar

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Login formulier | Inlogscherm | Makkelijk | Eenvoudig formulier met gebruikersnaam (text) en wachtwoord (password), beide `required`, en een submit-knop. |
| 2 | Contactformulier | Contactpagina van een fictief bedrijf/persoon | Gemiddeld | Naam (text), e-mail (email), telefoon (tel) en bericht (`<textarea>`), correct gelabeld, met submit- en reset-knop. |
| 3 | Enquête / inschrijvingsformulier | Bv. inschrijving voor een workshop/evenement | Gemiddeld–moeilijk | Combinatie van tekstvelden, `<select>` (dropdown), radiobuttons (bv. geslacht/optie), checkboxes (bv. interesses), een `range`-slider (bv. tevredenheid) en `<fieldset>`/`<legend>` om te groeperen in "verplicht" en "optioneel". |
| 4 | Webshop bestelformulier | Fictieve online bestelling | Moeilijk | Uitgebreid formulier met `file`-upload (met `accept`), `number` met `min`/`max`/`step`, `date`, `color`, meerdere `<fieldset>`-groepen, en doordachte combinatie van `required`/`placeholder` op alle velden. |

[⬆ terug naar boven](#inhoudstafel)

---

## 07. Structureren

**Link:** https://rogiervdl.github.io/HTML-course/07_structureren.html

### Beknopte uitleg
Structurele elementen geven **betekenis aan gebieden** van de pagina (in tegenstelling tot het
betekenisloze `<div>`/`<span>`): `<header>` (inleidend gedeelte), `<footer>` (afsluitend
gedeelte), `<main>` (hoofdinhoud, max één per pagina), `<nav>` (hoofdnavigatie), `<section>`
(blok met/zonder titel — in deze cursus de losse interpretatie), `<aside>` (gerelateerde
zij-inhoud), `<article>` (onafhankelijke, herbruikbare inhoud, bv. widgets, comments). Vuistregel:
**content die bij elkaar hoort, moet samen in één element zitten** (bv. socials in een `<ul>`,
een reactie in een `<article>`).

### Wat moet sowieso in de oefeningen komen
- Eén `<header>`, één `<main>`, één `<footer>`, één `<nav>` per pagina
- Correct onderscheid tussen `<section>`/`<article>`/`<aside>`/`<div>` (met motivatie in
  commentaar waar twijfel mogelijk is)
- Logisch groeperen van bij elkaar horende content (vuistregel toepassen)

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Basis pagina-skelet | Vrij te kiezen (bv. persoonlijke blog) | Makkelijk | Enkel de hoofdstructuur opzetten: `<header>` (titel + logo), `<nav>` (hoofdmenu), `<main>` (lege/placeholder-inhoud), `<footer>` (copyright + links). |
| 2 | Blogartikel met zijbalk | Blogpost over een zelfgekozen onderwerp | Gemiddeld | `<main>` met een `<article>` (het blogartikel zelf) en een `<aside>` met gerelateerde info (bv. "over de auteur", "recente posts"). |
| 3 | Van div-soep naar semantische HTML | Herstructureren van een gegeven "kale" of div-only pagina | Gemiddeld–moeilijk | De student krijgt een pagina die volledig met `<div>`'s is opgebouwd (naar analogie met het voorbeeld uit de les) en moet deze herschrijven met correcte semantische elementen. |
| 4 | Volledige nieuwssite lay-out | Homepage van een fictieve nieuwssite | Moeilijk | Combineert `<nav>`, meerdere `<section>`/`<article>`-blokken (verschillende nieuwsberichten), een `<aside>` ("populaire artikelen"), en een `<footer>` met sociale links (gegroepeerd in een `<ul>`), volgens de vuistregel "wat bij elkaar hoort, zit samen". |

[⬆ terug naar boven](#inhoudstafel)

---

## 08. Samenvatting

**Link:** https://rogiervdl.github.io/HTML-course/08_samenvatting.html

### Beknopte uitleg
Dit hoofdstuk introduceert **geen nieuwe leerstof**, maar geeft een volledig overzicht van alle
elementen uit lessen 1–7 (tekst, links, media, tabellen, formulieren, structuur). De oefeningen
bij dit hoofdstuk zijn daarom **geen nieuwe theorie-oefeningen**, maar **integratie- en
herhalingsoefeningen**: alles wat eerder apart geoefend werd, moet nu in combinatie en in een
overtuigend, samenhangend geheel worden toegepast — ideaal als afsluitend (mini-)project of
foutenopsporingsoefening.

### Wat moet sowieso in de oefeningen komen
- Minstens één oefening met opzettelijke fouten om op te sporen/verbeteren (test kennis van
  álle huisregels)
- Minstens één grotere, samenhangende opdracht die tekst + links + media + structuur combineert
- Idealiter minstens één keer een tabel én een formulier verwerkt in een groter geheel
- Gebruik van de W3C HTML validator (https://validator.w3.org/#validate_by_input) als
  controlestap

### Oefeningen

| # | Titel | Thema | Moeilijkheidsgraad | Beschrijving |
|---|-------|-------|---------------------|--------------|
| 1 | Debug-oefening | Gegeven pagina met opzettelijke fouten | Gemiddeld | Pagina met een reeks bewust ingebouwde fouten (hoofdletters/quotes, ontbrekende `alt`, verkeerd geneste elementen, foutief gebruik van `<b>`/`<i>`, tabel gebruikt voor layout...) die de student moet opsporen en corrigeren, en nadien laten valideren via de W3C validator. |
| 2 | Persoonlijk CV | Curriculum vitae | Gemiddeld–moeilijk | Volledige cv-pagina met semantische structuur (header/main/footer), titelhiërarchie, lijsten (vaardigheden/ervaring), een tabel (bv. taalvaardigheid of opleidingsoverzicht) en een contactformulier onderaan. |
| 3 | Mini-website "mijn favoriete hobby/interesse" | Vrij te kiezen onderwerp | Moeilijk | Eén (of meerdere gelinkte) pagina('s) die tekst, interne/externe links, afbeeldingen met figure/figcaption, een tabel én een formulier combineren binnen een volledig semantisch gestructureerde lay-out. |
| 4 | Eindproject: volledige website | Fictief bedrijf, vereniging of restaurant (meerdere pagina's) | Zeer moeilijk / examenniveau | Volwaardige meerpaginasite (bv. home, over ons, aanbod/menu met tabel, contact met formulier) met consistente navigatie (`<nav>` op elke pagina), correcte interne links tussen pagina's, mediagebruik, en volledige naleving van alle huisregels uit lessen 1–7. Afsluiten met W3C-validatiecontrole op elke pagina. |

[⬆ terug naar boven](#inhoudstafel)

---

## Suggestie voor mapstructuur (voor Claude Code)

```
html-cursus-oefeningen/
├── 01-syntax/
│   ├── oefening1-mijn-eerste-pagina.html
│   ├── oefening2-code-opschonen.html
│   ├── oefening3-metadata-links.html
│   └── oefening4-menukaart.html
├── 02-tekst/
│   └── ...
├── 03-links/
│   └── ...
├── 04-tabellen/
│   └── ...
├── 05-media/
│   └── ...
├── 06-formulieren/
│   └── ...
├── 07-structureren/
│   └── ...
├── 08-samenvatting/
│   └── ...
└── index.html   (overzichtspagina met links naar alle oefeningen)
```

Elk oefeningbestand kan starten met een HTML-commentaarblok met de opdracht, het thema en de
moeilijkheidsgraad, gevolgd door een lege/gedeeltelijke basisstructuur waarin de student verder
werkt (of volledig leeg, naargelang het gewenste niveau van ondersteuning).

---

## Definitieve mapstructuur (gegenereerd)

> Elke oefening krijgt zijn **eigen submap** met deze bestanden:
> - `index.html` — het **startbestand** (bijna leeg; de student vult zelf aan)
> - `oplossing.html` — de **afgewerkte versie** (referentie voor docent én student)
> - `styles.css` — styling zodat de pagina er netjes uitziet
> - `info.md` — de instructies voor de student
> - `img/` — map met de afbeeldingen van deze oefening (enkel waar nodig)
> - `voorbeeld.png` — *(optioneel)* full-page screenshot van het afgewerkte resultaat
>   (aangeleverd door de docent, enkel waar een volledig voorbeeld nuttig is)

```
html-cursus-oefeningen/
├── index.html                  (overzichtspagina met links naar alle oefeningen)
├── README.md                   (uitleg over de mappen en het gebruik)
├── 01-syntax/
│   ├── oefening1-mijn-eerste-pagina/
│   │   ├── index.html          (startbestand — student vult aan)
│   │   ├── oplossing.html      (afgewerkte versie)
│   │   ├── styles.css
│   │   ├── info.md
│   │   ├── img/                (afbeeldingen van deze oefening, enkel waar nodig)
│   │   └── voorbeeld.png      (optioneel screenshot)
│   ├── oefening2-code-opschonen/        (idem)
│   ├── oefening3-metadata-en-links/     (idem)
│   └── oefening4-menukaart/             (idem)
├── 02-tekst/
│   └── oefening1 ... oefening4 (elk met index.html, oplossing.html, styles.css, info.md, img/)
├── 03-links/       (idem)
├── 04-tabellen/    (idem)
├── 05-media/       (idem)
├── 06-formulieren/ (idem)
├── 07-structureren/(idem)
└── 08-samenvatting/(idem)
```

---

## Werkwijze voor de oefenbestanden

### Startbestand (`index.html`)
- Bevat **bovenaan de opdracht in een HTML-commentaarblok** (oefening, thema, moeilijkheidsgraad,
  opdracht en eventuele tips).
- Daaronder staat enkel een **correcte basisstructuur**: `<!DOCTYPE html>`, `<html lang="nl">`,
  `<head>` met `meta charset`, `meta viewport`, `<title>` en de `<link rel="stylesheet"
  href="styles.css">`, plus een grotendeels **leeg `<body>`**.
- De student bouwt de inhoud **vrijwel volledig zelf** — géén invul-oefeningen en géén
  voorgedrukt stappenplan. Waar houvast gewenst is, staan alleen stuur-commentaren, bijvoorbeeld:
  ```html
  <!-- Vul hier je HTML verder aan -->
  <!-- Plaats hier je navigatielijst (ul) -->
  ```
- **Uitzondering:** de fout-herstellende oefeningen (**01.2 Code opschonen**, **07.3 Van div-soep
  naar semantische HTML**, **08.1 Debug-oefening**) bevatten in `index.html` wél de te verbeteren
  ("foute") HTML, omdat de student die moet opsporen en corrigeren.

### Oplossing (`oplossing.html`)
- Elke oefening heeft een **afgewerkte, volledige versie** (`oplossing.html`) die aan álle
  vereisten uit `info.md` voldoet en dezelfde `styles.css` gebruikt.
- Dient als referentie voor de docent en als nakijkvoorbeeld voor de student.

### Voorbeeld-screenshot (`voorbeeld.png`)
- Waar een **volledig voorbeeld** van de afgewerkte pagina nuttig is, levert de docent een
  **full-page screenshot** van het eindresultaat aan. Dat bestand komt als `voorbeeld.png` in de
  map van de oefening te staan en wordt in `info.md` vermeld.
- Zie de tabel hieronder voor de oefeningen waar zo'n screenshot **aanbevolen** is.

### Waar is een voorbeeld-screenshot aanbevolen?
| Oefening | Voorbeeld-screenshot |
|----------|-----------------------|
| 01.1 Mijn eerste pagina | aanbevolen |
| 02.2 Persoonlijk profiel | aanbevolen |
| 03.1 Interne navigatie | aanbevolen |
| 04.2 Lesrooster | aanbevolen |
| 04.3 Prijzentabel hotel/reisorganisatie | aanbevolen |
| 06.2 Contactformulier | aanbevolen |
| 06.3 Enquête / inschrijvingsformulier | aanbevolen |
| 07.1 Basis pagina-skelet | aanbevolen |
| 07.2 Blogartikel met zijbalk | aanbevolen |
| 07.4 Volledige nieuwssite lay-out | aanbevolen |
| 08.2 Persoonlijk CV | aanbevolen |
| 08.3 Mini-website hobby | aanbevolen |
| 08.4 Eindproject website | aanbevolen |

> Bij de overige oefeningen is een screenshot optioneel (tabellen en formulieren zijn in de
> browser grotendeels invuloefeningen en hebben minder een volledig voorbeeld nodig).

---

## CSS-opdracht (styling)

> **Doel:** elke oefening moet in de browser als een **netjes ogende pagina** worden weergegeven,
> zonder dat de student zelf CSS hoeft te schrijven. De styling is dus een *service* die de
> HTML-oefening ondersteunt: de student focust op HTML, de CSS maakt het resultaat mooi en leesbaar.
> Dezelfde `styles.css` wordt gebruikt door zowel het startbestand (`index.html`) als de
> oplossing (`oplossing.html`).

### Vaste huisstijl (geldt voor elke `styles.css`)
- Moderne systeemfont-stack: `Segoe UI, system-ui, -apple-system, sans-serif`
- Rustige achtergrondkleur + witte "kaart" (max-width ±720px, gecentreerd) voor de inhoud
- Consistente accentkleur per les: 01 blauw-grijs, 02 groen, 03 indigo, 04 oranje, 05 roze,
  06 teal, 07 paars, 08 blauw
- Nette typografie: grotere, duidelijkere koppen; regelafstand ±1.6; zachte tekstkleuren
- Goede leesbaarheid en voldoende contrast (WCAG), zowel in light als dark mode
- Kleine CSS-reset: `box-sizing: border-box`, `margin`/`padding` waar nodig op 0

### Extra styling per les (waar van toepassing)
| Les | Extra CSS die nodig is |
|-----|------------------------|
| 01 Syntax | Algemene body/typografie; stijl voor `header`, `nav`, `footer`, menu-lijsten |
| 02 Tekst | Stijl voor `h1`–`h6`, `blockquote`, `address`, `ul`/`ol`/`dl`, `details`/`summary`, `abbr`, `mark` |
| 03 Links | Linkkleuren en `:hover`, stijl voor menu en secties, `scroll-behavior: smooth` voor ankers |
| 04 Tabellen | Tabelstijl: randen, zebra-striping (`tbody tr:nth-child(even)`), `caption`-opmaak, `thead`-achtergrond |
| 05 Media | Stijl voor `figure`/`figcaption`, `img`/`iframe` maximaal 100% breed (responsive), nette embeds |
| 06 Formulieren | Stijl voor `fieldset`/`legend`, label+control-layout, focus-ring, nette knoppen |
| 07 Structureren | Stijl voor `header`/`main`/`footer`/`nav`, `article`, `aside`, `section` (ruimte, scheidingslijnen) |
| 08 Samenvatting | Combinatie van alles hierboven; nadruk op een samenhangende, verzorgde lay-out |

### Belangrijke regels voor de CSS
- CSS is **puur presentatie** en mag de HTML-huisregels nooit "omzeilen" (geen `display:block`
  op een `span` als stiekeme fix, geen layout-tabellen die in CSS worden rechtgetrokken).
- Gebruik semantische selectors (tag- en class-selectors), geen overbodige wrapper-`<div>`'s.
- Houd de CSS per oefening **kort en overzichtelijk**; de student hoeft ze niet te begrijpen,
  maar mag er wel in kijken.

---

## Benodigde afbeeldingen per oefening

> Onderstaande oefeningen hebben een of meer afbeeldingen nodig. De student mag eigen foto's
> meebrengen, of er worden afbeeldingen in de `img/`-map van die oefening voorzien. In de
> `info.md` van elke oefening staat telkens precies welke afbeelding(en) nodig zijn. De
> verwijzing in de HTML gebeurt met een relatief pad (`img/...`).

| Oefening | Afbeelding(en) nodig |
|----------|----------------------|
| 01.1 Mijn eerste pagina | 1 afbeelding (bv. foto van jezelf) |
| 03.4 Portfolio / linkoverzicht | minstens 1 gelinkte afbeelding |
| 05.1 Foto met bijschrift | 1 afbeelding (favoriete foto) |
| 05.2 Meerdere afbeeldingen | meerdere afbeeldingen (2 paardenfoto's) |
| 05.4 Responsieve afbeelding | minstens 2–3 varianten (verschillende breedtes/formaten) |
| 07.1 Basis pagina-skelet | optioneel: 1 logo |
| 07.2 Blogartikel met zijbalk | optioneel: 1 afbeelding bij het artikel |
| 07.4 Volledige nieuwssite | optioneel: nieuwsafbeeldingen |
| 08.2 Persoonlijk CV | optioneel: pasfoto |
| 08.3 Mini-website hobby | minstens 1 afbeelding (met figure/figcaption) |
| 08.4 Eindproject website | optioneel: logo + overige media |

Oefeningen met video/kaart (05.3) en icon fonts (02.4) hebben **geen lokale afbeeldingen**
nodig; die gebruiken respectievelijk `<iframe>`-embeds en een iconfont-CDN.

---

## Afbeeldingsbronnen per oefening (open source)

> Alle afbeeldingen hieronder komen van **Wikimedia Commons** en mogen vrij gebruikt worden;
> controleer op de bronpagina de exacte licentie en naamsvermelding. De "direct"-URL kan
> rechtstreeks in `<img src="...">` geplaatst worden, of download het bestand naar de `img/`-map
> van de oefening. Waar de oefening om een **eigen** foto vraagt, zijn dit enkel voorbeelden.

### 01. Syntax
- **01.1 Mijn eerste pagina** (eigen foto mag, of een voorbeeldportret):
  - Portret John F. Kennedy — [bron](https://commons.wikimedia.org/wiki/File:John_F_Kennedy_Official_Portrait.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/21/John_F_Kennedy_Official_Portrait.jpg/1280px-John_F_Kennedy_Official_Portrait.jpg`
  - Dama z gronostajem (Leonardo) — [bron](https://commons.wikimedia.org/wiki/File:Dama_z_gronostajem.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/ed/Dama_z_gronostajem.jpg/1280px-Dama_z_gronostajem.jpg`
- **01.2 Code opschonen**:
  - Code op een computerscherm — [bron](https://commons.wikimedia.org/wiki/File:Code_on_computer_monitor_(Unsplash).jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/7/7f/Code_on_computer_monitor_%28Unsplash%29.jpg/1280px-Code_on_computer_monitor_%28Unsplash%29.jpg`
- **01.3 Metadata & links** (pagina over een hobby):
  - Wandelen op het strand — [bron](https://commons.wikimedia.org/wiki/File:Hobbies._Ejercicio._Pasear_por_la_playa.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/9/9f/Hobbies._Ejercicio._Pasear_por_la_playa.jpg/1280px-Hobbies._Ejercicio._Pasear_por_la_playa.jpg`
  - Wikipedian at otium — [bron](https://commons.wikimedia.org/wiki/File:Wikipedian_at_otium.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/3/37/Wikipedian_at_otium.jpg/1280px-Wikipedian_at_otium.jpg`
- **01.4 Menukaart**:
  - Menukaart Aziatisch restaurant — [bron](https://commons.wikimedia.org/wiki/File:Menu_du_jour_d%27un_restaurant_asiatique_lyonnais_en_2017.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/e0/Menu_du_jour_d%27un_restaurant_asiatique_lyonnais_en_2017.jpg/1280px-Menu_du_jour_d%27un_restaurant_asiatique_lyonnais_en_2017.jpg`
  - Feestmenu Kaiser Wilhelm 1898 — [bron](https://commons.wikimedia.org/wiki/File:Festessen_Kaiser_Wilhelm_1898_(front_page).jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/0/02/Festessen_Kaiser_Wilhelm_1898_%28front_page%29.jpg/1280px-Festessen_Kaiser_Wilhelm_1898_%28front_page%29.jpg`

### 02. Tekst
- **02.1 Receptpagina**:
  - Kokend eten met glimlach — [bron](https://commons.wikimedia.org/wiki/File:Cooking_food_with_smile.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/6/6d/Cooking_food_with_smile.jpg/1280px-Cooking_food_with_smile.jpg`
  - Koken op de boerderij — [bron](https://commons.wikimedia.org/wiki/File:Cooking_food_in_farm.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/f/f4/Cooking_food_in_farm.jpg`
- **02.2 Persoonlijk profiel**:
  - Zelfportret Helene Schjerfbeck — [bron](https://commons.wikimedia.org/wiki/File:Helene_Schjerfbeck,_Self-Portrait,_Black_Background,_1915.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/df/Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg/1280px-Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg`
  - Portret van een Sloveense boerin — [bron](https://commons.wikimedia.org/wiki/File:Portrait_of_a_Slovene_Peasant_Woman.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/25/Portrait_of_a_Slovene_Peasant_Woman.jpg/1280px-Portrait_of_a_Slovene_Peasant_Woman.jpg`
- **02.3 FAQ-accordeon**:
  - Vraagteken-icoon — [bron](https://commons.wikimedia.org/wiki/File:Question_Mark_Icon.png) · direct: `https://upload.wikimedia.org/wikipedia/commons/8/84/Question_Mark_Icon.png`
  - Vraagteken op een boekrol — [bron](https://commons.wikimedia.org/wiki/File:Question_mark_on_a_scroll.svg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/4/47/Question_mark_on_a_scroll.svg/1280px-Question_mark_on_a_scroll.svg.png`
- **02.4 Wetenschappelijk artikel**:
  - Scheikundelabo (Augustine University) — [bron](https://commons.wikimedia.org/wiki/File:Chemistry_Laboratory,_Augustine_University,_Ilara_Epe.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/da/Chemistry_Laboratory%2C_Augustine_University%2C_Ilara_Epe.jpg/1280px-Chemistry_Laboratory%2C_Augustine_University%2C_Ilara_Epe.jpg`
  - Chemistry Research Laboratory — [bron](https://commons.wikimedia.org/wiki/File:Chemistry_Research_Laboratory_-_geograph.org.uk_-_7958397.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/e/e5/Chemistry_Research_Laboratory_-_geograph.org.uk_-_7958397.jpg`

### 03. Links
- **03.1 Interne navigatie**:
  - Zelfportret Helene Schjerfbeck — [bron](https://commons.wikimedia.org/wiki/File:Helene_Schjerfbeck,_Self-Portrait,_Black_Background,_1915.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/df/Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg/1280px-Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg`
  - Portret John F. Kennedy — [bron](https://commons.wikimedia.org/wiki/File:John_F_Kennedy_Official_Portrait.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/21/John_F_Kennedy_Official_Portrait.jpg/1280px-John_F_Kennedy_Official_Portrait.jpg`
- **03.2 Contactpagina**:
  - Telefoon in Botanische Tuin São Paulo — [bron](https://commons.wikimedia.org/wiki/File:Telephone_in_the_Botanical_Garden_of_Sao_Paulo.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/26/Telephone_in_the_Botanical_Garden_of_Sao_Paulo.jpg/1280px-Telephone_in_the_Botanical_Garden_of_Sao_Paulo.jpg`
  - Northern Electric N415H — [bron](https://commons.wikimedia.org/wiki/File:Northern_Electric_N415H_02.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/58/Northern_Electric_N415H_02.jpg/1280px-Northern_Electric_N415H_02.jpg`
- **03.3 FAQ met inhoudsopgave**:
  - Vraagteken-icoon — [bron](https://commons.wikimedia.org/wiki/File:Question_Mark_Icon.png) · direct: `https://upload.wikimedia.org/wikipedia/commons/8/84/Question_Mark_Icon.png`
  - Vraag in een vraag (gif) — [bron](https://commons.wikimedia.org/wiki/File:Question_in_a_question_in_a_question_in_a_question.gif) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/1/11/Question_in_a_question_in_a_question_in_a_question.gif/1280px-Question_in_a_question_in_a_question_in_a_question.gif`
- **03.4 Portfolio / linkoverzicht**:
  - Mona Lisa (Leonardo) — [bron](https://commons.wikimedia.org/wiki/File:Mona_Lisa,_by_Leonardo_da_Vinci,_from_C2RMF_retouched.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/ec/Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg/1280px-Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg`
  - The triumph of french painting (Louvre) — [bron](https://commons.wikimedia.org/wiki/File:The_triumph_of_french_painting_The_apotheosis_of_Poussin,_Le_Sueur_and_Le_Brune_-_Louvre.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/21/The_triumph_of_french_painting_The_apotheosis_of_Poussin%2C_Le_Sueur_and_Le_Brune_-_Louvre.jpg/1280px-The_triumph_of_french_painting_The_apotheosis_of_Poussin%2C_Le_Sueur_and_Le_Brune_-_Louvre.jpg`

### 04. Tabellen
- **04.1 Klasoverzicht**:
  - Klaslokaal in Hanoi — [bron](https://commons.wikimedia.org/wiki/File:Hanoi_classroom,_summer_2003.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/f/f9/Hanoi_classroom%2C_summer_2003.jpg`
  - Grande salle ENC — [bron](https://commons.wikimedia.org/wiki/File:Grande_salle_ENC_n1.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/9/9a/Grande_salle_ENC_n1.jpg/1280px-Grande_salle_ENC_n1.jpg`
- **04.2 Lesrooster**:
  - Klaslokaal Hayesville High School — [bron](https://commons.wikimedia.org/wiki/File:A_Hayesville_High_School_classroom_in_Clay_County,_N.C.,_in_2004.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/d4/A_Hayesville_High_School_classroom_in_Clay_County%2C_N.C.%2C_in_2004.jpg/1280px-A_Hayesville_High_School_classroom_in_Clay_County%2C_N.C.%2C_in_2004.jpg`
  - Palamuse klassiruum — [bron](https://commons.wikimedia.org/wiki/File:Palamuse_kihelkonnakooli_klassiruum.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/b/bf/Palamuse_kihelkonnakooli_klassiruum.jpg/1280px-Palamuse_kihelkonnakooli_klassiruum.jpg`
- **04.3 Prijzentabel hotel/reisorganisatie**:
  - Hotel Tadoussac — [bron](https://commons.wikimedia.org/wiki/File:Tadoussac_-_Hotel_(1).jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/5b/Tadoussac_-_Hotel_%281%29.jpg/1280px-Tadoussac_-_Hotel_%281%29.jpg`
  - Restaurantruimte Amantaka Resort & Hotel — [bron](https://commons.wikimedia.org/wiki/File:Restaurant_room_of_Amantaka_luxury_Resort_%26_Hotel_in_Luang_Prabang_Laos.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/f3/Restaurant_room_of_Amantaka_luxury_Resort_%26_Hotel_in_Luang_Prabang_Laos.jpg/1280px-Restaurant_room_of_Amantaka_luxury_Resort_%26_Hotel_in_Luang_Prabang_Laos.jpg`
- **04.4 Volledig resultatenoverzicht**:
  - Olympiastadion bij schemering — [bron](https://commons.wikimedia.org/wiki/File:Olympiastadion_at_dusk.JPG) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/ab/Olympiastadion_at_dusk.JPG/1280px-Olympiastadion_at_dusk.JPG`
  - Nieuw stadion Kaliningrad — [bron](https://commons.wikimedia.org/wiki/File:Kaliningrad_05-2017_img74_new_stadium.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/c/c9/Kaliningrad_05-2017_img74_new_stadium.jpg/1280px-Kaliningrad_05-2017_img74_new_stadium.jpg`

### 05. Media
- **05.1 Foto met bijschrift**:
  - Joshua Tree National Park — [bron](https://commons.wikimedia.org/wiki/File:Joshua_Tree_National_Park_2013.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/55/Joshua_Tree_National_Park_2013.jpg/1280px-Joshua_Tree_National_Park_2013.jpg`
  - Toscaans landschap — [bron](https://commons.wikimedia.org/wiki/File:Tuscan_Landscape_6.JPG) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/fc/Tuscan_Landscape_6.JPG/1280px-Tuscan_Landscape_6.JPG`
- **05.2 Meerdere afbeeldingen** (informatie over paarden):
  - Paard (december 2014) — [bron](https://commons.wikimedia.org/wiki/File:Horse_December_2014-1.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/a2/Horse_December_2014-1.jpg/1280px-Horse_December_2014-1.jpg`
  - Paarden (Biandintz eta zaldiak) — [bron](https://commons.wikimedia.org/wiki/File:Biandintz_eta_zaldiak_-_modified2.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/a2/Biandintz_eta_zaldiak_-_modified2.jpg/1280px-Biandintz_eta_zaldiak_-_modified2.jpg`
- **05.3 Video & kaart embedden** (kaart als begeleidende afbeelding):
  - Wereldkaart 1689 — [bron](https://commons.wikimedia.org/wiki/File:World_Map_1689.JPG) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/3/3b/World_Map_1689.JPG/1280px-World_Map_1689.JPG`
  - Samuel Dunn wereldkaart 1794 — [bron](https://commons.wikimedia.org/wiki/File:1794_Samuel_Dunn_Wall_Map_of_the_World_in_Hemispheres_-_Geographicus_-_World2-dunn-1794.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/ff/1794_Samuel_Dunn_Wall_Map_of_the_World_in_Hemispheres_-_Geographicus_-_World2-dunn-1794.jpg/1280px-1794_Samuel_Dunn_Wall_Map_of_the_World_in_Hemispheres_-_Geographicus_-_World2-dunn-1794.jpg`
- **05.4 Responsieve afbeelding** (hero-afbeelding):
  - Berglandschap Nepal (Chola Valley) — [bron](https://commons.wikimedia.org/wiki/File:Mountains_in_snow,_Mountain_lake,_Chola_Valley,_Nepal,_Himalayas.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/5a/Mountains_in_snow%2C_Mountain_lake%2C_Chola_Valley%2C_Nepal%2C_Himalayas.jpg/1280px-Mountains_in_snow%2C_Mountain_lake%2C_Chola_Valley%2C_Nepal%2C_Himalayas.jpg`
  - Zagedan-meren, Kaukasus — [bron](https://commons.wikimedia.org/wiki/File:Zagedan_Lakes,_Mountain_cirque,_Caucasus_Mountains.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/8/88/Zagedan_Lakes%2C_Mountain_cirque%2C_Caucasus_Mountains.jpg/1280px-Zagedan_Lakes%2C_Mountain_cirque%2C_Caucasus_Mountains.jpg`

### 06. Formulieren
- **06.1 Login formulier**:
  - Verlicht toetsenbord — [bron](https://commons.wikimedia.org/wiki/File:Backlit_keyboard.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/c/c4/Backlit_keyboard.jpg/1280px-Backlit_keyboard.jpg`
  - Microsoft-toetsenbord (zoom burst) — [bron](https://commons.wikimedia.org/wiki/File:Camera_zoom_burst_on_a_Microsoft_computer_keyboard_in_Tuntorp_8.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/0/08/Camera_zoom_burst_on_a_Microsoft_computer_keyboard_in_Tuntorp_8.jpg/1280px-Camera_zoom_burst_on_a_Microsoft_computer_keyboard_in_Tuntorp_8.jpg`
- **06.2 Contactformulier**:
  - Secretaria da Justiça, São Paulo — [bron](https://commons.wikimedia.org/wiki/File:Secretaria_da_Justi%C3%A7a_e_da_Defesa_da_Cidadania,_S%C3%A3o_Paulo,_Brasil.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/b/bf/Secretaria_da_Justi%C3%A7a_e_da_Defesa_da_Cidadania%2C_S%C3%A3o_Paulo%2C_Brasil.jpg/1280px-Secretaria_da_Justi%C3%A7a_e_da_Defesa_da_Cidadania%2C_S%C3%A3o_Paulo%2C_Brasil.jpg`
  - ADAC-Zentrale, München — [bron](https://commons.wikimedia.org/wiki/File:ADAC-Zentrale,_Munich,_March_2017-05.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/7/73/ADAC-Zentrale%2C_Munich%2C_March_2017-05.jpg/1280px-ADAC-Zentrale%2C_Munich%2C_March_2017-05.jpg`
- **06.3 Enquête / inschrijvingsformulier** (workshop):
  - Elektricien in werkplaats São Paulo — [bron](https://commons.wikimedia.org/wiki/File:Electrician_at_the_Eletrotecnica_Bene_workshop,_Sao_Paulo.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/b/bb/Electrician_at_the_Eletrotecnica_Bene_workshop%2C_Sao_Paulo.jpg/1280px-Electrician_at_the_Eletrotecnica_Bene_workshop%2C_Sao_Paulo.jpg`
  - Werkstatt eines Schiffszimmerers — [bron](https://commons.wikimedia.org/wiki/File:Werkstatt_eines_Schiffszimmerers_im_Altonaer_Museum_IMG_5128_edit.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/9/94/Werkstatt_eines_Schiffszimmerers_im_Altonaer_Museum_IMG_5128_edit.jpg/1280px-Werkstatt_eines_Schiffszimmerers_im_Altonaer_Museum_IMG_5128_edit.jpg`
- **06.4 Webshop bestelformulier**:
  - Online shoppen met bankkaart — [bron](https://commons.wikimedia.org/wiki/File:Shopping_online_with_bank_card.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/aa/Shopping_online_with_bank_card.jpg/1280px-Shopping_online_with_bank_card.jpg`
  - Online shoppen in Rusland — [bron](https://commons.wikimedia.org/wiki/File:Overseas_online_shopping_in_Russia.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/1/1a/Overseas_online_shopping_in_Russia.jpg`

### 07. Structureren
- **07.1 Basis pagina-skelet** (optioneel logo):
  - Logo blog (voorbeeld) — [bron](https://commons.wikimedia.org/wiki/File:Logo_blog_Mas_Andisyam.png) · direct: `https://upload.wikimedia.org/wikipedia/commons/9/94/Logo_blog_Mas_Andisyam.png`
  - Blog-screenshot (2004) — [bron](https://commons.wikimedia.org/wiki/File:BlogActive.com_Screenshot_2004.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/c/cc/BlogActive.com_Screenshot_2004.jpg`
- **07.2 Blogartikel met zijbalk**:
  - Schrijfbureau van Pierre Victor de Besenval — [bron](https://commons.wikimedia.org/wiki/File:Writing_desk_of_Pierre_Victor_de_Besenval.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/6/6c/Writing_desk_of_Pierre_Victor_de_Besenval.jpg/1280px-Writing_desk_of_Pierre_Victor_de_Besenval.jpg`
  - Studiekamer Abbotsford House — [bron](https://commons.wikimedia.org/wiki/File:Abbotsford_House_Study_Room.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/1/13/Abbotsford_House_Study_Room.jpg/1280px-Abbotsford_House_Study_Room.jpg`
- **07.3 Van div-soep naar semantische HTML**:
  - Programmeercode — [bron](https://commons.wikimedia.org/wiki/File:Programming_code.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/ef/Programming_code.jpg/1280px-Programming_code.jpg`
  - Programmeerles — [bron](https://commons.wikimedia.org/wiki/File:Computer_programming_class.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/f4/Computer_programming_class.jpg/1280px-Computer_programming_class.jpg`
- **07.4 Volledige nieuwssite lay-out**:
  - Internationale krant (Rome 2005) — [bron](https://commons.wikimedia.org/wiki/File:International_newspaper,_Rome_May_2005.jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/2/2c/International_newspaper%2C_Rome_May_2005.jpg`
  - Land op de Maan (krantenkop 1969) — [bron](https://commons.wikimedia.org/wiki/File:Land_on_the_Moon_7_21_1969-repair.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/9/9a/Land_on_the_Moon_7_21_1969-repair.jpg/1280px-Land_on_the_Moon_7_21_1969-repair.jpg`

### 08. Samenvatting
- **08.1 Debug-oefening** (lieveheersbeestje = "bug"):
  - Lieveheersbeestjes (Coccinella septempunctata) — [bron](https://commons.wikimedia.org/wiki/File:Coccinella_septempunctata_couple_(aka).jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/b/bc/Coccinella_septempunctata_couple_%28aka%29.jpg/1280px-Coccinella_septempunctata_couple_%28aka%29.jpg`
  - Lieveheersbeestje eet bladluizen — [bron](https://commons.wikimedia.org/wiki/File:Ladybug_eating_aphids._(49485764276).jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/c/c1/Ladybug_eating_aphids._%2849485764276%29.jpg/1280px-Ladybug_eating_aphids._%2849485764276%29.jpg`
- **08.2 Persoonlijk CV** (optioneel pasfoto):
  - Julie Brown (business person) — [bron](https://commons.wikimedia.org/wiki/File:Julie_Brown_(business_person).jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/f/f4/Julie_Brown_%28business_person%29.jpg`
  - Shoko Takahashi (businesswoman) — [bron](https://commons.wikimedia.org/wiki/File:Shoko_Takahashi_(businesswoman).jpg) · direct: `https://upload.wikimedia.org/wikipedia/commons/1/1e/Shoko_Takahashi_%28businesswoman%29.jpg`
- **08.3 Mini-website hobby** (bv. gitaar):
  - Gitaar (mei 2009) — [bron](https://commons.wikimedia.org/wiki/File:Guitar_May_2009-1.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/c/c3/Guitar_May_2009-1.jpg/1280px-Guitar_May_2009-1.jpg`
  - Man speelt Braziliaanse gitaar — [bron](https://commons.wikimedia.org/wiki/File:Man_playing_an_acoustic_brazilian_guitar_(Viol%C3%A3o)_on_Marco_Zero_Square,_Refice,_Pernambuco,_Brazil.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/e0/Man_playing_an_acoustic_brazilian_guitar_%28Viol%C3%A3o%29_on_Marco_Zero_Square%2C_Refice%2C_Pernambuco%2C_Brazil.jpg/1280px-Man_playing_an_acoustic_brazilian_guitar_%28Viol%C3%A3o%29_on_Marco_Zero_Square%2C_Refice%2C_Pernambuco%2C_Brazil.jpg`
- **08.4 Eindproject: volledige website** (bv. restaurant):
  - Restaurant in Place D'Youville, Québec — [bron](https://commons.wikimedia.org/wiki/File:Restaurant_in_Place_D%27Youville,_Quebec_City.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/f9/Restaurant_in_Place_D%27Youville%2C_Quebec_City.jpg/1280px-Restaurant_in_Place_D%27Youville%2C_Quebec_City.jpg`
  - Restaurants aan de Aasee, Münster — [bron](https://commons.wikimedia.org/wiki/File:M%C3%BCnster,_Aasee,_Restaurants_--_2019_--_3464-8.jpg) · direct: `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/23/M%C3%BCnster%2C_Aasee%2C_Restaurants_--_2019_--_3464-8.jpg/1280px-M%C3%BCnster%2C_Aasee%2C_Restaurants_--_2019_--_3464-8.jpg`