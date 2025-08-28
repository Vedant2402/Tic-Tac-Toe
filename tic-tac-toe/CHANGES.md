# Tic-Tac-Toe Application Changes

This document outlines the changes made to the default Angular application to create the Tic-Tac-Toe game.

## `src/app/app.component.ts`

The main logic for the Tic-Tac-Toe game resides in this file. The original content was replaced with the following features:

-   **Game State Management:**
    -   `squares`: An array to represent the 9 squares of the board.
    -   `xIsNext`: A boolean to track whose turn it is.
    -   `winner`: A string to store the winner ('X' or 'O') or `null`.
    -   `isDraw`: A boolean to indicate if the game is a draw.

-   **Game Lifecycle:**
    -   `ngOnInit()`: Initializes the game when the component loads by calling `newGame()`.
    -   `newGame()`: Resets the game state, clearing the board and resetting the winner and turn.

-   **Game Logic:**
    -   `player` (getter): Returns the current player ('X' or 'O').
    -   `makeMove(idx)`: Handles a player's move. It updates the `squares` array, switches the turn, and checks for a winner or a draw.
    -   `calculateWinner()`: Checks all possible winning combinations (rows, columns, and diagonals) to determine if there is a winner.

## `src/app/app.component.html`

The HTML file was updated to create the user interface for the game. The placeholder content was removed and replaced with:

-   **Game Title:** An `<h1>` tag for "Tic-Tac-Toe".
-   **Status Display:** A section to display the current game status, such as the current player's turn, the winner, or if the game is a draw.
-   **New Game Button:** A button that allows the user to start a new game by calling the `newGame()` method.
-   **Game Board:** A 3x3 grid is dynamically generated using nested `*ngFor` loops. Each square is clickable and calls the `makeMove()` method with its index. The content of each square (`'X'`, `'O'`, or empty) is bound to the `squares` array.

## `src/app/app.component.css`

This file was populated with styles to make the game board and other UI elements visually appealing and functional.

-   **Layout:** Flexbox is used to center the game components on the page.
-   **Board Styling:** CSS Grid is used to create the 3x3 layout for the Tic-Tac-Toe board.
-   **Square Styling:** Styles for the individual squares, including borders, dimensions, font size, and alignment.
-   **Interactivity:** A hover effect is added to the squares to provide visual feedback to the user.
-   **Typography:** Basic styling for the status message and button.
