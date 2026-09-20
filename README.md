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
  - I Chrome/Edge (via `localhost` eller HTTPS) kan du peka ut en mapp
    en gång och få ett riktigt bibliotek — låtar sparas och laddas direkt
    från disken.
  - I Firefox/Safari (eller om filen öppnas direkt från disk) faller
    Chordic Lite tillbaka på nedladdning och filuppladdning.
- **Skriv ut till PDF** — gränssnittet göms automatiskt i utskriftsmallen.
- **Sparar automatiskt** aktuell låt i `localStorage`, så inget tappas
  vid en omladdning.

---

## Komma igång

**Snabbast:** öppna [livedemon](https://zebaztian2525.github.io/chordic-lite/)
i Chrome, Edge eller Firefox.

**Lokalt:** ladda ner `index.html` (eller `chordic-lite.html`) och öppna
den i valfri modern webbläsare.

Mappbiblioteket (endast Chrome/Edge) kräver en säker kontext. Livedemon
fungerar direkt eftersom GitHub Pages serverar över HTTPS. Kör du filen
lokalt kan du starta en enkel server:

```bash
python3 -m http.server 8000
# öppna sedan http://localhost:8000/index.html
