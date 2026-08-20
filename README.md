# Mission To Mars

Skoleprosjekt i HTML og CSS. En landingsside om Mars, bygget etter et utlevert designbilde.

**Live:** https://chermans1.github.io/mars-prosjekt/

Ren HTML og CSS. Ingen rammeverk, ingen byggesteg, ingen avhengigheter.

---

## Om oppgaven

One-page nettside med en planet som tema. Kravet var minimum to seksjoner og en navbar som scroller til dem, med vekt på design, layout, fargevalg, bilder og fonter.

Siden er bevisst ikke responsiv. Oppgaveteksten sier den ikke trenger å optimaliseres for mobil, og gruppen valgte å bruke tiden på layout og innhold i stedet.

---

## Hva som er bygget

| #   | Seksjon                 | Status      | Ansvarlig |
| --- | ----------------------- | ----------- | --------- |
| 1   | Hero med navbar         | Ferdig      | Christian |
| 2   | Split, InSight-landeren | Ferdig      | Christian |
| 3   | Mars Rovers             | Ferdig      | Ørjan     |
| 4   | Why Mars?               | Ikke bygget | Ørjan     |
| 5   | Kort                    | Ikke bygget | Sebastian |
| 6   | Banner                  | Ikke bygget | Sebastian |
| 7   | Footer                  | Ikke bygget | Sebastian |

Tre seksjoner er ferdigstilt. Kravet om minimum to er dermed oppfylt.

---

## Teknisk

**Layout** er bygget med flexbox og grid. `position: absolute` er bevisst unngått.

**Fargene og typografien** ligger som CSS-variabler i `css/base.css` og brukes gjennom hele siden. Ingen farger er skrevet rett inn i reglene.

**Tilgjengelighet:**

- Skip-link som lar tastaturbrukere hoppe forbi navbaren
- Synlig fokusmarkering via `:focus-visible`
- `.visually-hidden` for tekst som skjermlesere skal lese, men som ikke vises
- `prefers-reduced-motion` respekteres
- Aksentfargen finnes i to varianter: `--accent` til flater og `--accent-text` til bokstaver, siden den mørkeste varianten ikke når WCAG-kravet på 4,5:1 mot bakgrunnen

**Bildene** er komprimert før de ble lagt inn.

---

## Struktur

```
mars-prosjekt/
├── index.html          Alle seksjoner, merket med eier
├── css/
│   ├── base.css        Variabler, reset, typografi, tilgjengelighet (felles)
│   ├── christian.css   Seksjon 1-2
│   ├── orjan.css       Seksjon 3-4
│   └── sebastian.css   Seksjon 5-7
├── img/                Bilder
├── docs/
│   └── arbeidsflyt.md  Git-rutiner
└── README.md
```

Rekkefølgen på `<link>`-taggene i `index.html` er bevisst: `base.css` først, deretter personfilene. Bytter du om, overstyrer felles stiler de individuelle.

---

## Gruppe og brancher

| Person    | Branch      | CSS-fil             |
| --------- | ----------- | ------------------- |
| Christian | `christian` | `css/christian.css` |
| Ørjan     | `Orjan`     | `css/orjan.css`     |
| Sebastian | `sebzalo`   | `css/sebastian.css` |

`index.html` og `css/base.css` er felles. Endringer der avtales i gruppen først.

`main` er beskyttet. Alt går via pull request.

---

## Kjøre lokalt

```bash
git clone https://github.com/Chermans1/mars-prosjekt.git
cd mars-prosjekt
```

Åpne `index.html` i nettleseren. Bruker du VS Code, anbefales **Live Server**, da oppdateres siden automatisk når du lagrer.

Se `docs/arbeidsflyt.md` for git-rutinene.

---

## Erfaringer fra samarbeidet

Tre ganger i prosjektet oppsto samme type feil: fellesfiler ble endret fra utdaterte lokale kopier, eller delte klasser ble overstyrt i en personlig CSS-fil. Én gang forsvant alt innholdet i `base.css` fordi det ble committet over fra en gammel versjon.

Lærdommen vi tar med videre:

- Én person eier fellesfila
- Delte klasser som `.container` og `.section` endres ikke i personlige CSS-filer. Trenger du noe annet, lag en ny klasse
- Alle puller fra `main` før de begynner å jobbe
- Automatisk formatering skrus av, ellers skriver editoren om hele filer og lager konflikter der ingen har endret noe
