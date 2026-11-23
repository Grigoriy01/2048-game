# 2048 Game

A classic browser implementation of the **2048** sliding tile puzzle game built with **Vanilla JavaScript (ES6+)**, **HTML5**, and **modular SCSS**.

🔗 **[Live Demo](https://grigoriy01.github.io/2048-game/)**

---

## Features

- **Clean OOP Architecture:** Game logic (`Game` class with private fields and encapsulated state) is strictly separated from DOM manipulation (`GameView`).
- **Desktop & Mobile Controls:** Full keyboard navigation (Arrow keys) and responsive touch swipe detection with scroll lock.
- **Persistent High Score:** Automatically saves and restores the best score using `localStorage`.
- **Multi-Language Rules:** Built-in interactive rules modal available in **English**, **German**, **Spanish**, and **Russian**.
- **Smooth Animations:** Keyframe animations for tile merges, 2048 win state, and idle start hints.

---

## Tech Stack

- **JavaScript (ES6+):** Classes, private fields/methods, `structuredClone`, `localStorage`, Touch Events API.
- **SCSS (Sass):** Modular BEM-like architecture (`_vars`, `_animations`, `_game-field`, `_header`, etc.).
- **HTML5:** Semantic structure and custom favicon manifest.
- **Parcel:** Zero-config bundler for development and production builds.

---

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://grigoriy01.github.io/2048-game/](https://grigoriy01.github.io/2048-game/).git
