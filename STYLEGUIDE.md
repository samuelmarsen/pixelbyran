# Stilguide – Pixelbyrån AB

Gemensam referens för gruppen. Följ den här när du skriver CSS så att alla sidor ser likadana ut.
Ändringar i stilguiden tas upp med gruppen först.

## Företaget

**Pixelbyrån AB** – en webbyrå som gör hemsidor och appar åt småföretag.

## Färger

Definieras som CSS-variabler i `css/style.css` (`:root`). Använd alltid variablerna, skriv aldrig hex-koder direkt i andra filer.

| Variabel            | Hex       | Används till                          |
|---------------------|-----------|---------------------------------------|
| `--color-dark`      | `#1e2a38` | Header, footer, rubriker, brödtext    |
| `--color-dark-2`    | `#2a394b` | Öppen mobilmeny, hover på mörk yta    |
| `--color-bg`        | `#f4f6f8` | Sidans bakgrund                       |
| `--color-white`     | `#ffffff` | Kort, formulärfält                    |
| `--color-accent`    | `#ff7a59` | Knappar, länkar, aktiv menylänk       |
| `--color-muted`     | `#5b6775` | Sekundär text (t.ex. roll på kort)    |
| `--color-valid`     | `#2e9e5b` | Formulär: giltig inmatning            |
| `--color-invalid`   | `#d64545` | Formulär: felaktig inmatning          |

## Typsnitt

Laddas från Google Fonts i `<head>` på varje sida (före länken till `style.css`):

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=Poppins:wght@600;700&display=swap" rel="stylesheet">
```

| Variabel         | Typsnitt  | Används till         |
|------------------|-----------|----------------------|
| `--font-heading` | Poppins   | `h1`–`h4`, logotyp   |
| `--font-body`    | Inter     | All övrig text       |

Grundstorlek: `16px`, radavstånd `1.6`.

## Avstånd och former

| Variabel      | Värde   | Används till                   |
|---------------|---------|--------------------------------|
| `--space-s`   | `0.5rem`| Små mellanrum                  |
| `--space-m`   | `1rem`  | Standardavstånd                |
| `--space-l`   | `2rem`  | Mellan sektioner               |
| `--radius`    | `8px`   | Kort, knappar, formulärfält    |
| `--max-width` | `1100px`| Maxbredd på `.container`       |

## Brytpunkt

En gemensam brytpunkt: **`768px`**. Bygg mobil först, lägg desktop i:

```css
@media (min-width: 768px) { ... }
```

## Gemensamma klassnamn

| Klass           | Element / användning                                         | Fil              |
|-----------------|--------------------------------------------------------------|------------------|
| `.site-header`  | `<header>` högst upp                                         | navigation.css   |
| `.logo`         | Länk med företagsnamnet                                      | navigation.css   |
| `.navicon`      | Hamburgerknappen (`<button>`), syns bara under 768px         | navigation.css   |
| `.nav`          | `<ul>` med menylänkar                                        | navigation.css   |
| `.nav--open`    | Läggs på `.nav` av `navigation.js` för att visa mobilmenyn   | navigation.css   |
| `.container`    | Centrerat innehåll med `--max-width`                         | style.css        |
| `.site-footer`  | `<footer>` längst ner                                        | style.css        |
| `.btn`          | Knapp (korall bakgrund, vit text)                            | style.css        |
| `.card`         | Personkort på anställda-sidan                                | anstallda.css    |
| `.valid`        | Formulärfält med giltig inmatning (grön ram)                 | kontakt.css      |
| `.invalid`      | Formulärfält med felaktig inmatning (röd ram)                | kontakt.css      |
| `.feedback`     | Text under fält med valideringsmeddelande                    | kontakt.css      |

Namnge egna klasser på personliga sidor med prefix, t.ex. `.p1-slideshow`, `.p2-projects`, så de inte krockar med gemensamma klasser.

## Grundvariabler (klistra in högst upp i `css/style.css`)

```css
:root {
    --color-dark: #1e2a38;
    --color-dark-2: #2a394b;
    --color-bg: #f4f6f8;
    --color-white: #ffffff;
    --color-accent: #ff7a59;
    --color-muted: #5b6775;
    --color-valid: #2e9e5b;
    --color-invalid: #d64545;

    --font-heading: "Poppins", sans-serif;
    --font-body: "Inter", sans-serif;

    --space-s: 0.5rem;
    --space-m: 1rem;
    --space-l: 2rem;
    --radius: 8px;
    --max-width: 1100px;
}
```

## Regler

- Ingen CSS i HTML-filerna (inga `style`-attribut eller `<style>`-taggar).
- Globala egenskaper (typsnitt, färg, radavstånd) sätts på `body` och ärvs – upprepa dem inte.
- Ändra bara i gemensamma CSS-filer efter att ha sagt till i gruppen.
- Validera CSS på https://jigsaw.w3.org/css-validator/ innan pull request.
