# HTML/CSS-oefeningen Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Generate a complete, self-contained VS Code exercise suite — 8 themes × 4 exercises = 32 exercise folders (each with `index.html`, `oplossing.html`, `styles.css`, `info.md`, and `img/` where needed), plus a root overview `index.html` and `README.md`.

**Architecture:** Plain static files, no build step, no JavaScript. Each exercise folder is fully self-contained: the `styles.css` carries the shared huisstijl (with a per-theme accent via CSS custom properties) so the student focuses on HTML only. `index.html` is the start file (mostly empty); `oplossing.html` is the self-check reference (no grader). Content is co-created theme by theme with the user reviewing before each theme is generated.

**Tech Stack:** HTML5, CSS3, Markdown. No dependencies, no tooling. Images downloaded from Wikimedia Commons (open source) into local `img/` folders.

**Spec:** `docs/superpowers/specs/2026-09-26-html-css-oefeningen-design.md` — this plan argues from that spec (which in turn is derived from `alle_oefeningen.md`). Executors read both. All per-exercise titles, themes, difficulty, required elements, and image URLs live in the spec.

## Global Constraints

- **Language:** all generated content (HTML comments, `info.md`, page text, `alt`/`title`) is **Dutch**; technical notation (tags, attributes, filenames) is English.
- **No grader:** these are optional self-study exercises; `oplossing.html` is a self-check reference, not an answer key. Keep everything student-facing and non-evaluative.
- **HTML huisregels (every file):** full base structure (`<!DOCTYPE html>`, `<html lang="nl">`, `<head>` with `<meta charset="utf-8">` + viewport + `<title>`, `<body>`); lowercase tags/attributes; double quotes; consistent indentation (tabs **or** spaces, never mixed); valid nesting (no blocklevel in inline); **no `<b>`/`<i>`**; no layout tables; no `<div>`/`<span>` where a semantic element fits; every `<img>` has a relevant `alt`; max **one `<h1>`** per page; at least one `<!-- -->` comment; character entities where needed.
- **CSS huisregels:** `box-sizing: border-box` reset; font stack `"Segoe UI", system-ui, -apple-system, sans-serif`; centered "card" `max-width: 720px`; `line-height: 1.6`; light+dark mode via `prefers-color-scheme`; semantic selectors only; short and readable; CSS never "fixes" an HTML huisregel violation.
- **Accent per theme:** 01 `#5b6b7a`, 02 `#2f855a`, 03 `#4f46e5`, 04 `#c2410c`, 05 `#db2777`, 06 `#0d9488`, 07 `#7c3aed`, 08 `#2563eb`.
- **Images:** download into `img/` with descriptive kebab-case filenames; reference via relative `img/<file>`; on download failure fall back to a placeholder note in `info.md` + empty `src` in `index.html` (never a broken remote URL).
- **Screenshots:** none generated; the 13 "aanbevolen" exercises get an "Optioneel voorbeeld" note in `info.md`.
- **Not a git repo** (verified): commit steps are optional. Offer `git init` once, at the end.

---

## File Structure

```
(root = C:\Users\BenjiElena\Repositories\HTML-CSS-2026-2027)
├── README.md                          (Task 0)
├── index.html                         (Task 9 — overview, links to all 32)
├── 01-syntax/
│   ├── oefening1-mijn-eerste-pagina/    {index, oplossing, styles, info, img/}
│   ├── oefening2-code-opschonen/        (no img/)
│   ├── oefening3-metadata-en-links/     {…, img/}
│   └── oefening4-menukaart/             {…, img/}
├── 02-tekst/
│   ├── oefening1-receptpagina/          {…, img/}
│   ├── oefening2-persoonlijk-profiel/   {…, img/}
│   ├── oefening3-faq-accordeon/         (no img/)
│   └── oefening4-wetenschappelijk-artikel/ {…, img/}
├── 03-links/
│   ├── oefening1-interne-navigatie/     (no img/)
│   ├── oefening2-contactpagina/         (no img/)
│   ├── oefening3-faq-inhoudsopgave/     (no img/)
│   └── oefening4-portfolio-linkoverzicht/ {…, img/}
├── 04-tabellen/
│   ├── oefening1-klasoverzicht/         (no img/)
│   ├── oefening2-lesrooster/            {…, img/}
│   ├── oefening3-prijzentabel-hotel/    {…, img/}
│   └── oefening4-resultatenoverzicht/   (no img/)
├── 05-media/
│   ├── oefening1-foto-bijschrift/       {…, img/}
│   ├── oefening2-stappenplan-in-beeld/  {…, img/}
│   ├── oefening3-video-kaart-embedden/  (no img — iframes)
│   └── oefening4-responsieve-afbeelding/ {…, img/ (3 variants)}
├── 06-formulieren/  (all 4: no img/)
├── 07-structureren/
│   ├── oefening1-basis-pagina-skelet/   (no img/)
│   ├── oefening2-blogartikel-zijbalk/   {…, img/}
│   ├── oefening3-van-div-soep/          (no img/)
│   └── oefening4-nieuwssite-layout/     {…, img/}
└── 08-samenvatting/
    ├── oefening1-debug/                 (no img/)
    ├── oefening2-persoonlijk-cv/        {…, img/}
    ├── oefening3-mini-website-hobby/    {…, img/}
    └── oefening4-eindproject-website/   {…, img/}
```

Each exercise folder's four files have one clear responsibility:
- `index.html` — start file: comment block (assignment) + base structure + mostly empty `<body>` (or, for error-fixing exercises, the "wrong" HTML to correct).
- `oplossing.html` — complete correct version meeting all `info.md` requirements.
- `styles.css` — the huisstijl (base + theme accent + theme extra CSS).
- `info.md` — student instructions (Opdracht / Vereisten / Tips / Afbeeldingen).

---

## Canonical Templates (used by every theme task)

### T1. `index.html` start file — normal exercise

```html
<!--
  OEFENING 0X.N — <Titel>
  Thema: <thema>  ·  Moeilijkheidsgraad: <moeilijkheid>

  OPDRACHT
  ---------
  <1–3 zinnen in het Nederlands>

  TIPS
  ----
  - <optionele tip; weglaten indien geen tip>
-->
<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title><Titel></title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Vul hier je HTML verder aan -->

</body>
</html>
```

Steering comments (`<!-- Plaats hier je navigatielijst (ul) -->`) are added only where a nudge
helps; never a fill-in exercise, never a pre-printed step plan.

### T2. `index.html` start file — error-fixing exercise (01.2, 07.3, 08.1)

Same comment block, but the `<body>` contains the **deliberately wrong** HTML to correct (the
student finds and fixes it). The `oplossing.html` is the corrected version. Keep the deliberate
mistakes in an internal list (in the theme task below), NOT in the student-facing `info.md`.

### T3. `info.md`

```markdown
# Oefening <0X>.<N> — <Titel>

- **Thema:** <thema>
- **Moeilijkheidsgraad:** <moeilijkheid>
- **Bestanden:** `index.html` (start), `oplossing.html` (voorbeeld), `styles.css` (styling)

## Opdracht

<1–3 zinnen: wat de student moet bouwen>

## Vereisten

- [ ] <concrete vereiste 1>
- [ ] <vereiste 2>
- [ ] …

## Tips

- <optionele tip; weglaten indien geen>

## Afbeeldingen

- <welke afbeelding(en) in `img/`, of "eigen foto mag", of "geen lokale afbeeldingen nodig">
```

For the 13 "aanbevolen" exercises, append:

```markdown
## Referentie

> 📷 **Optioneel voorbeeld:** hier kan een full-page screenshot (`referentie.png`) van het
> afgewerkte resultaat worden toegevoegd.
```

The 13 exercises (from spec): 01.1, 02.2, 03.1, 04.2, 04.3, 06.2, 06.3, 07.1, 07.2, 07.4, 08.2, 08.3, 08.4.

### T4. `styles.css` — base (identical for all themes, except the two `--accent` values)

```css
/* Huisstijl HTML-cursus — thema 0X <naam> */
:root {
  --accent: <THEME HEX>;
  --accent-soft: <THEME SOFT HEX>;
  --page: #eef0f3;
  --card: #ffffff;
  --text: #2a2d34;
  --muted: #66707e;
  --border: #e2e6ea;
}

@media (prefers-color-scheme: dark) {
  :root {
    --page: #12141a;
    --card: #1c1f26;
    --text: #e8eaee;
    --muted: #9aa4b0;
    --border: #2e333d;
  }
}

* { box-sizing: border-box; margin: 0; padding: 0; }

html { background: var(--page); }

body {
  max-width: 720px;
  margin: 0 auto;
  min-height: 100vh;
  padding: 2.5rem 2rem;
  background: var(--card);
  box-shadow: 0 0 32px rgba(0, 0, 0, 0.06);
  font-family: "Segoe UI", system-ui, -apple-system, sans-serif;
  color: var(--text);
  line-height: 1.6;
}

h1, h2, h3, h4, h5, h6 { color: var(--accent); line-height: 1.25; margin: 1.5em 0 0.5em; }
h1 { font-size: 2rem; margin-top: 0; }
h2 { font-size: 1.5rem; }
h3 { font-size: 1.2rem; }
p { margin: 0.75em 0; }
img, iframe, video, picture { max-width: 100%; }

/* ==== THEME EXTRA CSS (below) ==== */
```

---

## Theme Extra CSS (append to the base, per theme)

**Les 01 — Syntax** (header/nav/footer/menu-lijsten):
```css
nav ul { list-style: none; display: flex; gap: 1rem; padding: 0.5rem 0; border-bottom: 1px solid var(--border); }
nav a { text-decoration: none; font-weight: 600; }
header, footer { padding: 1rem 0; }
footer { margin-top: 2rem; border-top: 1px solid var(--border); color: var(--muted); font-size: 0.9rem; }
```

**Les 02 — Tekst** (h1–h6, blockquote, address, ul/ol/dl, details/summary, abbr, mark):
```css
blockquote { border-left: 4px solid var(--accent); padding: 0.5rem 1rem; margin: 1rem 0; background: var(--accent-soft); font-style: italic; }
address { font-style: normal; color: var(--muted); margin: 0.5rem 0; }
ul, ol, dl { margin: 0.75rem 0; padding-left: 1.5rem; }
dt { font-weight: 600; }
details { margin: 0.5rem 0; padding: 0.5rem 0.75rem; border: 1px solid var(--border); border-radius: 6px; }
summary { cursor: pointer; font-weight: 600; color: var(--accent); }
mark { background: var(--accent-soft); color: inherit; padding: 0 0.2em; }
abbr { text-decoration: underline dotted; cursor: help; }
```

**Les 03 — Links** (linkkleuren + `:hover`, menu/secties, smooth scroll):
```css
html { scroll-behavior: smooth; }
a { color: var(--accent); text-decoration: none; border-bottom: 1px solid transparent; }
a:hover { border-bottom-color: var(--accent); }
nav ul { list-style: none; display: flex; gap: 1.25rem; padding: 0.5rem 0; }
section { margin: 1.5rem 0; padding-top: 1rem; border-top: 1px solid var(--border); }
```

**Les 04 — Tabellen** (randen, zebra, caption, thead):
```css
table { width: 100%; border-collapse: collapse; margin: 1rem 0; }
caption { caption-side: top; font-weight: 600; color: var(--accent); margin-bottom: 0.5rem; }
th, td { border: 1px solid var(--border); padding: 0.5rem 0.75rem; text-align: left; }
thead th { background: var(--accent); color: #fff; }
tbody tr:nth-child(even) { background: var(--accent-soft); }
tfoot td { font-weight: 600; background: var(--accent-soft); }
```

**Les 05 — Media** (figure/figcaption, img/iframe responsive):
```css
figure { margin: 1.5rem 0; }
figcaption { font-size: 0.9rem; color: var(--muted); margin-top: 0.5rem; font-style: italic; }
img, iframe, video { max-width: 100%; height: auto; border-radius: 6px; }
iframe { aspect-ratio: 16 / 9; width: 100%; border: 0; }
```

**Les 06 — Formulieren** (fieldset/legend, label+control, focus-ring, knoppen):
```css
fieldset { border: 1px solid var(--border); border-radius: 8px; padding: 1rem 1.25rem; margin: 1rem 0; }
legend { padding: 0 0.5rem; font-weight: 600; color: var(--accent); }
label { display: block; margin: 0.75rem 0 0.25rem; font-weight: 600; }
input, select, textarea { width: 100%; padding: 0.5rem 0.6rem; border: 1px solid var(--border); border-radius: 6px; font: inherit; background: var(--card); color: var(--text); }
input[type="radio"], input[type="checkbox"], input[type="range"], input[type="color"] { width: auto; }
input:focus, select:focus, textarea:focus { outline: 2px solid var(--accent); outline-offset: 1px; }
button { background: var(--accent); color: #fff; border: none; padding: 0.5rem 1.25rem; border-radius: 6px; font: inherit; font-weight: 600; cursor: pointer; }
button[type="reset"] { background: var(--muted); }
```

**Les 07 — Structureren** (header/main/footer/nav, article, aside, section):
```css
header, footer { padding: 1rem 0; }
header { border-bottom: 2px solid var(--accent); }
footer { border-top: 1px solid var(--border); margin-top: 2rem; color: var(--muted); font-size: 0.9rem; }
nav ul { list-style: none; display: flex; gap: 1.25rem; padding: 0.5rem 0; }
main { margin: 1.5rem 0; }
article { padding: 1rem 0; border-bottom: 1px solid var(--border); }
aside { background: var(--accent-soft); border-radius: 8px; padding: 1rem; margin: 1rem 0; }
section { margin: 1.5rem 0; }
```

**Les 08 — Samenvatting** (combinatie): include the base plus, per exercise, the relevant blocks from
Les 02–07 above (tables, forms, figures, structure) as each exercise's `oplossing.html` needs them.

---

## Image Asset Manifest (downloaded in Task 0)

| # | Destination file | Direct URL (Wikimedia Commons) |
|---|---|---|
| 1 | `01-syntax/oefening1-mijn-eerste-pagina/img/portret.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/2/21/John_F_Kennedy_Official_Portrait.jpg/1280px-John_F_Kennedy_Official_Portrait.jpg` |
| 2 | `01-syntax/oefening3-metadata-en-links/img/hobby-wandelen.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/9/9f/Hobbies._Ejercicio._Pasear_por_la_playa.jpg/1280px-Hobbies._Ejercicio._Pasear_por_la_playa.jpg` |
| 3 | `01-syntax/oefening4-menukaart/img/menukaart.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/e0/Menu_du_jour_d%27un_restaurant_asiatique_lyonnais_en_2017.jpg/1280px-Menu_du_jour_d%27un_restaurant_asiatique_lyonnais_en_2017.jpg` |
| 4 | `02-tekst/oefening1-receptpagina/img/koken.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/6/6d/Cooking_food_with_smile.jpg/1280px-Cooking_food_with_smile.jpg` |
| 5 | `02-tekst/oefening2-persoonlijk-profiel/img/profiel.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/df/Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg/1280px-Helene_Schjerfbeck%2C_Self-Portrait%2C_Black_Background%2C_1915.jpg` |
| 6 | `02-tekst/oefening4-wetenschappelijk-artikel/img/lab.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/da/Chemistry_Laboratory%2C_Augustine_University%2C_Ilara_Epe.jpg/1280px-Chemistry_Laboratory%2C_Augustine_University%2C_Ilara_Epe.jpg` |
| 7 | `03-links/oefening4-portfolio-linkoverzicht/img/mona-lisa.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/e/ec/Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg/1280px-Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg` |
| 8 | `04-tabellen/oefening2-lesrooster/img/klaslokaal.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/d/d4/A_Hayesville_High_School_classroom_in_Clay_County%2C_N.C.%2C_in_2004.jpg/1280px-A_Hayesville_High_School_classroom_in_Clay_County%2C_N.C.%2C_in_2004.jpg` |
| 9 | `04-tabellen/oefening3-prijzentabel-hotel/img/hotel.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/5b/Tadoussac_-_Hotel_%281%29.jpg/1280px-Tadoussac_-_Hotel_%281%29.jpg` |
| 10 | `05-media/oefening1-foto-bijschrift/img/joshua-tree.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/5/55/Joshua_Tree_National_Park_2013.jpg/1280px-Joshua_Tree_National_Park_2013.jpg` |
| 11 | `05-media/oefening2-stappenplan-in-beeld/img/paard-1.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/a2/Horse_December_2014-1.jpg/1280px-Horse_December_2014-1.jpg` |
| 12 | `05-media/oefening2-stappenplan-in-beeld/img/paard-2.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/a/a2/Biandintz_eta_zaldiak_-_modified2.jpg/1280px-Biandintz_eta_zaldiak_-_modified2.jpg` |
| 13 | `05-media/oefening4-responsieve-afbeelding/img/landschap-500.jpg` | Nepal mountains at 500px (thumb width variant) |
| 14 | `05-media/oefening4-responsieve-afbeelding/img/landschap-960.jpg` | Nepal mountains at 960px (thumb width variant) |
| 15 | `05-media/oefening4-responsieve-afbeelding/img/landschap-1280.jpg` | Nepal mountains at 1280px (thumb width variant) |
| 16 | `07-structureren/oefening2-blogartikel-zijbalk/img/bureau.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/6/6c/Writing_desk_of_Pierre_Victor_de_Besenval.jpg/1280px-Writing_desk_of_Pierre_Victor_de_Besenval.jpg` |
| 17 | `08-samenvatting/oefening2-persoonlijk-cv/img/pasfoto.jpg` | `https://upload.wikimedia.org/wikipedia/commons/f/f4/Julie_Brown_%28business_person%29.jpg` |
| 18 | `08-samenvatting/oefening3-mini-website-hobby/img/gitaar.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/c/c3/Guitar_May_2009-1.jpg/1280px-Guitar_May_2009-1.jpg` |
| 19 | `08-samenvatting/oefening4-eindproject-website/img/restaurant.jpg` | `https://thumb.wikimedia.org/wikipedia/commons/thumb/f/f9/Restaurant_in_Place_D%27Youville%2C_Quebec_City.jpg/1280px-Restaurant_in_Place_D%27Youville%2C_Quebec_City.jpg` |

**Nepal mountains base URL** (for rows 13–15, vary the width segment):
`https://thumb.wikimedia.org/wikipedia/commons/thumb/5/5a/Mountains_in_snow%2C_Mountain_lake%2C_Chola_Valley%2C_Nepal%2C_Himalayas.jpg/{W}px-Mountains_in_snow%2C_Mountain_lake%2C_Chola_Valley%2C_Nepal%2C_Himalayas.jpg`
with `{W}` ∈ {500, 960, 1280} (all allowed Wikimedia thumbnail sizes). This yields the three responsive variants for `05.4`.

**Download script** (`Task 0`, bash + curl; runs from repo root):
```bash
set -euo pipefail
UA="Mozilla/5.0 (X11; Linux x86_64) exercise-generator/1.0"
dl() { mkdir -p "$(dirname "$1")"; curl -sL -A "$UA" --retry 3 -o "$1" "$2"; }
# rows 1–12, 16–19 (full URLs) via dl "DEST" "URL"
# rows 13–15 via: dl "05-media/oefening4-responsieve-afbeelding/img/landschap-500.jpg" "…/{500}px-…"  (and 960, 1280)
```

---

## Task 0: Foundations — skeleton, README, image download

**Files:**
- Create: `README.md`
- Create: all 32 exercise directories (+ `img/` where the manifest above lists a file)
- Create: the downloaded image files listed in the Image Asset Manifest

**Interfaces:**
- Produces: the full directory skeleton every later task writes into.

- [ ] **Step 1: Create the directory skeleton** — run:
  ```bash
  cd "C:/Users/BenjiElena/Repositories/HTML-CSS-2026-2027"
  for t in 01-syntax 02-tekst 03-links 04-tabellen 05-media 06-formulieren 07-structureren 08-samenvatting; do
    mkdir -p "$t"
  done
  # per-exercise folders incl. img/ — see File Structure map above; create each with mkdir -p
  ```

- [ ] **Step 2: Download all images** — run the download script from the manifest. Verify with `find . -name '*.jpg' | wc -l` → expect **19**. For any download that fails (network/404), leave `img/` empty and note the fallback (see Global Constraints) — do not retry more than once.

- [ ] **Step 3: Write `README.md`** with the following content:
  ```markdown
  # HTML-cursus — Oefeningen

  Extra **optionele** oefeningen bij de HTML-cursus (Rogier van der Linde). Deze map bevat
  8 thema's met elk 4 oefeningen. Elke oefening staat in een eigen map met:

  - `index.html` — het startbestand (jij vult zelf aan)
  - `oplossing.html` — een afgewerkt voorbeeld om jezelf te controleren
  - `styles.css` — de styling (die hoef je niet te schrijven, alleen de HTML)
  - `info.md` — de opdracht en vereisten
  - `img/` — afbeeldingen (enkel waar nodig)

  ## Gebruik

  1. Open de map van een oefening in VS Code.
  2. Open `info.md` en lees de opdracht.
  3. Bewerk `index.html` (of open het in je browser).
  4. Vergelijk met `oplossing.html` als je klaar bent.

  ## Indeling

  | Map | Thema |
  |-----|-------|
  | `01-syntax` | Syntax & basisstructuur |
  | `02-tekst` | Tekst |
  | `03-links` | Links |
  | `04-tabellen` | Tabellen |
  | `05-media` | Media |
  | `06-formulieren` | Formulieren |
  | `07-structureren` | Structureren |
  | `08-samenvatting` | Samenvatting & integratie |
  ```

- [ ] **Step 4: Verify** — `find . -type d -name 'oefening*' | wc -l` → **32**; `README.md` exists; 19 `.jpg` files present.

- [ ] **Step 5: (Optional) commit** — offer `git init` once; skip unless the user wants it.

---

## Task 1: Theme 01 — Syntax (accent `#5b6b7a`, soft `#eef1f4`)

**Files:** create the 4 files in each of the 4 exercise folders under `01-syntax/`.

**Interfaces:**
- Consumes: skeleton + images from Task 0.
- Produces: complete `01-syntax/*` exercise folders.

**Co-creation step (do FIRST, in chat):** present the concrete content of all 4 exercises
(what each `index.html`/`oplossing.html` contains, the `info.md` Vereisten, the deliberate errors
for 01.2) and get the user's approval before writing files.

- [ ] **Step 1: `oefening1-mijn-eerste-pagina`** (Heel makkelijk) — base page: `<title>`, one `<p>` about yourself, one `<img src="img/portret.jpg" alt="…">`. Applies T1/T3/T4. Info.md Vereisten: volledige basisstructuur, één paragraaf, één afbeelding met `alt`, minstens één commentaar. **Referentie-note** (aanbevolen).
- [ ] **Step 2: `oefening2-code-opschonen`** (Makkelijk) — error-fixing (T2). Deliberate errors to build in: UPPERCASE tags, single quotes, missing quotes, inconsistent indentation, a `<P>` around `<img>` (invalid nesting). Corrected `oplossing.html` follows the huisregels. Internal error list (not in info.md).
- [ ] **Step 3: `oefening3-metadata-en-links`** (Gemiddeld) — `<head>` with `<meta name="description">`, `keywords`, `author`, `<link rel="icon">`, `<link rel="stylesheet">`; body over a hobby with `img/hobby-wandelen.jpg`. Tests head-vs-body understanding.
- [ ] **Step 4: `oefening4-menukaart`** (Gemiddeld–moeilijk) — nested menu structure (categories with content), correct nesting; part of the code temporarily commented out. Image `img/menukaart.jpg`.
- [ ] **Step 5: Verify (huisregel checklist)** — each file: base structure, `lang="nl"`, lowercase, double quotes, valid nesting, one `<h1>` max, ≥1 comment, `alt` on every `<img>`, no `<b>`/`<i>`.
- [ ] **Step 6: User review gate** — show the theme's files (or summary) for approval before Task 2.

---

## Task 2: Theme 02 — Tekst (accent `#2f855a`, soft `#e6f4ec`)

- [ ] **Step 0 (co-creation):** propose concrete content for the 4 exercises; get approval.
- [ ] **Step 1: `oefening1-receptpagina`** (Makkelijk) — `<h1>` titel, intro `<p>`, `<ul>` ingrediënten, `<ol>` stappen. Image `img/koken.jpg`. Vereisten: correcte titelhiërarchie, één `<ul>` én één `<ol>`, `<strong>`/`<em>` betekenisvol, geen `<b>`/`<i>`.
- [ ] **Step 2: `oefening2-persoonlijk-profiel`** (Gemiddeld) — h1 naam, h2 secties ("Over mij", "Hobby's"), `<address>`, `<blockquote>`, `<strong>`/`<em>`. Image `img/profiel.jpg`. **Referentie-note**.
- [ ] **Step 3: `oefening3-faq-accordeon`** (Gemiddeld) — ≥4 `<details name="faq">` + `<summary>`, plus a `<dl>` with a few term/definition pairs. No image.
- [ ] **Step 4: `oefening4-wetenschappelijk-artikel`** (Moeilijk) — `<sub>`/`<sup>` (formules), `<abbr title>`, `<mark>`, character entities (`&amp;`, `&copy;`, `&rarr;`), optional Google Icons for social buttons. Image `img/lab.jpg`.
- [ ] **Step 5: Verify** — as Task 1 Step 5, plus: no `<b>`/`<i>` anywhere, correct title hierarchy, entities coded.
- [ ] **Step 6: User review gate.**

---

## Task 3: Theme 03 — Links (accent `#4f46e5`, soft `#eae8fb`)

- [ ] **Step 0 (co-creation):** propose + approve.
- [ ] **Step 1: `oefening1-interne-navigatie`** (Makkelijk) — `<ul>` menu bovenaan met ankers `href="#id"` naar secties op dezelfde pagina. **Referentie-note**.
- [ ] **Step 2: `oefening2-contactpagina`** (Gemiddeld) — `<address>` met `mailto:`, `tel:`, optioneel `sms:` links, betekenisvolle linkteksten.
- [ ] **Step 3: `oefening3-faq-inhoudsopgave`** (Gemiddeld) — inhoudsopgave met links naar elke vraag (ankers) + "terug naar boven"-anker onderaan elke vraag.
- [ ] **Step 4: `oefening4-portfolio-linkoverzicht`** (Moeilijk) — relatieve + absolute links, een gelinkte afbeelding met `title` én `aria-label`. Image `img/mona-lisa.jpg`. Combineert les 2+3.
- [ ] **Step 5: Verify** — every link has meaningful text (no "klik hier"), ≥1 relative + ≥1 absolute URL, ≥1 `title`, ≥1 anker.
- [ ] **Step 6: User review gate.**

---

## Task 4: Theme 04 — Tabellen (accent `#c2410c`, soft `#fdece2`)

- [ ] **Step 0 (co-creation):** propose + approve.
- [ ] **Step 1: `oefening1-klasoverzicht`** (Makkelijk) — only `<table>`/`<tr>`/`<td>` (no headers yet).
- [ ] **Step 2: `oefening2-lesrooster`** (Gemiddeld) — `<caption>` + `<th scope="col">`/`<th scope="row">`. Image `img/klaslokaal.jpg`. **Referentie-note**.
- [ ] **Step 3: `oefening3-prijzentabel-hotel`** (Gemiddeld–moeilijk) — `colspan`/`rowspan` (title spanning columns; room type same price across seasons). Image `img/hotel.jpg`. **Referentie-note**.
- [ ] **Step 4: `oefening4-resultatenoverzicht`** (Moeilijk) — `<thead>`/`<tbody>`/`<tfoot>` (average/total in footer) + `<colgroup>`/`<col>`.
- [ ] **Step 5: Verify** — tabular data only (no layout tables), every table has `<caption>`, `th` has `scope`, no `<td>` used as a header.
- [ ] **Step 6: User review gate.**

---

## Task 5: Theme 05 — Media (accent `#db2777`, soft `#fce7f0`)

- [ ] **Step 0 (co-creation):** propose + approve.
- [ ] **Step 1: `oefening1-foto-bijschrift`** (Makkelijk) — one `<figure>` with `<img alt>` + `<figcaption>`. Image `img/joshua-tree.jpg`.
- [ ] **Step 2: `oefening2-stappenplan-in-beeld`** (Gemiddeld) — one `<figure>` with ≥3 `<img>` (each with meaningful `alt`) + one shared `<figcaption>`. Images `img/paard-1.jpg`, `img/paard-2.jpg`.
- [ ] **Step 3: `oefening3-video-kaart-embedden`** (Gemiddeld) — embedded YouTube `<iframe>` + Google Maps `<iframe>` + begeleidende tekst. No local images.
- [ ] **Step 4: `oefening4-responsieve-afbeelding`** (Moeilijk) — `<picture>` with multiple `<source media="...">` (500/960/1280 variants) + `<img>` fallback; argue jpg vs png vs svg vs webp in a comment. Images `img/landschap-*.jpg`.
- [ ] **Step 5: Verify** — every `<img>` has relevant `alt`; ≥1 figure/figcaption; content-vs-design reasoning present where asked.
- [ ] **Step 6: User review gate.**

---

## Task 6: Theme 06 — Formulieren (accent `#0d9488`, soft `#e0f5f2`)

- [ ] **Step 0 (co-creation):** propose + approve.
- [ ] **Step 1: `oefening1-login`** (Makkelijk) — username (`text`) + password (`password`), both `required`, `<button type="submit">`.
- [ ] **Step 2: `oefening2-contactformulier`** (Gemiddeld) — naam (`text`), e-mail (`email`), telefoon (`tel`), bericht (`<textarea>`), submit + reset. **Referentie-note**.
- [ ] **Step 3: `oefening3-enquete-inschrijving`** (Gemiddeld–moeilijk) — tekstvelden, `<select>`, radio's, checkboxes, `range`, `<fieldset>`/`<legend>` (verplicht vs optioneel). **Referentie-note**.
- [ ] **Step 4: `oefening4-webshop-bestelformulier`** (Moeilijk) — `file` (+`accept`), `number` (+`min`/`max`/`step`), `date`, `color`, multiple `<fieldset>`, `required`/`placeholder`.
- [ ] **Step 5: Verify** — every control has a correctly-linked `<label for>` (or nested for radio/checkbox), correct `type` per datum, ≥1 `required`, submit button, one `<div>`/`<p>` per label/control pair.
- [ ] **Step 6: User review gate.**

---

## Task 7: Theme 07 — Structureren (accent `#7c3aed`, soft `#efe9fd`)

- [ ] **Step 0 (co-creation):** propose + approve.
- [ ] **Step 1: `oefening1-basis-pagina-skelet`** (Makkelijk) — `<header>` (titel+logo), `<nav>`, `<main>` (placeholder), `<footer>` (copyright+links). **Referentie-note**.
- [ ] **Step 2: `oefening2-blogartikel-zijbalk`** (Gemiddeld) — `<main>` with `<article>` + `<aside>`. Image `img/bureau.jpg`. **Referentie-note**.
- [ ] **Step 3: `oefening3-van-div-soep`** (Gemiddeld–moeilijk) — error-fixing (T2): div-only page → rewrite with semantic elements. Internal error list.
- [ ] **Step 4: `oefening4-nieuwssite-layout`** (Moeilijk) — `<nav>` + multiple `<section>`/`<article>` + `<aside>` + `<footer>` with social links in a `<ul>`. **Referentie-note**.
- [ ] **Step 5: Verify** — one each of header/main/footer/nav; correct section/article/aside/div distinction (with comment rationale where ambiguous); related content grouped together.
- [ ] **Step 6: User review gate.**

---

## Task 8: Theme 08 — Samenvatting (accent `#2563eb`, soft `#e8f0fe`)

- [ ] **Step 0 (co-creation):** propose + approve (largest theme — allow a bit more back-and-forth).
- [ ] **Step 1: `oefening1-debug`** (Gemiddeld) — error-fixing (T2): page with deliberate errors (hoofdletters/quotes, missing `alt`, wrong nesting, `<b>`/`<i>`, table-for-layout). Student finds + corrects, then validates via W3C. Internal error list; `info.md` mentions the W3C validator as control step.
- [ ] **Step 2: `oefening2-persoonlijk-cv`** (Gemiddeld–moeilijk) — header/main/footer, title hierarchy, lists, a table (talen/opleiding), a contact form. Image `img/pasfoto.jpg`. **Referentie-note**.
- [ ] **Step 3: `oefening3-mini-website-hobby`** (Moeilijk) — text + internal/external links + figure/figcaption + table + form in one semantically structured page. Image `img/gitaar.jpg`. **Referentie-note**.
- [ ] **Step 4: `oefening4-eindproject-website`** (Zeer moeilijk) — multi-page site (home, over ons, aanbod/menu with table, contact with form), consistent `<nav>`, internal links, media. Image `img/restaurant.jpg`. **Referentie-note**. Note: this exercise's "index.html" is a small multi-file site; add the extra `.html` pages as siblings in the same folder.
- [ ] **Step 5: Verify** — all huisregels from lessons 1–7; W3C validator mentioned as control step; ≥1 exercise combines text+links+media+structure, ≥1 has table+form.
- [ ] **Step 6: User review gate.**

---

## Task 9: Root overview `index.html`

**Files:**
- Create: `index.html` (repo root)

- [ ] **Step 1: Write root `index.html`** — a landing page (Dutch) that links to every exercise. Use the base huisstijl (accent `#2563eb`), an `<h1>`, and per theme a `<section>` with an `<h2>` and a `<ul>` of 4 links pointing to each `oefening*/index.html` (relative paths). Link each folder's `oplossing.html` too, labelled "(oplossing)". Example:
  ```html
  <li><a href="01-syntax/oefening1-mijn-eerste-pagina/index.html">01.1 Mijn eerste pagina</a> (<a href="01-syntax/oefening1-mijn-eerste-pagina/oplossing.html">oplossing</a>)</li>
  ```
- [ ] **Step 2: Verify** — open in a browser; every one of the 32 links resolves (no 404), all 8 themes listed.
- [ ] **Step 3: Final pass** — spot-check 2–3 random exercises end-to-end against the huisregel checklist.

---

## Self-Review notes (run at the end of writing files)

- **Spec coverage:** every "Wat moet sowieso in de oefeningen komen" block per lesson maps to a theme task's Vereisten and Verify step. Error-fixing exercises (01.2, 07.3, 08.1) use T2. Screenshot notes applied to the 13 listed exercises. W3C validator mentioned in lesson 08. ✓
- **Placeholders:** none — templates are full code; accent hexes and soft tints are explicit per task; image URLs are in the manifest.
- **Consistency:** CSS custom-property names (`--accent`, `--accent-soft`, `--page`, `--card`, `--text`, `--muted`, `--border`) are identical across all theme tasks; folder names match the File Structure map; the info.md template fields match the comment-block fields.
