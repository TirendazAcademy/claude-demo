# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a collection of standalone browser games — each game lives in a single self-contained HTML file. No build tools, no dependencies, no package managers. Open any `.html` file directly in a browser to run it.

## Games

| File | Description |
|------|-------------|
| `tic-tac-toe.html` | 2-player Tic-Tac-Toe with scoreboard, Turkish UI |
| `shooter.html` | Top-down arena shooter with waves, enemy types, particle FX, CRT overlay |

## Architecture pattern

Each game is a **single HTML file** containing inline `<style>` and `<script>`. The games are structured using ES6 classes:

- `shooter.html` uses a class-per-entity pattern: `InputHandler`, `Particle`, `ParticleSystem`, `Bullet`, `Player`, enemy classes (`Grunt`, `Runner`, `Tank`), and a `Game` controller that runs the `requestAnimationFrame` loop with delta-time (`dt`) based updates.
- `tic-tac-toe.html` uses plain procedural JS with module-level state.

When adding a new game, follow the same single-file pattern. Keep all CSS, HTML, and JS in one file.

## Language

UI strings are in **Turkish** (`lang="tr"`). Keep new games consistent with this convention.

## Git workflow

Commit and push frequently while working — after each meaningful change (new feature, bug fix, new file). Never let significant work sit uncommitted.

Commit message format:
```
<type>: <short description>
```

Types: `feat`, `fix`, `refactor`, `style`, `docs`

Examples:
- `feat: add snake game with high score tracking`
- `fix: correct collision detection in shooter`
- `docs: update CLAUDE.md with new game entry`

After committing, always push:
```bash
git push origin main
```
