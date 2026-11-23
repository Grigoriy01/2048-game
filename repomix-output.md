This file is a merged representation of a subset of the codebase, containing specifically included files, combined into a single document by Repomix.

<file_summary>
This section contains a summary of this file.

<purpose>
This file contains a packed representation of a subset of the repository's contents that is considered the most important context.
It is designed to be easily consumable by AI systems for analysis, code review,
or other automated processes.
</purpose>

<file_format>
The content is organized as follows:
1. This summary section
2. Repository information
3. Directory structure
4. Repository files (if enabled)
5. Multiple file entries, each consisting of:
  - File path as an attribute
  - Full contents of the file
</file_format>

<usage_guidelines>
- This file should be treated as read-only. Any changes should be made to the
  original repository files, not this packed version.
- When processing this file, use the file path to distinguish
  between different files in the repository.
- Be aware that this file may contain sensitive information. Handle it with
  the same level of security as you would the original repository.
</usage_guidelines>

<notes>
- Some files may have been excluded based on .gitignore rules and Repomix's configuration
- Binary files are not included in this packed representation. Please refer to the Repository Structure section for a complete list of file paths, including binary files
- Only files matching these patterns are included: src/**/*
- Files matching patterns in .gitignore are excluded
- Files matching default ignore patterns are excluded
- Files are sorted by Git change count (files with more changes are at the bottom)
</notes>

</file_summary>

<directory_structure>
src/
  images/
    favicon_io/
      about.txt
      android-chrome-192x192.png
      android-chrome-512x512.png
      apple-touch-icon.png
      favicon-16x16.png
      favicon-32x32.png
      favicon.ico
      site.webmanifest
    .gitkeep
    reference.png
  modules/
    Game.class.js
  scripts/
    main.js
  styles/
    blocks/
      _animations.scss
      _container.scss
      _counter.scss
      _game-field.scss
      _header-controls.scss
      _header.scss
      _language.scss
      _massege.scss
      _page.scss
      _rules.scss
    utils/
      _extends.scss
      _vars.scss
    _typography.scss
    _utils.scss
    main-test.scss
    main.scss
  index.html
</directory_structure>

<files>
This section contains the contents of the repository's files.

<file path="src/images/favicon_io/about.txt">
This favicon was generated using the following font:

- Font Title: Archivo Black
- Font Author: undefined
- Font Source: https://fonts.gstatic.com/s/archivoblack/v22/HTxqL289NzCGg4MzN6KJ7eW6OYuP_x7yx3A.ttf
- Font License: undefined)
</file>

<file path="src/images/.gitkeep">

</file>

<file path="src/styles/blocks/_animations.scss">
.vibrate-element {
  animation-name: vibration;
  animation-duration: 0.3s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

.scale-element {
  animation-name: scale-cells;
  animation-duration: 0.3s;
  animation-timing-function: linear;
  animation-iteration-count: 1;
}

@keyframes vibration {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(3deg);
  }
  50% {
    transform: rotate(0deg);
  }
  75% {
    transform: rotate(-3deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

@keyframes scale-cells {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }

  100% {
    transform: scale(1);
  }
}
</file>

<file path="src/styles/blocks/_container.scss">
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 350px;
}
</file>

<file path="src/styles/blocks/_language.scss">
.language-buttons {
  display: flex;
  justify-content: space-evenly;
}

.btn-language {
  cursor: pointer;

  width: 50px;
  border: none;
  border-radius: 5px;

  font-family: sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #f2bd1e;

  transition: 0.3s;

  &:hover {
    transform: scale(1.1);
  }

  &:active {
    transform: scale(0.9);
  }

  &--is-active {
    background-color: #484747;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
  }
}
</file>

<file path="src/styles/utils/_extends.scss">
// empty
</file>

<file path="src/styles/_typography.scss">
// empty
</file>

<file path="src/styles/_utils.scss">
@import 'utils/vars';
@import 'utils/extends';
</file>

<file path="src/styles/main-test.scss">
@import './typography';
@import './utils';
@import './blocks/page';
@import './blocks/container';
@import './blocks/header';
@import './blocks/header-controls';
@import './blocks/game-field';
@import './blocks/animations';
@import './blocks/massege';
@import './blocks/counter';
@import './blocks/language';
@import './blocks/rules';
</file>

<file path="src/images/favicon_io/site.webmanifest">
{
  "name": "",
  "short_name": "",
  "icons": [
    {
      "src": "./android-chrome-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "./android-chrome-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "theme_color": "#ffffff",
  "background_color": "#ffffff",
  "display": "standalone"
}
</file>

<file path="src/modules/Game.class.js">
'use strict';

/**
 * This class represents the game.
 * Now it has a basic structure, that is needed for testing.
 * Feel free to add more props and methods if needed.
 */
class Game {
  /**
   * Creates a new game instance.
   *
   * @param {number[][]} initialState
   * The initial state of the board.
   * @default
   * [[0, 0, 0, 0],
   *  [0, 0, 0, 0],
   *  [0, 0, 0, 0],
   *  [0, 0, 0, 0]]
   *
   * If passed, the board will be initialized with the provided
   * initial state.
   */
  static statuses = {
    idle: 'idle',
    playing: 'playing',
    win: 'win',
    lose: 'lose',
  };

  #size;
  #mergedCellIndex = [];
  // #localValue = localStorage.getItem('best-score');

  #bestScore;

  #score = 0;
  #initialBoard;
  #status;

  constructor(
    initialState = [
      [0, 0, 0, 0],
      [0, 0, 0, 0],
      [0, 0, 0, 0],
      [0, 0, 0, 0],
    ],
  ) {
    // eslint-disable-next-line no-console
    console.log(initialState);
    this.#initialBoard = structuredClone(initialState);
    this.board = structuredClone(this.#initialBoard); // tiefe clonen
    this.#size = this.board.length;
    this.#status = Game.statuses.idle;

    const localValue = localStorage.getItem('best-score');

    this.#bestScore =
      this.localValue === null ? this.#score : Number(localValue);
  }
  // #region moves
  moveLeft() {
    // reset
    this.#mergedCellIndex = [];

    // guard from pushing button
    if (
      this.#status === Game.statuses.lose ||
      this.#status === Game.statuses.win
    ) {
      return;
    }

    let canMove = false;

    this.board = this.board.map((row, rowIndex) => {
      const { newValidRow, isChange, targetIndex } = this.#shiftDirection(row);

      canMove ||= isChange;

      targetIndex.forEach((el) => {
        const globalCellIndex = rowIndex * 4 + el;

        this.#mergedCellIndex.push(globalCellIndex);
      });

      return newValidRow;
    });

    // wenn keine änderung werden, keine neuer Zehlen
    if (!canMove) {
      return;
    }

    this.#generateRandomPositions();
    this.#checkGameStatus();
  }

  moveRight() {
    // reset
    this.#mergedCellIndex = [];

    // guard from pushing button
    if (
      this.#status === Game.statuses.lose ||
      this.#status === Game.statuses.win
    ) {
      return;
    }

    let canMove = false;

    // A double reverse is required for correct display.
    this.board = this.board.map((row, rowIndex) => {
      const { newValidRow, isChange, targetIndex } = this.#shiftDirection(
        [...row].reverse(),
      );

      canMove ||= isChange;

      const reverseTargetIndex = targetIndex.map((el) => 3 - el);

      reverseTargetIndex.forEach((el) => {
        const globalCellIndex = rowIndex * 4 + el;

        this.#mergedCellIndex.push(globalCellIndex);
      });

      return newValidRow.reverse();
    });

    if (!canMove) {
      return;
    }

    this.#generateRandomPositions();
    this.#checkGameStatus();
  }

  moveUp() {
    // reset
    this.#mergedCellIndex = [];

    // guard from pushing button
    if (
      this.#status === Game.statuses.lose ||
      this.#status === Game.statuses.win
    ) {
      return;
    }

    let canMove = false;

    // I form a column, taking one cell from each row.
    for (let x = 0; x < this.#size; x++) {
      const tempRow = [];

      for (let y = 0; y < this.#size; y++) {
        tempRow.push(this.board[y][x]);
      }

      const { newValidRow, isChange, targetIndex } =
        this.#shiftDirection(tempRow);

      canMove ||= isChange;

      for (let y = 0; y < this.#size; y++) {
        this.board[y][x] = newValidRow[y];
      }

      targetIndex.forEach((el) => {
        const globalCellIndex = el * 4 + x;

        this.#mergedCellIndex.push(globalCellIndex);
      });
    }

    if (!canMove) {
      return;
    }

    this.#generateRandomPositions();
    this.#checkGameStatus();
  }

  moveDown() {
    // reset
    this.#mergedCellIndex = [];

    // guard from pushing button
    if (
      this.#status === Game.statuses.lose ||
      this.#status === Game.statuses.win
    ) {
      return;
    }

    let canMove = false;

    // I form a column, taking one cell from each row.
    for (let x = 0; x < this.#size; x++) {
      const tempRow = [];

      for (let y = 0; y < this.#size; y++) {
        tempRow.push(this.board[y][x]);
      }

      // A double reverse is required for correct display.
      const { newValidRow, isChange, targetIndex } = this.#shiftDirection(
        [...tempRow].reverse(),
      );

      newValidRow.reverse();
      canMove ||= isChange;

      for (let y = 0; y < this.#size; y++) {
        this.board[y][x] = newValidRow[y];
      }

      const reverseTargetIndex = targetIndex.map((el) => 3 - el);

      reverseTargetIndex.forEach((el) => {
        const globalCellIndex = el * 4 + x;

        this.#mergedCellIndex.push(globalCellIndex);
      });
    }

    if (!canMove) {
      return;
    }

    this.#generateRandomPositions();
    this.#checkGameStatus();
  }
  // #endregion moves

  /**
   * @returns {number}
   */
  getScore() {
    return this.#score;
  }

  getBestScore() {
    return this.#bestScore;
  }

  /**
   * @returns {number[][]}
   */
  getState() {
    return {
      score: this.getScore(),
      bestScore: this.getBestScore(),
      statusGame: this.getStatus(),
      board: this.board,
      targetCellIndex: this.#mergedCellIndex,
    };
  }

  /**
   * Returns the current game status.
   *
   * @returns {string} One of: 'idle', 'playing', 'win', 'lose'
   *
   * `idle` - the game has not started yet (the initial state);
   * `playing` - the game is in progress;
   * `win` - the game is won;
   * `lose` - the game is lost
   */
  getStatus() {
    return this.#status;
  }

  /**
   * Starts the game.
   */
  start() {
    this.#score = 0;
    this.#generateRandomPositions();
    this.#generateRandomPositions();
    this.#status = Game.statuses.playing;
  }

  /**
   * Resets the game.
   */
  restart() {
    this.#score = 0;
    this.board = structuredClone(this.#initialBoard);
    this.#generateRandomPositions();
    this.#generateRandomPositions();
    this.#status = Game.statuses.playing;
  }

  // Add your own methods here

  // #region function-tools
  // update the Bestscore and localStorage
  #updateBestScore() {
    if (this.#bestScore < this.#score) {
      this.#bestScore = this.#score;
      localStorage.setItem('best-score', this.#bestScore);
    }
  }
  // --> shift of values in the row and addition of values
  #shiftDirection(row) {
    // Clear the array of zeros to work only with active numbers
    const nonZeroValues = row.filter((el) => el > 0);
    const updatedArray = [];
    const targetIndex = [];

    for (let i = 0; i < nonZeroValues.length; i++) {
      const currNum = nonZeroValues[i];

      // is last number
      if (i === nonZeroValues.length - 1) {
        updatedArray.push(currNum);
        break;
      }

      const nextNum = nonZeroValues[i + 1];

      if (currNum === nextNum) {
        const sum = currNum + nextNum;

        updatedArray.push(sum);
        targetIndex.push(updatedArray.length - 1);
        this.#score += sum;
        this.#updateBestScore();
        i++;
      } else {
        updatedArray.push(currNum);
      }
    }

    const newValidRow = [];

    for (let i = 0; i < this.#size; i++) {
      const curr = updatedArray[i];

      newValidRow.push(typeof curr === 'number' ? curr : 0);
    }

    const beforeRow = row.join(',');
    const afterRow = newValidRow.join(',');
    const isChange = beforeRow !== afterRow;

    return {
      newValidRow,
      isChange,
      targetIndex,
    };
  }
  // --> random position of Numbers on the board
  #generateRandomPositions() {
    const cellPosition = {
      x: [],
      y: [],
    };

    this.board.forEach((row, rowIndex) => {
      row.forEach((col, colIndex) => {
        if (col === 0) {
          cellPosition.y.push(colIndex);
          cellPosition.x.push(rowIndex);
        }
      });
    });

    // var coordinate for position of Number on the board
    const randomIndex = Math.floor(Math.random() * cellPosition.x.length);
    const coorX = cellPosition.x[randomIndex];
    const coorY = cellPosition.y[randomIndex];

    this.board[coorX][coorY] = this.#getRandomNumbers();
  }

  // --> randoms numbers 2 or (4 - 10% chance)
  #getRandomNumbers() {
    if (this.#status === Game.statuses.idle) {
      return 2;
    } else {
      return Math.random() > 0.1 ? 2 : 4;
    }
  }

  // --> scaning board and change the status-game
  #checkGameStatus() {
    let hasEmptyCells = false;
    let hasPossibleMerges = false;

    for (let y = 0; y < this.#size; y++) {
      for (let x = 0; x < this.#size; x++) {
        const bottomNeighbor =
          y > this.#size - 2 ? undefined : this.board[y + 1][x];
        const currentValue = this.board[y][x];
        const rightNeighbor =
          x > this.#size - 2 ? undefined : this.board[y][x + 1];

        if (currentValue === 2048) {
          this.#status = Game.statuses.win;

          return;
        }

        if (currentValue === 0) {
          hasEmptyCells = true;
        }

        if (currentValue === rightNeighbor || currentValue === bottomNeighbor) {
          hasPossibleMerges = true;
        }
      }
    }

    if (!hasEmptyCells && !hasPossibleMerges) {
      this.#status = Game.statuses.lose;
    }
  }
  // #endregion function-tools
}

// module.exports = Game;
export default Game;
</file>

<file path="src/styles/blocks/_header-controls.scss">
.controls {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.button {
  cursor: pointer;

  width: 75px;
  height: 75px;
  border: none;
  border-radius: $button-border-radius;

  font-family: $font-button-family;
  font-size: $font-button-size-web;
  font-weight: $font-button-weight;
  color: $bg-main;

  box-shadow: $button-box-shadow;

  transition: 0.25s ease background, 0.25s ease box-shadow;
}

.start {
  font-size: $font-score-size-web;
  background: $button-start;

  &:hover {
    box-shadow: $button-hover-box-shadow;
  }
}

.restart {
  background: $button-restart;

  &:hover {
    box-shadow: $button-hover-box-shadow;
  }
}

/*
.controls {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.button {
  cursor: pointer;

  width: 75px;
  height: 75px;
  border: none;
  border-radius: 5px;

  font-family: sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #f9f6f2;

  transition: 0.25s ease background;
}

.start {
  font-size: 20px;
  background: #1dae28;

  &:hover {
    background: #179921;
  }
}

.restart {
  background: #f1b2b2;

  &:hover {
    background: #f87474;
  }
}
*/
</file>

<file path="src/styles/blocks/_header.scss">
.game-header {
  display: flex;
  justify-content: space-between;

  box-sizing: border-box;
  width: 100%;
  margin-bottom: 24px;
  padding: $grid-padding;
}

h1 {
  display: flex;
  align-items: center;
  justify-content: center;

  box-sizing: border-box;
  width: 150px;
  height: 75px;
  margin: 0;
  border-radius: $tile-border-radius;

  font-family: $font-header-family;
  font-size: $font-header-size-web;
  font-weight: $font-header-weight;
  color: $bg-main;

  background: linear-gradient(to bottom, $tile-2048-start, $tile-2048-end);
  box-shadow: $tile-2048-glow;
}

/*
.game-header {
  display: flex;
  justify-content: space-between;

  box-sizing: border-box;
  width: 100%;
  margin-bottom: 24px;
  padding: 10px;
}

h1 {
  display: flex;
  align-items: center;
  justify-content: center;

  box-sizing: border-box;
  width: 95px;
  height: 75px;
  margin: 0;
  border-radius: 5px;

  font-size: 24px;
  color: #f9f6f2;

  background: #edc22e;
}
*/
</file>

<file path="src/styles/utils/_vars.scss">
// color menu
$bg-main: #FFF;
$text-header: #2D3436;
$text-info: #636E72;
$tile-default: #F1F2F6;
$button-start: #00CFC1;
$button-restart: #d595cc;
$button-rules: #B9B4E3;

// color cells
$tile-2-start: #E1F5FE;
$tile-2-end: #E0F2F1;
$tile-4-start: #E8F5E9;
$tile-4-end: #D4E157;
$tile-8-start: #FFFDE7;
$tile-8-end: #FDD835;
$tile-16-start: #FFF3E0;
$tile-16-end: #FB8C00;
$tile-32-start: #FFEBEE;
$tile-32-end: #E53935;
$tile-64-start: #FCE4EC;
$tile-64-end: #D81B60;
$tile-128-start: #F3E5F5;
$tile-128-end: #8E24AA;
$tile-256-start: #F8BBD0;
$tile-256-end: #C2185B;
$tile-512-start: #E0F7FA;
$tile-512-end: #00ACC1;
$tile-1024-start: #E0F2F1;
$tile-1024-end: #00796B;
$tile-2048-start: #FFFDE7;
$tile-2048-end: #F9A825;

// ----------title "2048"----------
$font-header-family: 'Montserrat', sans-serif;
$font-header-weight: 700;
$font-header-size-web: 42px;
$font-header-size-mobile: 6.0rem;

// labels "SCORE", "BEST"
$font-label-family: 'Montserrat', sans-serif;
$font-label-weight: 400;
$font-label-size-web: 14px;
$font-label-size-mobile: 1.5rem;

// score value (numbers in the score and best)
$font-score-family: 'Montserrat', sans-serif;
$font-score-weight: 700;
$font-score-size-web: 20px;
$font-score-size-mobile: 2.5rem;

// numbers of tiles (2-8)
$font-tile-small-family: 'Montserrat', sans-serif;
$font-tile-small-weight: 700;
$font-tile-small-size-web: 28px;
$font-tile-small-size-mobile: 3.5rem;

// numbers of tiles (16+)
$font-tile-large-family: 'Montserrat', sans-serif;
$font-tile-large-weight: 700;
$font-tile-large-size-web: 24px;
$font-tile-large-size-mobile: 3.0rem;

// buttons "New Game", "Rules"
$font-button-family: 'Montserrat', sans-serif;
$font-button-weight: 600;
$font-button-size-web: 14px;
$font-button-size-mobile: 1.8rem;

// -----------General tile settings------------
$tile-border-radius: 12px;
$tile-box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);

// Special effects for tile 2048
$tile-2048-glow: 0 0 15px 5px rgba(249, 168, 37, 0.4);

// Grid cells (empty slots)
$cell-border-radius: 12px;
$cell-background: #bbada0; // Default background for empty cells
$cell-border: none;

// Main game container / grid
$grid-border: none;
$grid-padding: 10px;

// Button styles
$button-border-radius: 8px;
$button-box-shadow: 0 0px 15px rgba(187, 183, 183, 0.1);

// Button hover state
$button-hover-box-shadow: 0 0 10px rgba(255, 255, 255, 0.7);
</file>

<file path="src/styles/blocks/_counter.scss">
.counter-title {
  display: flex;
  align-items: center;
  justify-content: space-around;

  box-sizing: border-box;
  width: 100%;
  height: 30px;
  margin-block: 0;

  // Применяем общее скругление для ячеек/элементов
  border-radius: $cell-border-radius;

  // Типография для лейблов "SCORE/BEST"
  font-family: $font-label-family;
  font-size: $font-label-size-web;
  font-weight: $font-label-weight;

  // Цвет текста (основной инфо-текст)
  color: $text-info;

  // Фон счетчика (используем дефолтный цвет пустой плитки/ячейки)
  background: $tile-default;

  &__best {
    // Более светлый оттенок для второстепенного текста
    color: $text-info;
  }
}

.counter {
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  width: 50%;
  margin: 0 auto;
}

.game-score {
  // Значение счета (числа)
  font-family: $font-score-family;
  font-size: $font-score-size-web;
  font-weight: $font-score-weight;
  color: $text-header;
}

.game-best-score {
  // Значение самого счета (числа)
  font-family: $font-score-family;
  font-size: $font-label-size-web;
  font-weight: $font-label-weight;
  color: $text-header;
}

/* .counter-title {
  display: flex;
  align-items: center;
  justify-content: space-around;

  box-sizing: border-box;
  width: 100%;
  height: 30px;
  margin-block: 0;
  border-radius: 15px;

  font-size: 16px;
  color: #776e65;

  background: #d6cdc4;

  &__best {
    color: #9d958d;
  }
}

.counter {
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  width: 50%;
  margin: 0 auto;
}

.game-best-score {
  color: #9d958d;
}
*/
</file>

<file path="src/styles/blocks/_massege.scss">
.message {
  box-sizing: border-box;
  width: 100%;
  padding: $grid-padding;
  border-radius: $tile-border-radius;

  font-family: $font-tile-large-family;
  font-size: $font-score-size-web;
  font-weight: $font-tile-large-weight;
  color: $text-info;
  text-align: center;

  opacity: 1;
  background: $tile-default;

  transition: opacity 0.5s;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 350px;
}

.message-win {
  color: $bg-main;
  background: linear-gradient(to bottom, $tile-2048-start, $tile-2048-end);
  box-shadow: $tile-2048-glow;
}

.message-lose {
  position: absolute;
  top: 0;
}

.message-start {
  position: absolute;
  top: 0;

}

.message-container {
  position: relative;
  width: 100%;
  height: 150px;

  .rules-btn {
    margin-top: 10px;

    // Стили кнопки правил
    border-radius: $button-border-radius;

    font-family: $font-button-family;
    font-size: $font-button-size-web;
    font-weight: $font-button-weight;

    background: $button-rules;
  }
}

.message-rules {
  position: absolute;
  bottom: 100%;

  width: fit-content;
  height: 350px;
  border-radius: $tile-border-radius;

  text-align: left;

  opacity: 1;
  background: $bg-main;
  box-shadow: $button-hover-box-shadow;
}

.hidden {
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}

/*
.message {
  box-sizing: border-box;
  width: 100%;
  padding: 10px;
  border-radius: 5px;

  font-size: 20px;
  color: #776e65;
  text-align: center;

  opacity: 1;
  background: #d6cdc4;

  transition: opacity 0.5s;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 350px;
}

.message-win {
  color: #f9f6f2;
  background: #edc22e;
}

.message-lose {
  position: absolute;
  top: 0;
}

.message-start {
  position: absolute;
  top: 0;
}

.message-container {
  position: relative;
  width: 100%;
  height: 150px;

  .rules-btn {
    margin-top: 10px;
  }
}

.message-rules {
  position: absolute;
  bottom: 100%;

  width: fit-content;
  height: 350px;

  opacity: 1;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
}

.hidden {
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}
*/
</file>

<file path="src/styles/blocks/_page.scss">
html, body {
  overflow: hidden;
  overscroll-behavior-y: contain;
  width: 100%;
  margin: 0;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  min-height: 100vh;
  margin: 0;

  font-family: sans-serif;
  font-size: 24px;
  font-weight: 900;

  background: #31302e;
}

.version {
  position: absolute;
  top: 0;
  right: 0;

  font-size: 8px;
  color: #9f9992;
}
</file>

<file path="src/styles/blocks/_game-field.scss">
.field-cell {
  user-select: none;
  box-sizing: border-box;
  width: 75px;
  height: 75px;

  // Общие настройки из _vars.scss
  border: $cell-border;
  border-radius: $tile-border-radius;

  box-shadow: $tile-box-shadow;

  // Центрирование контента
  // display: flex;
  // align-items: center;
  // justify-content: center;
  text-align: center;

  // По умолчанию (пустая ячейка)
  background: $tile-default;

  // --- Стили для плиток с номиналом ---

  &--2, &--4, &--8 {
    font-family: $font-tile-small-family;
    font-size: $font-tile-small-size-web;
    font-weight: $font-tile-small-weight;
    color: $text-header; // Темный текст для светлых плиток
  }

  &--16, &--32, &--64, &--128, &--256, &--512, &--1024, &--2048 {
    font-family: $font-tile-large-family;
    font-size: $font-tile-large-size-web;
    font-weight: $font-tile-large-weight;
    color: #FFF; // Белый текст для контраста на темных/ярких фонах
  }

  &--2 {
    background: linear-gradient(to bottom, $tile-2-start, $tile-2-end);
  }

  &--4 {
    background: linear-gradient(to bottom, $tile-4-start, $tile-4-end);
  }

  &--8 {
    background: linear-gradient(to bottom, $tile-8-start, $tile-8-end);
  }

  &--16 {
    background: linear-gradient(to bottom, $tile-16-start, $tile-16-end);
  }

  &--32 {
    background: linear-gradient(to bottom, $tile-32-start, $tile-32-end);
  }

  &--64 {
    background: linear-gradient(to bottom, $tile-64-start, $tile-64-end);
  }

  &--128 {
    background: linear-gradient(to bottom, $tile-128-start, $tile-128-end);
  }

  &--256 {
    background: linear-gradient(to bottom, $tile-256-start, $tile-256-end);
  }

  &--512 {
    background: linear-gradient(to bottom, $tile-512-start, $tile-512-end);
  }

  &--1024 {
    background: linear-gradient(to bottom, $tile-1024-start, $tile-1024-end);
  }

  &--2048 {
    background: linear-gradient(to bottom, $tile-2048-start, $tile-2048-end);
    box-shadow: $tile-2048-glow; // Акцентное свечение для победной плитки
  }
}

.game-field {
  // Основная сетка
  padding: $grid-padding;
  border: $grid-border;
  border-radius: $tile-border-radius;

  background: $cell-background; // Цвет подложки сетки

  // Если вы используете display: grid вместо table:
  grid-gap: 10px;

  // display: grid;
}
</file>

<file path="src/styles/blocks/_rules.scss">
.rules-btn {
  z-index: 30;

  width: 100px;
  height: 30px;
  border-radius: $button-border-radius;

  font-family: $font-button-family;
  font-size: $font-button-size-web;
  font-weight: $font-button-weight;

  background-color: $button-rules;

  &:hover {
    box-shadow: $button-hover-box-shadow;
  }
}

.rules-list {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  height: 100%;
  margin-top: 0;
  padding: 0;

  font-family: $font-label-family;
  font-size: 16px;
  color: $text-info;
  list-style-type: none;
}
</file>

<file path="src/scripts/main.js">
'use strict';

// Uncomment the next lines to use your game instance in the browser
import Game from '../modules/Game.class.js';

const game = new Game();

class GameView {
  #timerWin;
  #languages = {
    en: [
      'How to play: Use the arrow keys (up, down, left, right) or ' +
        'swipes on a mobile device to move the tiles.',
      'Merging: When two tiles with the same number touch, ' +
        'they merge into one!',
      'Goal: Join the tiles to get to the 2048 tile!',
      'Game Over: If the board is full and there are no moves left, ' +
        'the game is over.',
    ],
    de: [
      'Spielanleitung: Verwenden Sie die Pfeiltasten (hoch, runter, links, ' +
        'rechts) oder Wischgesten auf einem mobilen Gerät, ' +
        'um die Spielsteine zu bewegen.',
      'Verschmelzen: Wenn zwei Kacheln mit der gleichen Zahl einander ' +
        'berühren, verschmelzen sie zu einer!',
      'Ziel: Kombiniere die Kacheln, um die 2048-Kachel zu erreichen!',
      'Spiel vorbei: Wenn das Spielfeld voll ist und keine Züge ' +
        'mehr möglich sind, ist das Spiel beendet.',
    ],
    ru: [
      'Как играть: используйте клавиши со стрелками (вверх, вниз, влево, ' +
        'вправо) или свайпы на мобильном устройстве, чтобы перемещать плитки.',
      'Слияние: Когда две плитки с одинаковыми числами соприкасаются, ' +
        'они объединяются в одну, а их номиналы суммируются.',
      'Цель: Соединяй плитки и копи очки, чтобы добраться до числа 2048.',
      'Конец игры: Если поле заполнено и доступных ходов для слияния ' +
        'больше нет — игра окончена.',
    ],
    esp: [
      'Cómo jugar: Usa las teclas de flecha (arriba, abajo, izquierda, ' +
        'derecha) para mover las fichas.',
      'Fusión: ¡Cuando dos fichas con el mismo número se tocan, ' +
        'se fusionan en una sola!',
      'Objetivo: ¡Combina las fichas para llegar a la ficha 2048!',
      'Fin del juego: Si el tablero está lleno y no quedan ' +
        'movimientos, el juego termina.',
    ],
  };

  #touchPosStartX = 0;
  #touchPosStartY = 0;

  constructor(logic) {
    this.game = logic;

    this.bodyContainer = document.querySelector('tbody');
    this.startBtn = document.querySelector('.button');
    this.rulesBtn = document.querySelector('.rules-btn');
    this.rulesMessage = document.querySelector('.message-rules');
    this.rulesItems = document.querySelectorAll('.rules-item');
    this.languageContainer = document.querySelector('.language-buttons');
    this.currentScore = document.querySelector('.game-score');
    this.bestScore = document.querySelector('.game-best-score');
    this.tableItems = [...document.querySelectorAll('.field-cell')];

    this.messageItems = document.querySelector('.message-container');
    this.titleGame = document.querySelector('h1');

    // Variables for the blocks Message
    this.messageStart = this.messageItems.querySelector('.message-start');
    this.messageWin = this.messageItems.querySelector('.message-win');
    this.messageLose = this.messageItems.querySelector('.message-lose');

    this.initListener();

    // We start an inactivity timer
    // to draw the user's attention to the Start button.
    this.timerIdle = setTimeout(
      () => this.applyAnimationClass(this.startBtn),
      5000,
    );
  }

  // #region Listeners
  initListener() {
    this.startBtn.addEventListener('click', () => {
      this.handleBtnStart();
      clearTimeout(this.timerIdle);
      this.updateView();
    });

    this.rulesBtn.addEventListener('click', () => {
      this.switchLanguage('en');
      this.rulesMessage.classList.toggle('hidden');
    });

    this.bodyContainer.addEventListener('touchstart', (e) => {
      this.#touchPosStartX = e.touches[0].clientX;
      this.#touchPosStartY = e.touches[0].clientY;
    });

    this.bodyContainer.addEventListener(
      'touchmove',
      (e) => {
        e.preventDefault();
      },
      { passive: false },
    );

    this.bodyContainer.addEventListener('touchend', (e) => {
      const touchPosEndX = e.changedTouches[0].clientX;
      const touchPosEndY = e.changedTouches[0].clientY;

      const threshold = 50; // pixels
      const diffX = touchPosEndX - this.#touchPosStartX;
      const diffY = touchPosEndY - this.#touchPosStartY;

      // We check whether the movement was long enough along any of the axes
      if (Math.abs(diffX) < threshold && Math.abs(diffY) < threshold) {
        return;
      }

      if (Math.abs(diffX) > Math.abs(diffY)) {
        if (diffX > 0) {
          this.game.moveRight();
        } else {
          this.game.moveLeft();
        }
      } else {
        if (diffY > 0) {
          this.game.moveDown();
        } else {
          this.game.moveUp();
        }
      }

      this.updateView();
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowLeft') {
        this.game.moveLeft();
        this.updateView();
      }

      if (e.key === 'ArrowRight') {
        this.game.moveRight();
        this.updateView();
      }

      if (e.key === 'ArrowUp') {
        this.game.moveUp();
        this.updateView();
      }

      if (e.key === 'ArrowDown') {
        this.game.moveDown();
        this.updateView();
      }
    });

    this.languageContainer.addEventListener('click', (e) => {
      const value = e.target.closest('.btn-language');

      if (!value) {
        return;
      }

      const lowerCaseValue = value.textContent.toLowerCase();
      const targetValue = e.target;

      this.switchLanguage(lowerCaseValue, targetValue);
    });

    // #endregion Listeners
  }

  // Update view
  updateView() {
    const state = this.game.getState();

    this.renderBoard(state.board, state.targetCellIndex);
    this.renderStatusGame(state.statusGame);
    this.renderScore(state.score, state.bestScore);
  }
  // #region methods-tools
  // timer win
  runWinTimer() {
    this.#timerWin = setTimeout(
      () => this.applyAnimationClass(this.startBtn),
      5000,
    );
  }
  // Work with message blocks
  renderMessage(statusValue) {
    if (statusValue === Game.statuses.idle) {
      return;
    }

    this.messageStart.classList.add('hidden');
    this.messageLose.classList.add('hidden');
    this.messageWin.classList.add('hidden');
    this.messageItems.classList.add('hidden');
    this.titleGame.classList.remove('hidden');

    if (statusValue !== Game.statuses.playing) {
      const suffix = statusValue === Game.statuses.win ? 'win' : 'lose';
      const messageEl = this.messageItems.querySelector(`.message-${suffix}`);

      if (suffix === 'lose') {
        this.runWinTimer();
      }

      if (suffix === 'win') {
        this.titleGame.classList.add('hidden');
      }
      messageEl.classList.remove('hidden');
      this.messageItems.classList.remove('hidden');
    }
  }

  // Handle button Start
  handleBtnStart() {
    const statusValue = this.game.getState().statusGame;

    if (statusValue !== Game.statuses.idle) {
      this.game.restart();
      this.tableItems.forEach((el) => this.applyAnimationClass(el));
      this.applyAnimationClass(this.startBtn);
      clearTimeout(this.#timerWin);
    } else {
      this.game.start();
      this.applyAnimationClass(this.startBtn);
      clearTimeout(this.timerIdle);
    }
  }

  // Rendering Board
  renderBoard(boardData, cellIndex) {
    const flatBoard = boardData.flat();

    this.tableItems.forEach((cell, i) => {
      const classListValue = [...cell.classList];
      const value = flatBoard[i];
      const classModif = `field-cell--${value}`;
      let j = 0;

      // Remove old class modifiers (field-cell--value)
      // before rendering the new state
      while (j < classListValue.length) {
        const currString = classListValue[j];

        if (currString.startsWith('field-cell--')) {
          cell.classList.remove(currString);
        }
        j++;
      }

      if (value === 2048) {
        this.applyAnimationClass(cell);
        this.runWinTimer();
      }

      cell.textContent = value === 0 ? '' : value;
      cell.classList.add(classModif);

      cellIndex.forEach((val) => {
        if (i === val) {
          this.triggerCellPulse(cell);
        }
      });
    });
  }

  // Rendering Status - Game
  renderStatusGame(infoStatus) {
    // changing button
    if (infoStatus !== Game.statuses.idle) {
      this.startBtn.classList.remove('start');
      this.startBtn.classList.add('restart');
      this.startBtn.textContent = 'Restart';
    }

    this.renderMessage(infoStatus);
  }

  // Rendering Score
  renderScore(dataScore, dataBestScore) {
    this.currentScore.textContent = dataScore;
    this.bestScore.textContent = dataBestScore;
  }

  // #endregion methods-tools

  // #region animation
  triggerCellPulse(currCell) {
    currCell.classList.add('scale-element');

    setTimeout(() => {
      currCell.classList.remove('scale-element');
    }, 300);
  }

  applyAnimationClass(element) {
    const currStatus = this.game.getState().statusGame;

    if (currStatus === Game.statuses.playing) {
      element.classList.remove('vibrate-element');

      return;
    }

    element.classList.add('vibrate-element');
  }

  switchLanguage(newLanguage, currEl) {
    switch (newLanguage) {
      case 'de':
        this.changeActiveLanguageClass(currEl);

        return this.renderRulesMessage(this.#languages.de);

      case 'ru':
        this.changeActiveLanguageClass(currEl);

        return this.renderRulesMessage(this.#languages.ru);

      case 'esp':
        this.changeActiveLanguageClass(currEl);

        return this.renderRulesMessage(this.#languages.esp);

      default:
        if (currEl) {
          this.changeActiveLanguageClass(currEl);
        }

        return this.renderRulesMessage(this.#languages.en);
    }
  }

  renderRulesMessage(arrText) {
    let str = 0;

    this.rulesItems.forEach((li) => {
      while (str < arrText.length) {
        li.textContent = arrText[str];
        str++;
        break;
      }
    });
  }

  changeActiveLanguageClass(currButton) {
    const activeClass = this.languageContainer.querySelector(
      '.btn-language--is-active',
    );

    if (activeClass) {
      activeClass.classList.remove('btn-language--is-active');
    }

    currButton.classList.add('btn-language--is-active');
  }
}

const view = new GameView(game);

view.updateView();
</file>

<file path="src/index.html">
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>2048</title>
    <link rel="stylesheet" href="./styles/main-test.scss" />
    <link
      rel="apple-touch-icon"
      sizes="180x180"
      href="../src/images/favicon_io/apple-touch-icon.png"
    />
    <link
      rel="icon"
      type="image/png"
      sizes="32x32"
      href="../src/images/favicon_io/favicon-32x32.png"
    />
    <link
      rel="icon"
      type="image/png"
      sizes="16x16"
      href="../src/images/favicon_io/favicon-16x16.png"
    />
    <link
      rel="icon"
      type="image/png"
      sizes="192x192"
      href="../src/images/favicon_io/android-chrome-192x192.png"
    />
    <link
      rel="icon"
      type="image/png"
      sizes="512x512"
      href="../src/images/favicon_io/android-chrome-512x512.png"
    />
    <link rel="manifest" href="../src/images/favicon_io/site.webmanifest" />
  </head>
  <span class="version">version 1.2_daniyal</span>
  <body>
    <div class="container">
      <div class="game-header">
        <h1>2048</h1>
        <div class="controls">
          <div class="counter">
            <p class="counter-title">
              Score:
              <span class="game-score">0</span>
            </p>
            <p class="counter-title counter-title__best">
              Best:
              <span class="game-best-score">0</span>
            </p>
          </div>

          <button class="button start">Start</button>
        </div>
      </div>

      <table class="game-field">
        <tbody>
          <tr class="field-row">
            <td class="field-cell field-cell--2"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
          </tr>

          <tr class="field-row">
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
          </tr>

          <tr class="field-row">
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
          </tr>

          <tr class="field-row">
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
            <td class="field-cell"></td>
          </tr>
        </tbody>
      </table>

      <div class="message-container">
        <div class="message message-rules hidden">
          <div class="language-buttons">
            <button class="btn-language btn-language--is-active btn-en">
              En
            </button>
            <button class="btn-language btn-de">De</button>
            <button class="btn-language btn-esp">Esp</button>
            <button class="btn-language btn-ru">Ru</button>
          </div>
          <ul class="rules-list">
            <li class="rules-item"></li>
            <li class="rules-item"></li>
            <li class="rules-item"></li>
            <li class="rules-item"></li>
          </ul>
        </div>
        <p class="message message-lose hidden">You lose! Restart the game?</p>
        <p class="message message-win hidden">Winner! Congrats! You did it!</p>
        <p class="message message-start">
          Press "Start" to begin game.<br>
           Good luck!
        </p>
        <button class="button rules-btn">Rules</button>
      </div>
    </div>
    <script type="module" src="scripts/main.js"></script>
  </body>
</html>
</file>

<file path="src/styles/main.scss">
html, body {
  overflow: hidden;
  overscroll-behavior-y: contain;
  width: 100%;
  margin: 0;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;

  min-height: 100vh;
  margin: 0;

  font-family: sans-serif;
  font-size: 24px;
  font-weight: 900;

  background: #fbf8ef;
}

.field-cell {
  user-select: none;

  box-sizing: border-box;
  width: 75px;
  height: 75px;
  border-radius: 5px;

  color: #776e65;
  text-align: center;
  vertical-align: center;

  background: #d6cdc4;

  &--2 {
    background: #eee4da;
  }

  &--4 {
    background: #ede0c8;
  }

  &--8 {
    color: #f9f6f2;
    background: #f2b179;
  }

  &--16 {
    color: #f9f6f2;
    background: #f59563;
  }

  &--32 {
    color: #f9f6f2;
    background: #f67c5f;
  }

  &--64 {
    color: #f9f6f2;
    background: #f65e3b;
  }

  &--128 {
    color: #f9f6f2;
    background: #edcf72;
  }

  &--256 {
    color: #f9f6f2;
    background: #edcc61;
  }

  &--512 {
    color: #f9f6f2;
    background: #edc850;
  }

  &--1024 {
    color: #f9f6f2;
    background: #edc53f;
  }

  &--2048 {
    color: #f9f6f2;
    background: #edc22e;
  }
}

.game-field {
  border-spacing: 10px;
  border-radius: 5px;
  background: #bbada0;
}

.game-header {
  display: flex;
  justify-content: space-between;

  box-sizing: border-box;
  width: 100%;
  margin-bottom: 24px;
  padding: 10px;
}

h1 {
  display: flex;
  align-items: center;
  justify-content: center;

  box-sizing: border-box;
  width: 95px;
  height: 75px;
  margin: 0;
  border-radius: 5px;

  font-size: 24px;
  color: #f9f6f2;

  background: #edc22e;
}

.counter-title {
  display: flex;
  align-items: center;
  justify-content: space-around;

  box-sizing: border-box;
  width: 100%;
  height: 30px;
  margin-block: 0;
  border-radius: 15px;

  font-size: 16px;
  color: #776e65;

  background: #d6cdc4;

  &__best {
    color: #9d958d;
  }
}

.game-best-score {
  color: #9d958d;
}

.counter {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 0 auto;
  width: 50%;
}

.controls {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.button {
  cursor: pointer;

  width: 75px;
  height: 75px;
  border: none;
  border-radius: 5px;

  font-family: sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #f9f6f2;

  transition: 0.25s ease background;
}

.start {
  font-size: 20px;
  background: #1dae28;

  &:hover {
    background: #179921;
  }
}

.restart {
  background: #f1b2b2;

  &:hover {
    background: #f87474;
  }
}

.rules-btn {
  z-index: 30;
  width: 100px;
  height: 30px;
  background-color: #f2b179;

  &:hover {
    background-color: #ed994e;
  }
}

.language-buttons {
  display: flex;
  justify-content: space-evenly;
}

.btn-language {
  cursor: pointer;

  width: 50px;
  border: none;
  border-radius: 5px;

  font-family: sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #f2bd1e;

  transition: 0.3s;

  &:hover {
    transform: scale(1.1);
  }

  &:active {
    transform: scale(0.9);
  }

  &--is-active {
    background-color: #484747;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
  }
}

.message {
  box-sizing: border-box;
  width: 100%;
  padding: 10px;
  border-radius: 5px;

  font-size: 20px;
  color: #776e65;
  text-align: center;

  opacity: 1;
  background: #d6cdc4;

  transition: opacity 0.5s;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 350px;
}

.message-win {
  color: #f9f6f2;
  background: #edc22e;
}

.message-lose {
  position: absolute;
  top: 0;
}

.message-start {
  position: absolute;
  top: 0;
}

.message-container {
  position: relative;
  width: 100%;
  height: 150px;

  .rules-btn {
    margin-top: 10px;
  }
}

.message-rules {
  position: absolute;
  bottom: 100%;

  width: fit-content;
  height: 350px;

  opacity: 1;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
}

.rules-list {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  height: 100%;
  margin-top: 0;
  padding: 0;

  font-size: 16px;
  list-style-type: none;
}

.hidden {
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}

// animation
.vibrate-element {
  animation-name: vibration;
  animation-duration: 0.3s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

.scale-element {
  animation-name: scale-cells;
  animation-duration: 0.3s;
  animation-timing-function: linear;
  animation-iteration-count: 1;
}

@keyframes vibration {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(3deg);
  }
  50% {
    transform: rotate(0deg);
  }
  75% {
    transform: rotate(-3deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

@keyframes scale-cells {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }

  100% {
    transform: scale(1);
  }
}
</file>

</files>
