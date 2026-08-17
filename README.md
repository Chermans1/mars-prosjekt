# Mission To Mars

Skoleprosjekt. En landingsside om NASAs InSight-oppdrag, bygget etter et utlevert designbilde.

Ren HTML og CSS. Ingen rammeverk, ingen byggesteg.

**Status:** stillas. Filene finnes, men koden er ikke skrevet ennå.

## Gruppe og brancher

| Person | Branch | Seksjoner | CSS-fil |
|---|---|---|---|
| Christian | `christian` | 1. Hero + navbar<br>2. Split | `css/christian.css` |
| Ørjan | `orjan` | 3. NASA Insight<br>4. Why Mars? | `css/orjan.css` |
| Sebastian | `sebastian` | 5. Kort<br>6. Banner<br>7. Footer | `css/sebastian.css` |

Felles: `index.html` og `css/base.css`. Endringer der avtales i gruppen først.

## Kom i gang

```bash
git clone https://github.com/BRUKERNAVN/mars-prosjekt.git
cd mars-prosjekt
git checkout -b DITT-NAVN
```

Åpne `index.html` i nettleseren. Bruker du VS Code, anbefales **Live Server** - da oppdateres siden automatisk når du lagrer.

Se `docs/arbeidsflyt.md` for git-rutinene.

## Mappestruktur

```
mars-prosjekt/
├── index.html          Tomme seksjoner merket med eier
├── css/
│   ├── base.css        Variabler, reset, typografi (felles)
│   ├── christian.css   Seksjon 1-2
│   ├── orjan.css       Seksjon 3-4
│   └── sebastian.css   Seksjon 5-7
├── img/                Bilder (tom foreløpig)
├── docs/
│   └── arbeidsflyt.md  Git-rutiner
├── .github/
│   └── pull_request_template.md
├── .gitignore
└── README.md
```

Rekkefølgen på `<link>`-taggene i `index.html` er bevisst: `base.css` først, deretter personfilene. Bytter du om, kan felles stiler overstyre de individuelle.

## Rekkefølge på arbeidet

**Steg 1 - felles, før noen begynner å style**

Bli enige om variablene i `base.css`: farger, fonter, brekkpunkter og avstander. Gjør dette sammen på én branch og merge den inn. Det er mye lettere å avtale én gang enn å rette opp tre ulike nyanser etterpå.

**Steg 2 - hver for seg**

Nå kan alle jobbe parallelt på hver sin branch uten å komme i veien for hverandre.

**Steg 3 - felles igjen**

Bilder, tekst, testing, tilgjengelighet.

## Bilder

`img/` er tom. Legg inn ekte bilder her og komprimer dem før dere pusher - ingenting over 500 KB.

Gode kilder til frie NASA-bilder:

- [images.nasa.gov](https://images.nasa.gov)
- [mars.nasa.gov/insight](https://mars.nasa.gov/insight/)

## Font

Ikke valgt ennå. Originalen ser ut til å bruke en tung geometrisk sans. Space Grotesk eller Archivo fra Google Fonts ligger nært. Legges inn i `<head>` og settes som `--font` i `base.css`.

## Å gjøre

- [ ] Bli enige om variabler i `base.css`
- [ ] Velge og legge inn font
- [ ] Bygge seksjon 1-2 (Christian)
- [ ] Bygge seksjon 3-4 (Ørjan)
- [ ] Bygge seksjon 5-7 (Sebastian)
- [ ] Legge inn bilder
- [ ] Skrive ferdig innholdstekst
- [ ] Sjekke kontrast og tastaturnavigasjon
