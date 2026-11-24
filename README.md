# Calendos

En social kalender: hav din egen kalender, få anbefalet events ud fra dine interesser, følg dine venners kalendere og find et tidspunkt, hvor hele gruppen har fri.

Afsluttende projekt i *Grundlæggende datalogi*, efterår 2026. Aflevering **18. december 2026**.

Vores projektbeskrivelse og samarbejdsaftale ligger i [`docs/`](docs/).

---

## Sider

| Side | Fil | Hvad den skal kunne |
|---|---|---|
| Min kalender | `index.html` | Se ugen, tilføje egne events |
| Anbefalinger | `anbefalinger.html` | Vælge interesser og få forslag til events |
| Venner | `venner.html` | Følge venner og se fælles events/interesser |
| Grupper | `grupper.html` | Finde tidspunkter hvor alle har fri |

Ingen side "ejes" af én person. Vi laver dem sammen i par, så alle kender hele koden.

## Mappestruktur

```
calendos/
├── index.html            Min kalender (forsiden)
├── anbefalinger.html
├── venner.html
├── grupper.html
├── static/
│   ├── css/
│   │   ├── style.css     Fælles stil (farver, menu, knapper, formularer)
│   │   └── <side>.css    Stil kun for én side
│   ├── js/
│   │   ├── data.js       Fælles: hent og gem data
│   │   └── <side>.js     JavaScript kun for én side
│   └── img/              Billeder
├── data/
│   ├── events.json       Eksempel-events
│   └── users.json        Eksempel-brugere (venner)
└── docs/                 Projektbeskrivelse og andre dokumenter
```

**Hver side har sin egen `.css`- og `.js`-fil.** Så er det nemt at finde rundt i koden, og en fejl på én side ødelægger ikke de andre. Ændringer i `style.css` og `data.js` påvirker alle sider, så sig til før I ændrer dem.

---

## Sådan arbejder vi sammen

Vi har alle samme niveau og arbejder mest sammen fysisk, ved én computer.

**Pair programming**
- **Driver** skriver koden.
- **Navigator** læser med, stiller spørgsmål, finder fejl og foreslår løsninger.
- Vi **bytter rolle ca. hver halve time**, så alle skriver kode.
- Vi **bytter også computer** fra gang til gang. GitHub viser commits under den, hvis computer der kodes på, så på den måde kan man se, at alle bidrager.
- Når en del er færdig, gennemgår vi den sammen, så alle kan forklare hele løsningen.

**Roller der går på skift hver uge**
- **Tovholder:** holder styr på tidsplanen og møderne.
- **Rapportansvarlig:** samler rapporten.

**Beslutninger** tager vi sammen. Kan vi ikke blive enige, stemmer vi. Står det lige, spørger vi vejlederen.

---

## Iterativ udvikling og test

Vi bygger én funktion ad gangen i korte cyklusser:

1. **Planlæg**: hvad skal funktionen kunne?
2. **Skitsér**: tegn den på papir eller i en wireframe.
3. **Programmér**: lav den simpleste version, der virker.
4. **Test**: prøv den i browseren efter hver ændring, og senere med testpersoner.
5. **Evaluér**: hvad virker, hvad skal rettes? Så starter vi forfra.

**Tidsplan**

| Uge | Mål |
|---|---|
| 48 | Problemformulering, skitser/wireframes, repo og fælles design |
| 49 | 1. iteration: kalender og anbefalinger virker i en simpel version og er testet |
| 50 | 2. iteration: venne- og gruppefunktion, test af hele siden. Præsentationsdag 12/12 |
| 51 | Sidste iteration: rettelser efter feedback, rapporten færdig, aflevering 18/12 |

---

## Kom i gang (første gang)

1. **Lav en GitHub-konto** på [github.com](https://github.com) og send dit brugernavn til mig (Timothée), så du kan blive tilføjet til repoet.
2. **Acceptér invitationen** fra GitHub (den kommer på mail).
3. **Installér programmet:**
   - [GitHub Desktop](https://desktop.github.com)
4. **Hent projektet:** Åbn GitHub Desktop → *File → Clone repository* → vælg `calendos` → *Clone*.
5. **Åbn i VS Code:** I GitHub Desktop, tryk *Open in Visual Studio Code*.
6. **Installér to udvidelser i VS Code:** tryk Ctrl+Shift+X, søg efter **Live Server** og **Live Share**, og tryk *Install* på begge.

## Se hjemmesiden

Højreklik på `index.html` i VS Code → **Open with Live Server**. Siden åbner i browseren og opdaterer selv, når du gemmer.

> Dobbeltklik ikke bare på HTML-filen. Så kan JavaScript ikke hente filerne i `data/`.

---

## GitHub: upload og hent arbejdet

GitHub er vores fælles sted for koden. Det gør det hurtigt og sikkert at uploade og hente arbejdet, og det er samtidig vores backup.

1. **Før I starter:** I GitHub Desktop, tryk **Fetch origin** og derefter **Pull origin**. Så har I den nyeste version. (Timothée forklarer det mere i dybden.)
2. **Kod sammen** (se *Pair programming* ovenfor).
3. **Test i browseren**, at siden stadig virker.
4. **Når I er færdige** (eller stopper for i dag):
   - Skriv en kort besked nederst til venstre i GitHub Desktop, fx `Tilføjet formular til nyt event`.
   - Tryk **Commit to main**.
   - Tryk **Push origin**.

**Gode vaner**
- Pull før I starter, push når I stopper. Så ligger den nyeste version altid sikkert på GitHub.
- Commit ofte med små, tydelige beskeder. Historikken bruger vi i rapporten.
- Push kun kode, der er testet og virker.
- Koder I hver for sig, men på samme fil? Brug **Live Share** i VS Code (ikonet i venstre side → *Share* → send linket).

**Hvis GitHub Desktop siger "conflict":** spørg i gruppen. VS Code viser begge versioner, og man vælger den rigtige med *Accept Current* / *Accept Incoming*.

---

## Data

Indtil videre ligger al data lokalt:
- `data/events.json`: events der kan anbefales
- `data/users.json`: venner med interesser og hvilke events de skal til
- Brugerens egne events kan gemmes i browseren med `localStorage`

Al kode der henter eller gemmer data skal ligge i `static/js/data.js`.

## Senere: måske online

I skal ikke tænke på `static/`, `templates/` osv. Det tager jeg mig af, hvis siden skal online senere.

---

## Gruppe

- Ida Carolina Kronholm
- Olivia Lundberg
- Alberte Birkholm
- Timothée
