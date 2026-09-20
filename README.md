# 🎵 Chordic Lite

**[▶ Try it live in your browser](https://zebaztian2525.github.io/chordic-lite/)** — no installation required.

A lightweight, browser-based chord editor for songwriters, church musicians,
and anyone who wants to place chords exactly where they belong — right above
the syllable that carries the beat.

Chordic Lite runs entirely in your browser. No server, no install, no account.
Just open it and start typing.

> **Status:** early prototype. Feedback and pull requests are very welcome.

---

## Features

- **Write lyrics, place chords above individual letters.** Every character in
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

**Quickest:** open the [live demo](https://zebaztian2525.github.io/chordic-lite/)
in Chrome, Edge, or Firefox.

**Locally:** download `index.html` (or `chordic-lite.html`) and open it in any
modern browser.

The folder library (Chrome/Edge only) requires a secure context. The live demo
works out of the box because GitHub Pages serves over HTTPS. If you run the
file locally, start a simple server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/index.html
