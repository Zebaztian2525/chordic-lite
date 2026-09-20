# 🎵 Chordic Lite

**[▶ Test directly in the browser](https://zebaztian2525.github.io/chordic-lite/chordic-lite.html)** — no installation required.

A lightweight, browser-based chord editor for songwriters, church musicians,
and anyone who wants to place chords exactly where they belong — right above
the syllable that carries the beat.

Chordic Lite runs entirely in your browser. No server, no install, no account.
Just open the HTML file and start typing.

> **Status:** early prototype. Feedback and pull requests are very welcome.

---

## Features

- **Write lyrics, place chords above individual letters.** Each character in
  the lyric is a drop target, so you can put three chords over "Amazing" —
  one for each stressed vowel — or drop a chord in the gap between two words.
- **Drag-and-drop chords** from a palette of diatonic chords in the current key.
- **Build custom chords** — root note, quality (m, 7, maj7, sus4, dim…),
  and slash bass note. Drag the result onto a letter, or click a letter and
  press "Lägg till".
- **Piano keyboard** for choosing key. The palette updates to the diatonic
  chords of that key automatically.
- **Transpose** the entire song up or down one semitone at a time.
  Chord symbols *and* the selected key move together.
- **Save and load** songs as `.chordic.json` files.
  - In Chrome/Edge (served over `localhost` or HTTPS) you can pick a folder
    once and get a proper library — songs save and load directly from disk.
  - In Firefox/Safari (or when opening the file from disk), Chordic Lite
    falls back to downloading and uploading individual files.
- **Print to PDF** — the UI is hidden automatically in the print stylesheet.
- **Autosaves** your current song to `localStorage` so nothing is lost on
  a refresh.

---

## Getting started

1. Download `chordic-lite.html`.
2. Open it in a modern browser. That's it.

If you want to use the folder library (Chrome / Edge only):

```bash
# from the folder containing chordic-lite.html
python3 -m http.server 8000
# then open http://localhost:8000/chordic-lite.html
```
