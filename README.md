# Calendos

En social kalender: hav din egen kalender, få anbefalet events ud fra dine interesser, følg dine venners kalendere og find et tidspunkt, hvor hele gruppen har fri.

Afsluttende projekt i *Grundlæggende datalogi*, efterår 2026. Aflevering **18. december 2026**.

---

## Sider

| Side | Fil | Hvad den skal kunne | Ansvarlig |
|---|---|---|---|
| Min kalender | `index.html` | Se ugen, tilføje egne events | _navn_ |
| Anbefalinger | `anbefalinger.html` | Vælge interesser og få forslag til events | _navn_ |
| Venner | `venner.html` | Følge venner og se fælles events/interesser | _navn_ |
| Grupper | `grupper.html` | Finde tidspunkter hvor alle har fri | _navn_ |

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
└── data/
    ├── events.json       Eksempel-events
    └── users.json        Eksempel-brugere (venner)
```

**Hver side har sin egen `.css`- og `.js`-fil.** Så kan vi arbejde samtidig uden at ødelægge hinandens kode. Ændringer i `style.css` og `data.js` påvirker alle sider, så snak sammen før I ændrer dem.

---

## Kom i gang (første gang)

1. **Lav en GitHub-konto** på [github.com](https://github.com) og send dit brugernavn til Timothée, så du kan blive tilføjet til repoet.
2. **Acceptér invitationen** fra GitHub (den kommer på mail).
3. **Installér programmerne:**
   - [GitHub Desktop](https://desktop.github.com)
   - [Visual Studio Code](https://code.visualstudio.com)
4. **Hent projektet:** Åbn GitHub Desktop → *File → Clone repository* → vælg `calendos` → *Clone*.
5. **Åbn i VS Code:** I GitHub Desktop, tryk *Open in Visual Studio Code*.
6. **Installér to udvidelser i VS Code:** tryk Ctrl+Shift+X, søg efter **Live Server** og **Live Share**, og tryk *Install* på begge.

## Se hjemmesiden

Højreklik på `index.html` i VS Code → **Open with Live Server**. Siden åbner i browseren og opdaterer selv, når du gemmer.

> Dobbeltklik ikke bare på HTML-filen. Så kan JavaScript ikke hente filerne i `data/`.

---

## Sådan arbejder vi hver dag

1. **Før du starter:** I GitHub Desktop, tryk **Fetch origin** og derefter **Pull origin**. Så har du de andres nyeste ændringer.
2. **Kod** i dine egne filer.
3. **Når du er færdig** (eller stopper for i dag):
   - Skriv en kort besked nederst til venstre i GitHub Desktop, fx `Tilføjet formular til nyt event`.
   - Tryk **Commit to main**.
   - Tryk **Push origin**.

**Gode vaner**
- Pull før du starter, push når du stopper.
- Commit ofte med små, tydelige beskeder. Historikken bruger vi i rapporten.
- Rediger ikke en anden persons fil uden at sige det først.
- Kod sammen på samme fil? Brug **Live Share** i VS Code (ikonet i venstre side → *Share* → send linket).

**Hvis GitHub Desktop siger "conflict":** Bliv rolig og spørg i gruppen. VS Code viser begge versioner, og man vælger den rigtige med *Accept Current* / *Accept Incoming*.

---

## Data

Indtil videre ligger al data lokalt:
- `data/events.json`: events der kan anbefales
- `data/users.json`: venner med interesser og hvilke events de skal til
- Brugerens egne events kan gemmes i browseren med `localStorage`

Al kode der henter eller gemmer data skal ligge i `static/js/data.js`.

## Senere: online med Flask

Strukturen er lavet, så den passer til Flask:
- `static/` er præcis den mappe Flask bruger til CSS, JS og billeder.
- HTML-filerne flyttes ind i en `templates/`-mappe.
- `data.js` ændres fra at læse JSON-filer/`localStorage` til at kalde Flask, fx `fetch("/api/events")`. Resten af JavaScript-koden kan blive som den er.

---

## Gruppe

- Timothée
- _navn_
- _navn_
- _navn_
