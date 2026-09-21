# 🎵 Chordic Lite

**[▶ Try it live in your browser](https://zebaztian2525.github.io/chordic-lite/)** — no installation required.

**🌍 Languages:** English (default) · [Svenska](https://zebaztian2525.github.io/chordic-lite/index-sv.html)

A small, browser-based chord editor for songwriters, church musicians, and
anyone who wants to place chords exactly where they belong — right above the
syllable that carries the beat.

Chordic Lite runs entirely in your browser. No server, no install, no account.
Just open it and start typing.

> **Status:** early prototype. Feedback and pull requests are very welcome.

---

## Features

- **Write lyrics, place chords above individual letters.** Every character in
  the lyric is a drop target, so you can put three chords over "Amazing" —
  one for each stressed vowel — or drop a chord in the gap between two words.
- **Drag-and-drop chords** from a palette of diatonic chords in the current key.
- **Build custom chords** — root note, quality (m, 7, maj7, sus4, dim…), and
  slash bass note. Drag the result onto a letter, or click a letter and
  press "Add".
- **Piano keyboard** for choosing key. The palette updates to the diatonic
  chords of that key automatically.
- **Transpose** the entire song up or down one semitone at a time.
  Chord symbols *and* the selected key move together.
- **ChordPro import and export** — compatible with most other chord editors.
  Imported intros (leading chord-only lines) are shown as a separate block in
  the song header, so they don't clutter the lyrics.
- **Chord positions follow your edits.** When you add or remove text, the
  chords stay above the correct letters. Insert a new line and everything
  below moves down; the chords come along.
- **Save and load** songs as `.chordic.json` files.
  - In Chromium-based browsers (Chrome, Edge, Vivaldi, Brave, Opera, Deepin
    Browser…) you can pick a folder once and get a proper library — songs
    save and load directly from disk. This usually works even when opening
    the file directly from disk.
  - In Firefox and Safari, Chordic Lite falls back to downloading and
    uploading individual files.
- **Print to PDF** — the UI hides itself in the print stylesheet.
- **Autosaves** your current song to `localStorage`, so nothing is lost on
  a refresh.

---

## Getting started

**Quickest:** open the [live demo](https://zebaztian2525.github.io/chordic-lite/)
in any modern browser.

**Local:** download `index.html` and open it by double-clicking. In
Chromium-based browsers the folder library works right away. In Firefox and
Safari you need to start a small local server if you want the folder library:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

Downloading and uploading files works in every browser, no matter how the
page is opened.

------

## How to use

| Action             | How                                                          |
| :----------------- | :----------------------------------------------------------- |
| Select a letter    | Click it                                                     |
| Add a chord        | Drag a chip onto a letter, or select a letter and click a chord |
| Add a custom chord | Build it in the builder panel, then drag or press "Add"      |
| Move a chord       | Drag it to a new letter                                      |
| Remove a chord     | `Ctrl`-click (`⌘`-click on macOS) it                         |
| Change key         | Click a piano key                                            |
| Transpose          | Use `−½` / `+½`                                              |
| Edit lyrics        | Type in the text area on the right                           |
| Import ChordPro    | Click "📥 ChordPro"                                           |
| Export ChordPro    | Click "📤 ChordPro"                                           |
| Print / PDF        | Click "🖨️ PDF"                                                |
| Save file          | Use the library panel or "⬇ Download"                        |
| Switch to Swedish  | Click "🇸🇪 SV" in the top right                               |

------

## Roadmap / ideas

- □ 

  Undo / redo

- □ 

  Verse / chorus / bridge markers with repeat

- □ 

  Multiple chord rows per line (two-voice arrangements)

- □ 

  Custom chord palette per song

- □ 

  Keyboard navigation (arrow keys to move selection, Tab between chords)

If you'd like to help with any of these, open an issue or a PR.

------

## Browser support

| Feature                              | Chromium* | Firefox | Safari |
| :----------------------------------- | :-------- | :------ | :----- |
| Core editing                         | ✅         | ✅       | ✅      |
| Folder library via `file://`         | ✅         | —       | —      |
| Folder library via HTTPS / localhost | ✅         | —       | —      |
| Download / upload files              | ✅         | ✅       | ✅      |
| Print to PDF                         | ✅         | ✅       | ✅      |

\* Chromium covers Chrome, Edge, Vivaldi, Brave, Opera, Deepin Browser, and
other browsers built on the same engine.

------

## Tech

Single HTML file. No build step, no dependencies, no framework.
Plain HTML, CSS, and vanilla JavaScript.

The chord/character model is intentionally simple:

js

```
state = {
  title:  "My song",
  artist: "Bob Dylan",
  intro:  ["F", "Am", "Dm", "C", "F"],
  lyrics: "Amazing grace how sweet the sound\n…",
  chords: [ { line: 0, char: 4, chord: "G" }, … ],
  key:    "C"
}
```



`chords` is a flat list of `{ line, char, chord }` — one chord per position.
The `char` index counts characters within a line, including spaces, so a
chord placed "between two words" simply has the index of the space character.
`intro` holds the leading chord sequence (e.g. a riff or count-in) shown in
the song header rather than in the lyrics.

When you edit the lyrics, `applyLyrics()` runs a prefix/suffix diff between
the old and new text and re-maps every chord position. Chords before the edit
stay put, chords after the edit shift by the length of the change, and chords
inside the changed region are dropped.

------

## License

MIT — see [LICENSE](https://license/).

<details> <summary><strong>🇸🇪 Om projektet (svenska)</strong></summary>
Chordic Lite är ett litet, webbläsarbaserat ackordprogram för låtskrivare
och kyrkomusiker. Du skriver in låttexten och placerar ackord ovanför exakt
den bokstav där ackordet ska byta — även flera ackord över samma ord, och i
mellanrummen mellan ord.

Testa live (engelska): https://zebaztian2525.github.io/chordic-lite/
Svensk version: https://zebaztian2525.github.io/chordic-lite/index-sv.html

Allt körs lokalt i webbläsaren. Ingen server, inget konto, ingen installation.
Filen är en enda HTML-fil och kan öppnas direkt från disk.

Feedback och bidrag är varmt välkomna!

Om du vill läsa README på svenska kan du använda webbläsarens
översättningsfunktion — högerklicka på sidan och välj "Översätt till svenska".

</details> 
