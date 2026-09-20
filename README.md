# 🎵 Chordic Lite

**[▶ Testa direkt i webbläsaren](https://zebaztian2525.github.io/chordic-lite/)** — ingen installation krävs.

Ett litet, webbläsarbaserat ackordprogram för låtskrivare, kyrkomusiker och
alla som vill placera ackord exakt där de hör hemma — rakt ovanför den
stavelse som bär betoningen.

Chordic Lite körs helt och hållet i webbläsaren. Ingen server, ingen
installation, inget konto. Öppna bara filen och börja skriva.

> **Status:** tidig prototyp. Feedback och pull requests är varmt välkomna.

*Programmet är på svenska. Den som vill ha en engelsk version får gärna
forka repot och översätta — det uppskattas.*

---

## Funktioner

- **Skriv låttext och placera ackord ovanför enskilda bokstäver.** Varje
  tecken i texten är en egen drop-zon, så du kan sätta tre ackord över
  "Amazing" — ett för varje betonad vokal — eller lägga ett ackord i
  mellanrummet mellan två ord.
- **Dra och släpp-ackord** från en palett med diatoniska ackord i vald tonart.
- **Bygg egna ackord** — grundton, typ (m, 7, maj7, sus4, dim…) och
  basnot. Dra resultatet till en bokstav, eller markera en bokstav och
  tryck "Lägg till".
- **Pianoklaviatur** för att välja tonart. Paletten uppdateras automatiskt
  till skalans ackord.
- **Transponera** hela låten upp eller ner ett halvt steg i taget.
  Både ackordsymbolerna och den valda tonarten flyttas med.
- **Spara och ladda** låtar som `.chordic.json`-filer.
  - I Chrome, Edge, Vivaldi, Brave, Opera och andra Chromium-baserade
    webbläsare kan du peka ut en mapp en gång och få ett riktigt
    bibliotek — låtar sparas och laddas direkt från disken. Detta
    fungerar oftast även när du öppnar filen direkt från datorn
    (`file://`).
  - I Firefox och Safari krävs att sidan körs över HTTPS eller
    `localhost` för mappbiblioteket. Där faller Chordic Lite istället
    tillbaka på nedladdning och filuppladdning.
- **Skriv ut till PDF** — gränssnittet göms automatiskt i utskriftsmallen.
- **Sparar automatiskt** aktuell låt i `localStorage`, så inget tappas
  vid en omladdning.

---

## Komma igång

**Snabbast:** öppna [livedemon](https://zebaztian2525.github.io/chordic-lite/)
i valfri modern webbläsare.

**Lokalt:** ladda ner `index.html` (eller `chordic-lite.html`) och öppna
den genom att dubbelklicka på filen. I Chromium-baserade webbläsare
fungerar mappbiblioteket direkt även då. I Firefox och Safari behöver du
starta en enkel lokal server om du vill använda mappbiblioteket:

```bash
python3 -m http.server 8000
# öppna sedan http://localhost:8000/index.html
```

Nedladdning och filuppladdning fungerar i alla webbläsare oavsett hur
sidan öppnas.

---

## Så använder du programmet

| Åtgärd | Hur |
|---|---|
| Markera en bokstav | Klicka på den |
| Lägg till ett ackord | Dra en chip till en bokstav, eller markera en bokstav och klicka på ett ackord |
| Lägg till ett eget ackord | Bygg det i byggarpanelen, dra eller tryck "Lägg till" |
| Flytta ett ackord | Dra det till en ny bokstav |
| Ta bort ett ackord | `Ctrl`-klicka (`⌘`-klicka på macOS) |
| Byt tonart | Klicka på en pianotangent |
| Transponera | Använd `−½` / `+½` |
| Redigera texten | Klicka "✏️ Text" |
| Skriv ut / PDF | Klicka "🖨️ PDF" |
| Spara fil | Använd bibliotekspanelen eller "⬇ Ladda ner" |

---

## Idéer för framtiden

- [ ] Ångra / gör om
- [ ] Vers- / refräng- / brygga-markeringar med upprepning
- [ ] Import och export av ChordPro-format
- [ ] Flera ackordrader per textrad (tvåstämmigt)
- [ ] Anpassad ackordpalett per låt
- [ ] Tangentbordsnavigering (piltangenter för markering, Tab mellan ackord)

Vill du hjälpa till med något av detta? Öppna en issue eller en PR.

---

## Webbläsarstöd

| Funktion | Chromium* | Firefox | Safari |
|---|---|---|---|
| Grundläggande redigering | ✅ | ✅ | ✅ |
| Mappbibliotek via `file://` | ✅ | — | — |
| Mappbibliotek via HTTPS / localhost | ✅ | — | — |
| Ladda ner / ladda upp filer | ✅ | ✅ | ✅ |
| Skriv ut till PDF | ✅ | ✅ | ✅ |

\* Chromium omfattar Chrome, Edge, Vivaldi, Brave, Opera, Deepin Browser
och andra webbläsare som bygger på samma motor.

---

## Teknik

En enda HTML-fil. Inget byggsteg, inga beroenden, inget ramverk.
Ren HTML, CSS och vanlig JavaScript.

Modellen för ackord och tecken är medvetet enkel:

```js
state = {
  title:  "Min låt",
  lyrics: "Amazing grace how sweet the sound\n…",
  chords: [ { line: 0, char: 4, chord: "G" }, … ],
  key:    "C"
}
```

`chords` är en platt lista av `{ line, char, chord }` — ett ackord per
position. `char` räknar tecken inom raden, inklusive mellanslag, så ett
ackord som placerats "mellan två ord" har helt enkelt mellanslagets
index.

---

## Licens

MIT — se [LICENSE](LICENSE).

---

## Om projektet

Chordic Lite är ett litet, webbläsarbaserat ackordprogram för låtskrivare
och kyrkomusiker. Du skriver in låttexten och placerar ackord ovanför
exakt den bokstav där ackordet ska byta — även flera ackord över samma
ord, och i mellanrummen mellan ord.

**Testa live:** https://zebaztian2525.github.io/chordic-lite/

Allt körs lokalt i webbläsaren. Ingen server, inget konto, ingen
installation. Filen är en enda HTML-fil och kan öppnas direkt från disk.

Feedback och bidrag är varmt välkomna!
