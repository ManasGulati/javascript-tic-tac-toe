# Tic Tac Toe

**A two-player browser game built with zero dependencies, pure HTML, CSS, and JavaScript.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen?style=flat-square)
![Status](https://img.shields.io/badge/status-complete-success?style=flat-square)


---

## Table of Contents

- [Overview](#overview)
- [Tools and Technologies](#tools-and-technologies)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Key Features](#key-features)
- [Output](#output)
- [How to Run](#how-to-run)
- [Result and Conclusion](#result-and-conclusion)
- [Future Work](#future-work)
- [Author and Contact](#author-and-contact)

---

## Overview

This is a classic Tic Tac Toe game that runs entirely in the browser, no server, no framework, no build step. Two players share the same device, taking turns clicking cells on a 3×3 grid. The game automatically detects wins across all 8 possible lines and highlights the winning combination, or announces a draw when the board fills up. A **New Game** button resets everything without reloading the page.

The project was built to practise core front-end fundamentals: semantic HTML structure, CSS Grid layout, glassmorphism styling, and clean event-driven JavaScript.

---

## Tools and Technologies

| Layer      | Technology | Purpose |
|------------|-----------|---------|
| Structure  | HTML5     | Semantic markup, 3×3 grid via `<div>` elements |
| Styling    | CSS3      | CSS Grid, glassmorphism cards, win highlight, responsive layout |
| Logic      | JavaScript (ES6) | Game state, event listeners, win/draw detection |
| Font       | Google Fonts – Poppins | Clean, modern sans-serif (CDN, optional) |
| Assets     | JPG       | Abstract gradient backdrop image |

No npm, no bundler, no framework, just the native browser stack.

---

## Project Structure

```
Tic-Tac-Toe/
├── src/
│   ├── index.html              # Entry point — board markup and script links
│   ├── style.css               # Full game styling (grid, glassmorphism, win states)
│   └── script.js               # All game logic (init, click handling, win detection)
├── assets/
│   └── background.jpg          # Full-viewport gradient background image
├── README.md                   # This file
└── dependencies.txt            # Dependency manifest (zero external packages)
```

---

## How It Works

The game logic lives entirely in `script.js` across four focused functions:

**`initialize()`**
Resets the `gameGrid` array to nine empty strings, clears all cell text and classes, restores pointer events, hides the New Game button, and sets Player X as the current turn.

**`handleClick(index)`**
Fires when a cell is clicked. Guards against overwriting with an empty-cell check, writes the current player's mark (`X` or `O`) to both the DOM and the `gameGrid` array, then chains `swapTurn()` and `checkGameOver()`.

**`swapTurn()`**
Toggles `currentPlayer` between `"X"` and `"O"` and updates the status display at the top of the board.

**`checkGameOver()`**
Iterates through all 8 winning position sets. If three identical non-empty values are found, it applies a `.win` class to those cells (green highlight), disables all clicks, and announces the winner. If all 9 cells are filled with no match, it declares a draw.

### Win Conditions

```
Rows:       [0,1,2]  [3,4,5]  [6,7,8]
Columns:    [0,3,6]  [1,4,7]  [2,5,8]
Diagonals:  [0,4,8]  [2,4,6]
```

---

## Key Features

- **Zero dependencies** : runs offline, no install needed
- **Win detection** : checks all 8 lines after every move
- **Draw detection** : triggers when all 9 cells are filled with no winner
- **Visual feedback** : winning cells highlighted in translucent green
- **No-reload reset** : New Game button reinitialises state in place
- **Glassmorphism UI** : frosted-glass card and status bar over a gradient backdrop

---

## Output

The `output/` folder contains `game_states_dashboard.html`, open it in any browser to see:

- All four game states side by side (initial, mid-game, X wins, draw)
- All 8 win conditions illustrated on mini boards
- The full game logic flow summarised visually

A PDF project report covering architecture, implementation details, and future enhancements is in `report/project_report.pdf`.

---

## How to Run

**Option 1 — Direct open (simplest)**

```bash
# Clone the repo
git clone https://github.com/<your-username>/Tic-Tac-Toe.git
cd Tic-Tac-Toe

# Open the game
open src/index.html        # macOS
xdg-open src/index.html    # Linux
start src/index.html       # Windows
```

Then just open `src/index.html` in your browser, no server or install required.

**Option 2 — Local dev server (optional, for live reload)**

```bash
# Using Python
python3 -m http.server 3000
# then visit http://localhost:3000/src/

# Or using Node's http-server
npx http-server src/ -p 3000
```

---

## Result and Conclusion

The game works correctly across all tested browsers (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+). Win and draw detection are reliable across all 8 possible line combinations, and the board resets cleanly on every new game without a page reload.

The project demonstrates that interactive browser applications do not require a framework. Keeping the stack simple, one HTML file, one stylesheet, one script, produces code that is easy to read, easy to debug, and easy to extend.

---

## Future Work

- **AI opponent** using the Minimax algorithm for single-player mode
- **Score tracking** across rounds with session persistence
- **Animations** for move placement and win/draw announcements
- **Sound effects** for player actions and game outcomes
- **Mobile-first redesign** with touch-optimised tap targets
- **Larger board variants** (4×4, 5×5) with configurable win length

---

## Author and Contact

**Developed by:** Manas Gulati  
**Email:** manasgulati222@gmail.com  
**LinkedIn:** [linkedin.com/in/manasgulatiryu](https://linkedin.com/in/manasgulatiryu)
**GitHub:** [github.com/ManasGulati](https://github.com/ManasGulati) 

Made with vanilla HTML, CSS, and JavaScript.

Feel free to fork, open an issue, or reach out if you have suggestions.

> *"The best code is the code you don't need to install."*
