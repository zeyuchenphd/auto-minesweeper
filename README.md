# Auto Minesweeper

A faithful recreation of classic Windows 95 Minesweeper — playable in your browser with smart assists that make the game more enjoyable without taking away the challenge.

**[Play Now](https://zeyuchenphd.github.io/auto-minesweeper/)**

## Features

### Classic Minesweeper
- Pixel-perfect Win95 aesthetic — 3D beveled cells, sunken panels, blue title bar
- 7-segment LED displays (DSEG7 font) with ghost segments for mine counter and timer
- SVG-rendered mines, flags, and number colors matching the original
- Three difficulty modes:

| Mode         | Grid   | Mines |
|--------------|--------|-------|
| Beginner     | 9 × 9  | 10    |
| Intermediate | 16 × 16 | 40    |
| Expert       | 16 × 30 | 99    |

### Smart Assists

#### Spacebar Controls
- **Hover over an unrevealed cell + Space** — toggle flag (same as right-click)
- **Hover over a revealed number + Space** — recursive chord: reveals adjacent cells if flag count matches, then automatically chains to any newly revealed numbers that are also satisfied

#### Auto-Chord on Flag
When you place a flag, the game automatically checks all adjacent numbers. If any number's flag count now matches its value, it reveals the remaining neighbors — and chains recursively.

#### Auto Solve Mode (Optional)
Toggle via **Game > Auto Solve** in the menu (off by default). When enabled:
- After every action, the game scans all visible numbers
- If a number's remaining hidden neighbors exactly equals its remaining mine count, those cells are **automatically flagged**
- Satisfied numbers are then **automatically chorded**
- This repeats until no more logical deductions can be made

This lets you focus on the tricky decisions — the game handles the obvious ones.

### Controls

| Action | Input |
|--------|-------|
| Reveal a cell | Left-click |
| Flag / unflag | Right-click or Ctrl+click |
| Place ? mark | Right-click a flag (when Marks enabled) |
| Chord (reveal neighbors) | Middle-click or Left+Right click |
| Recursive chord | Spacebar on a number |
| Flag cell | Spacebar on unrevealed cell |
| New game | F2 or click the smiley face |

## Tech

Single self-contained HTML file. No dependencies, no build step, no frameworks — just HTML, CSS, and vanilla JavaScript.

- CSS Grid layout for the minefield
- Inline SVG for mine and flag graphics
- [DSEG7 Classic](https://github.com/keshikan/DSEG) font for 7-segment LCD displays
- BFS-based recursive chord and auto-solve algorithms

## License

MIT
