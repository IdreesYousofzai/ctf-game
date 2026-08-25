# NEXUS // Breach File

A browser-based hacking puzzle game built for IT students. Investigate a fictional corporation, recover 22 pieces of evidence, and put the story together — no installs, no backend, just a single HTML file.

**[▶ Play it live](#getting-started)** · Built with vanilla HTML, CSS, and JavaScript.

---

## What is this?

You've been anonymously recruited to investigate a corporation called NEXUS. Twenty-two pieces of evidence are scattered across a single web page, each protected by a different technique. Find them, decode them, and submit each one in the format `NEXUS{...}` to unlock the next fragment of the story.

There are no numbered "levels" — every case file is open from the start, and you can tackle them in any order. They're arranged roughly from easiest to hardest, but the game won't stop you from jumping ahead (or getting stuck).

## Puzzle types

The 22 cases mix four categories of challenge, so no single skill will get you through the whole thing:

- **Source & DevTools inspection** — reading the DOM, hunting through decoys, spotting things browsers render but don't display
- **Ciphers & encodings** — classic and layered encoding schemes, from beginner-friendly to genuinely tricky
- **Logic & deduction** — riddles, number patterns, and a lie-detection puzzle with witness statements
- **A working fake terminal** — a simulated shell with its own filesystem, supporting commands like `ls`, `cd`, `cat`, and `grep`

Every case includes two optional hints if you get stuck, so it's meant to teach as much as it tests.

## Features

- 22 handcrafted cases with an ongoing mystery that pays off once you clear the board
- A built-in **Analyst Toolkit** — a slide-out panel with working Base64, hex, ROT13, Caesar cipher, binary, Morse code, and XOR (single-key and repeating-key) converters, so you can experiment freely
- Flags are checked client-side via SHA-256 hashing — solutions aren't sitting in plain text in the page source
- **Resume codes**: since there's no backend or browser storage involved, finishing the game in one sitting isn't required — generate a short code to save your progress and pick up where you left off later
- Fully self-contained: one HTML file, no build step, no dependencies to install

## Getting started

No setup required.

1. Download `nexus-breach-file.html` (or clone this repo)
2. Open the file directly in any modern browser (Chrome, Firefox, Edge, Safari)
3. Click **Begin Investigation** and start looking for the first case

If you're hosting it (GitHub Pages, Netlify, etc.), just point your host at `nexus-breach-file.html` — it works as a static site with zero configuration.

```bash
git clone <this-repo-url>
cd <repo-folder>
open nexus-breach-file.html   # or just double-click it
```

## How to play

- Every case has a **briefing** (the puzzle) and a **flag input** (the answer, formatted `NEXUS{your_answer}`)
- Some cases want you to read the page's underlying structure — right-click and choose **Inspect**, or press F12, to open your browser's Developer Tools
- Some cases want you to open the **Console** tab in Developer Tools and read what's printed there
- The **Toolkit** button (top right) gives you decoding tools for common ciphers — you'll need to figure out which tool fits which case
- Stuck? Each case has two hints you can reveal — the first nudges you in the right direction, the second explains the technique outright
- Your progress lives in the page's memory only. Use the **Resume Code** button before closing the tab if you want to continue later

No spoilers here — that's genuinely the whole game. Good luck.

## Tech stack

- Plain HTML5 / CSS3 / JavaScript (ES2020+) — no frameworks, no build tools
- `crypto.subtle` (Web Crypto API) for client-side SHA-256 flag verification
- Google Fonts (IBM Plex Mono, Spectral) loaded via CDN

## Browser support

Works in any modern browser with support for the Web Crypto API (`crypto.subtle`) — all current versions of Chrome, Firefox, Edge, and Safari. Requires JavaScript to be enabled.

## Project structure

```
.
└── nexus-breach-file.html   # the entire game — HTML, CSS, and JS in one file
```

## Contributing / feedback

This was built as a personal/portfolio project. Bug reports and suggestions are welcome via issues — please avoid posting flag answers or spoilers in public issues or PRs.

## License

MIT — feel free to fork it, learn from it, or build your own case files on top of it.
