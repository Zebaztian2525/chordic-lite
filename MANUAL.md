## Manual

A slightly longer walkthrough of what Chordic Lite can do and how the
pieces fit together.

### The layout

- **Left sidebar** (top on small screens): the key, the diatonic chord
  palette, and the chord builder. On tablets and phones this whole panel
  can be collapsed using the round button in its top-right corner.
- **Center**: the song itself. Lyrics with chords above them, and — when
  a ChordPro file provides one — an intro chord sequence shown to the
  right of the title.
- **Right column** (below on small screens): the lyrics editor and the
  folder library.

### Placing a chord

There are three ways to place a chord on a letter:

1. **Drag a chip** from the palette or builder onto the letter.
2. **Click a chip** while a letter is already selected.
3. **Build a chord and press "Add"** while a letter is selected.

Each letter in the lyrics is a drop target. You can place several chords
above the same word — one per stressed syllable — or place a chord in the
gap between two words if that is where the change happens.

### Moving and removing chords

- **Drag** a placed chord to move it to another letter.
- **Ctrl+click** (⌘-click on macOS) to remove it.
- On a **touch device**, tapping a placed chord shows a small red × to
  remove it.

### Selecting a letter

Click a letter to select it. The selection stays where you put it, so you
can add several chords to the same letter one at a time. It is cleared
automatically when you edit the lyrics, import a file, load a song, or
press Escape.

The selection is not stored between sessions — reloading the page starts
with no selection.

### Chord positions follow your edits

When you change the lyrics, Chordic Lite compares the old and new text
and re-maps every chord. Chords before the edit stay where they are;
chords after the edit shift along with the text. Chords that fall inside
the changed region are removed, since there is no longer a sensible
position for them.

Insert a new line and chords on the following lines move down one step,
still above the right letters.

### Undo and redo

The toolbar has ↶ and ↷ buttons, or use `Ctrl+Z` / `Ctrl+Y` (or
`Cmd+Z` / `Shift+Cmd+Z` on macOS) when the focus is not in a text field.
Up to 50 steps are remembered.

Every meaningful action creates a step: placing a chord, moving it,
removing it, transposing, importing, loading, and applying edits to the
lyrics.

### Keys and transposition

Click a piano key to set the key. The diatonic palette updates
immediately.

Use `−½` / `+½` to transpose the whole song by one semitone. Chord
symbols *and* the selected key move together, so the relationship between
them stays intact.

### Building custom chords

The builder panel lets you combine a root note, a chord type (maj, m,
7, maj7, sus4, dim…), and a slash bass note. The preview chip shows the
result. Drag it onto a letter, or press "Add" while a letter is selected.

### The library

In Chromium-based browsers (Chrome, Edge, Vivaldi, Brave, Opera, Deepin
Browser…) you can pick a folder and get a proper library. Songs save and
load directly from disk. In Firefox and Safari, Chordic Lite falls back
to downloading and uploading individual files.

Either way, songs are stored as `.chordic.json` for the native format or
as `.pro` for ChordPro import and export.

### Importing and exporting

- **📥 ChordPro** imports a ChordPro file. Leading chord-only lines are
  turned into an intro block in the song header; the rest becomes lyrics
  with chords.
- **📤 ChordPro** exports the current song in ChordPro format, including
  title, artist, key, intro, and lyrics.
- **🖨️ PDF** opens the browser's print dialog. The UI hides itself in
  the print stylesheet, leaving only the song on the page.

### Printing

The print output is designed for A4. Only the song is printed — the
sidebar, the editor, the library, and the toolbar are hidden
automatically. Chords and lyrics keep their exact alignment, and any
selected-letter highlighting is removed.

### Known behaviour differences

A few small things behave differently depending on the device. None of
them affect the result of your work, but they are worth knowing about.

**Selection after pressing "Add".**
On desktop, the highlighted letter stays selected after you place a
chord with the "Add" button. On some touch devices, the selection is
cleared instead. Both behaviours are acceptable — on a tablet the
cleared selection can act as a small "done" signal, and on desktop the
kept selection lets you place several chords on the same letter in a
row.

If you want exactly the same behaviour everywhere, the relevant line in
the code is `state.selectedChar = null;` inside the `addChord`
function. Removing it makes the selection persist; keeping it makes the
selection clear.

**Folder library.**
Only available in Chromium-based browsers (Chrome, Edge, Vivaldi,
Brave, Opera, Deepin Browser…) and only when the page is served over
HTTPS or `localhost`. In Firefox and Safari — or when opening the file
directly from disk in some browsers — the library falls back to
downloading and uploading individual files.

**Autosave across languages.**
The English and Swedish versions keep separate autosave states. A song
you started in one language is not automatically visible in the other.
Use the library, or export and import, to move songs between them.

**Chord placement near the left edge.**
When dragging a chord with a pen or finger, the drop position is
calculated from the point where you release. If you are aiming for the
first letter of a line, Chordic Lite snaps to the nearest letter within
a small radius, so you do not have to hit it exactly.

### Language

Click **🇸🇪 SV** in the top-right corner to switch to the Swedish
version. Click **🇬🇧 EN** to come back.

The two versions keep separate autosave states, so a song you started in
one language is not automatically visible in the other. Use the library
or export/import to move songs between them.
