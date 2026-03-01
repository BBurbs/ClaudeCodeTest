# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the Project

Open `tictactoe.html` directly in a browser — no build step, server, or dependencies required.

```bash
open tictactoe.html
```

## Architecture

Single self-contained HTML file (`tictactoe.html`) with all CSS and JS inlined. No frameworks, no external dependencies.

**Game logic (inline `<script>`):**
- `board` — flat 9-element array (`null | 'X' | 'O'`) representing the grid
- `WINS` — static array of the 8 winning index triplets
- `checkWinner()` — iterates `WINS`; returns `{ winner, line }` on win, `{ winner: null, line: [] }` on draw, `null` if game still in progress
- `score` — persists across `init()` calls (`{ X, O, D }`)
- `init()` — resets board/DOM state without resetting score

**DOM structure:** 9 `.cell` divs with `data-i` attributes (0–8) map 1:1 to `board[]` indices. CSS classes `x`, `o`, `taken`, and `win` are added dynamically.

## Commit and Push Policy

After completing any meaningful unit of work, commit and push to GitHub immediately. Do not batch unrelated changes into a single commit. The goal is that no work is ever lost and the repo history reflects each logical step taken.

```bash
git add <files>
git commit -m "<type>: <description>"
git push
```

**Commit types:**
- `feat:` new feature
- `fix:` bug fix
- `style:` visual/UI changes
- `refactor:` code restructure with no behavior change
- `docs:` documentation updates

Remote: `origin/main` → https://github.com/BBurbs/ClaudeCodeTest
