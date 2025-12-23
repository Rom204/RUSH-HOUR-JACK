# Rush Hour (Jack)

A classic Rush Hour puzzle game implementation in the Jack language for the Nand to Tetris course (Project 9).

## Overview
This is a logic puzzle game where the goal is to drive the **Player Car ("CAR")** out of a 6x6 grid traffic jam. To escape, you must slide other blocking vehicles out of the way.

## Features
- **4 Distinct Levels**: Increasing difficulty, procedurally selected.
- **Graphical Interface**: 6x6 Grid visualization with 32x32 pixel cells.
- **Full Control**: Select and move any vehicle on the board.
- **Visual Feedback**:
    - Player car labeled "CAR".
    - Blocker cars labeled with ID numbers.
    - Selected car highlighted with a double border.
- **Game Logic**:
    - Valid movement rules (cars only slide forwards/backwards).
    - Collision detection (cannot move through other cars or walls).
    - Win condition detection.
    - Input locking upon victory.
- **Robustness**:
    - Memory management (no heap overflows).
    - Spam protection (regeneration delay).

## Controls
| Key | Action |
| :--- | :--- |
| **0** | Select Player Car ("CAR") |
| **1** - **5** | Select Blocker Cars (by ID) |
| **Arrow Keys** | Move selected car (Up/Down/Left/Right) |
| **R** | Regenerate Level (Reset) |
| **Q** | Quit Game |

*Note: Once you win, controls are locked. Press 'R' to play again.*

## How to Run
1.  Open the **Nand2Tetris VM Emulator**.
2.  Load the compiled directory (containing the `.vm` files).
3.  Set the speed to **Normal** or **Fast** (Animation enabled).
4.  Press **Run**.
5.  Follow the on-screen prompt ("Press any key to start") to seed the random level generator.

## Project Structure
- `Main.jack`: Entry point. Handles random seeding and game loop initialization.
- `RushHourGame.jack`: Main game controller. Manages input handling, game state (playing/won), and level transitions.
- `Board.jack`: Handles the grid logic, collision detection, and rendering of lines and cars.
- `Car.jack`: Represents a single vehicle with position, size, orientation, and self-drawing capability.
- `LevelGenerator.jack`: Contains the layouts for the 4 distinct puzzle levels.
