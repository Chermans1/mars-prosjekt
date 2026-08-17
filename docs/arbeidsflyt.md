# Arbeidsflyt

Vi jobber med én branch per person. `main` skal alltid være en versjon som virker.

## Branchene

| Branch | Eier | Innhold |
|---|---|---|
| `main` | felles | Alltid fungerende. Ingen jobber direkte her. |
| `christian` | Christian | Seksjon 1-2 |
| `orjan` | Ørjan | Seksjon 3-4 |
| `sebastian` | Sebastian | Seksjon 5-7 |

Trenger vi å endre noe felles, lager vi en egen branch for det, for eksempel `felles/variabler`, og merger den inn når alle er enige.

## Førstegangsoppsett

En av oss oppretter repoet på GitHub og pusher stillaset til `main`. De to andre kloner:

```bash
git clone https://github.com/Chermans1/mars-prosjekt.git
cd mars-prosjekt
```

Sett navn og e-post én gang per maskin:

```bash
git config --global user.name "Ditt Navn"
git config --global user.email "din@epost.no"
```

Lag din egen branch og push den opp:

```bash
git checkout -b christian
git push -u origin christian
```

`-u origin christian` kobler den lokale branchen til GitHub. Etterpå holder det med `git push`.

## Daglig rutine

**1. Sørg for at du står på din egen branch**

```bash
git branch
```

Stjernen viser hvor du er. Står du feil sted:

```bash
git checkout christian
```

**2. Hent inn det som har kommet i main**

```bash
git pull origin main
```

Dette er det viktigste steget. Gjør det hver gang du setter deg ned. Hopper du over det, jobber du videre på gammel kode, og da blir merge vondt senere.

**3. Jobb, og commit underveis**

```bash
git add .
git commit -m "Legg til hover-effekt på navlenker"
```

Commit ofte. Små commits er lettere å forstå og lettere å angre.

**4. Push**

```bash
git push
```

## Når du er ferdig med noe

Lag en pull request på GitHub fra din branch inn i `main`. En av de andre ser over og merger.

Ikke merge din egen PR. Poenget er at noen andre får sett koden.

Etter at PR-en er merget, hent den inn i din egen branch:

```bash
git pull origin main
```

Da har du de andres arbeid hos deg, og neste PR blir mindre å slå sammen.

## Commit-meldinger

Skriv hva endringen gjør, ikke hva du gjorde.

Bra:

- `Legg til responsivt oppsett for kortseksjonen`
- `Fiks feil i grid-plassering på collagen`
- `Bytt placeholder til ekte NASA-bilde i hero`

Dårlig:

- `oppdatering`
- `fix`
- `ting`
- `asdf`

Norsk eller engelsk går like bra, bare vær konsekvent.

## Hvis du får merge-konflikt

Ikke få panikk, og ikke slett noe. Git markerer konflikten slik i filen:

```
<<<<<<< HEAD
    din kode
=======
    den andre sin kode
>>>>>>> main
```

Slik løser du den:

1. Åpne filen og finn markørene
2. Bestem hva som skal stå igjen - noen ganger begge deler, noen ganger bare den ene
3. Slett alle tre markørlinjene (`<<<<<<<`, `=======`, `>>>>>>>`)
4. Lagre
5. `git add FILNAVN` og `git commit`

Er du usikker på hva som skal beholdes: spør den som skrev den andre delen. Ikke gjett.

## Ting som skaper konflikter

- Noen glemmer å hente fra `main` før de begynner
- To personer redigerer samme linje i `index.html` eller `base.css`
- Store omskrivinger av felles filer uten å si fra
- Editor som auto-formaterer hele filen, så alle linjer ser endret ut

Det siste er verdt å sjekke med en gang: skru av "format on save" for HTML og CSS, eller bli enige om samme innstillinger. Ellers får dere konflikter på linjer ingen har rørt.

## Nyttige kommandoer

```bash
git status              # hva har jeg endret?
git diff                # vis endringene linje for linje
git log --oneline -10   # de ti siste commitene
git branch              # hvilke brancher finnes lokalt, og hvor står jeg?
git checkout main       # bytt til main
git restore FILNAVN     # angre endringer i en fil du ikke har committet
git stash               # legg endringene til side midlertidig
git stash pop           # hent dem tilbake
```

## Før innlevering

- [ ] Alle brancher er merget inn i `main`
- [ ] `git pull` på `main` gir ingen nye endringer
- [ ] Siden fungerer når man åpner `index.html` fra en frisk klone
- [ ] Ingen døde lenker eller manglende bilder
- [ ] Testet i minst to nettlesere
