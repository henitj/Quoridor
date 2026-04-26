## README.md

# Quoridor (JS)

A browser-based version of the abstract strategy game **Quoridor**. This project focuses on implementing the unique mechanics of the game: navigating a pawn across a $9 \times 9$ grid while strategically placing walls to block the opponent.

URL - https://quoridor-eosin.vercel.app/

## 🚀 Features
* **Pathfinding Validation:** Uses a **Breadth-First Search (BFS)** algorithm to ensure that no wall placement completely blocks a player from their goal.
* **Grid-Based Interaction:** Dynamic wall placement logic that snaps to grid intersections.
* **Turn-Based System:** Robust state management to handle movement, wall inventory, and turn alternation.
* **Victory Detection:** Real-time monitoring of pawn positions relative to the opposite goal line.

## 🛠️ Technical Stack
* **JavaScript (ES6):** Game logic, BFS algorithm, and state management.
* **HTML5 Canvas:** Rendering the board, pawns, and placed walls.
* **CSS3:** UI for wall counts and turn indicators.

## 🕹️ How to Play
1. **Clone the repository:**
   ```bash
   git clone https://github.com/HenitJain/Quoridor.git
   ```
2. **Launch:**
   * Open `index.html` in your browser.
3. **Gameplay:**
   * **Movement:** On your turn, move your pawn one square (horizontally or vertically).
   * **Walls:** Instead of moving, place a wall to block your opponent. You have a limited supply.
   * **Goal:** Be the first player to reach any square on the opposite side of the board.

## 📂 Project Structure
* `index.html`: Board container and controls.
* `game.js`: Core loop and input handling.
* `pathfinder.js`: Implementation of BFS to validate move legality.
* `README.md`: Documentation.

## ⚙️ Key Algorithm: BFS Pathfinding
The most critical part of Quoridor's logic is ensuring that every player always has at least one path to their goal. Whenever a player attempts to place a wall, the engine runs a BFS:

1.  Add the current pawn position to a queue.
2.  Mark the position as visited.
3.  While the queue is not empty:
    * Dequeue the current cell.
    * Check all 4 neighbors (up, down, left, right) that are not blocked by a wall.
    * If a neighbor is on the goal line, the wall placement is **Valid**.
    * Otherwise, add unvisited neighbors to the queue.
4.  If the queue empties without reaching the goal, the wall placement is **Illegal**.
