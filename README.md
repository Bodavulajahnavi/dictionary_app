# The Daily Lexicon — Dictionary App

A simple, single-file dictionary web app styled like an old library card catalog. Search any word to see its pronunciation, definitions, examples, and synonyms.

Two versions are included:

| File | Data source | Where it works |
|---|---|---|
| `dictionary-local.html` | [Free Dictionary API](https://dictionaryapi.dev/) (real definitions + audio pronunciation) | Works in a regular browser, but needs to be run through a local server (see below) |

If you want real dictionary data and actual audio pronunciations, use `dictionary-local.html` and follow the setup steps below.

---

## Running `dictionary-local.html`

Browsers block this file's network requests when opened directly by double-clicking (`file://...`), so it needs to be served over a local web address instead. This takes about a minute.

### Windows

1. Open **File Explorer** and go to the folder where you saved `dictionary-local.html` (likely **Downloads**).
2. Click on empty space inside that folder window (make sure nothing is selected).
3. Hold **Shift** and **right-click** → choose **"Open PowerShell window here"** or **"Open in Terminal"**.
4. Check Python is installed by typing:
   ```
   python --version
   ```
   If this errors, install Python from [python.org/downloads](https://python.org/downloads) — during setup, check **"Add python.exe to PATH"**. Then reopen the terminal (repeat step 3).
5. Start the server:
   ```
   python -m http.server 8000
   ```
6. Open your browser and go to:
   ```
   http://localhost:8000/dictionary-local.html
   ```
7. When finished, go back to the terminal and press **Ctrl + C** to stop the server.

### Mac

1. Open **Finder** and go to the folder where you saved `dictionary-local.html` (likely **Downloads**).
2. Open **Terminal** (press `Cmd + Space`, type "Terminal", press Enter).
3. Type `cd ` (with a trailing space), then drag the folder from Finder into the Terminal window to auto-fill the path. Press Enter.
4. Start the server:
   ```
   python3 -m http.server 8000
   ```
5. Open your browser and go to:
   ```
   http://localhost:8000/dictionary-local.html
   ```
6. When finished, go back to the terminal and press **Ctrl + C** to stop the server.

### Chromebook / Linux

1. Open a terminal and `cd` into the folder containing the file, e.g.:
   ```
   cd ~/Downloads
   ```
2. Start the server:
   ```
   python3 -m http.server 8000
   ```
3. Open your browser and go to:
   ```
   http://localhost:8000/dictionary-local.html
   ```
4. When finished, press **Ctrl + C** in the terminal to stop the server.

---

## Features

- Search any word for definitions, part of speech, and example sentences
- Numbered senses grouped by part of speech
- Synonym chips — click one to look it up instantly
- "Surprise me" button for a random word
- Recently searched words shown as quick-access chips
- Alphabet tab strip on the side that highlights the current word's starting letter
- (`dictionary-local.html` only) Pronunciation audio playback, when available

## Notes

- `dictionary-local.html` pulls from the free, open [Dictionary API](https://dictionaryapi.dev/), which sources from Wiktionary. Not every word will have an entry, and very obscure or informal words may return "no entry found."
- The file is self-contained single HTML file — no installation or build step required beyond the local server step above.
