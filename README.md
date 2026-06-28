# 2048-AI

A fully autonomous, self-playing 2048 game powered by an Expectimax algorithm. Built purely with HTML, CSS, and Vanilla JavaScript, this project features a modern dark-mode interface and highly optimized decision-making logic.

## Features

* **Expectimax Algorithm**: Calculates the best possible moves by evaluating a decision tree that accounts for the random nature of new tile spawns.
* **Dynamic Search Depth**: Automatically scales the search depth (from 3 to 7) based on the number of empty tiles, ensuring fast early-game moves and deep calculation during tight endgame scenarios.
* **Advanced Heuristics**: Evaluates board states using a carefully tuned mix of smoothness, monotonicity, and empty tile counts.
* **Corner Locking**: Utilizes a specialized weight matrix and heavy corner penalties to ensure the highest value tile stays safely anchored in the top-left corner.
* **Performance Optimized**: Implements precomputed Log2 lookup tables, fast matrix math, and probabilistic pruning to evaluate thousands of moves per second without freezing the browser.
* **Zero Dependencies**: Built entirely from scratch using vanilla web technologies without any external libraries.
* **Sleek UI/UX**: A responsive, modern dark-themed interface with color-coded tiles supporting values up to 65,536.

## How It Works

The AI uses the **Expectimax** algorithm to look ahead multiple turns. Since 2048 has an element of chance (2 or 4 tiles spawning randomly), standard Minimax isn't sufficient. Expectimax calculates the "expected value" of random events (chance nodes) rather than assuming the worst-case scenario.

To determine the strength of a board state, the AI relies on a heuristic evaluation function that scores the board based on:
1. **Weight Matrix**: Encourages a "snake" pattern, heavily rewarding large tiles structured in specific formations.
2. **Monotonicity**: Ensures tile values strictly increase or decrease along rows and columns.
3. **Smoothness**: Minimizes the value difference between adjacent tiles to allow for easier merging.
4. **Empty Spaces**: Rewards keeping the board as open as possible.

## Usage

Since the project uses zero external dependencies, running it is incredibly simple:

1. Clone this repository or download the `index.html` file.
2. Open `index.html` in any modern web browser.
3. Click the **Start Engine** button to watch the neural net optimize and play the game automatically.
   
