# N-Puzzle Solver

This project implements an **N-Puzzle Solver** using the **A\*** algorithm in JavaScript. The program solves sliding tile puzzles on a k \* k grid, where one cell is empty, and the task is to rearrange the tiles into their correct order.

---

## Features

- **A\*** Algorithm:
  - Efficient pathfinding using heuristic (Manhattan distance).
  - Dynamic exploration of states to find the optimal solution.

- **Dynamic Input Handling**:
  - Accepts any valid k \* k grid size between 3 \* 3 and 5 \* 5.

- **Customizable Goal State**:
  - Automatically generates the target configuration for the puzzle.

- **Move Tracking**:
  - Outputs the sequence of moves required to solve the puzzle.

- **Edge Case Handling**:
  - Detects and reports if no solution exists.

---

## Input Format

The program reads input from a file (e.g., `input.txt`) containing:

1. **Grid Size**: The first line specifies the grid size `k`.
2. **Initial State**: The next k \* k lines represent the grid configuration, with `0` denoting the empty cell.

### Example Input:
```
3
0
3
8
4
1
7
2
6
5
```

This input represents the following initial state:

```
0 3 8
4 1 7
2 6 5
```

---

## Output Format

1. The first line contains the number of moves required to solve the puzzle.
2. The subsequent lines list the moves in order (e.g., `UP`, `DOWN`, `LEFT`, `RIGHT`).

### Example Output:
```
70
RIGHT
DOWN
...
```

---

## How It Works

1. **Manhattan Distance Heuristic**:
   - Calculates the sum of distances of all tiles from their correct positions.

2. **Move Generation**:
   - Generates all valid moves for the empty cell (`0`) based on its position.

3. **A\*** Algorithm:
   - Prioritizes states with the lowest cost (`g + h`):
     - `g`: Cost to reach the current state.
     - `h`: Heuristic estimate to the goal.

4. **Solution Path**:
   - Tracks the sequence of moves leading to the solved state.

---

## Running the Program

### Prerequisites

- **Node.js** installed on your system.

### Steps

1. Save the JavaScript code in a file named `n_puzzle_solver.js`.
2. Prepare an input file (e.g., `input.txt`) with the grid configuration.
3. Run the program in your terminal:

   ```bash
   node n_puzzle_solver.js
   ```

   Ensure the `fs` module is used to read the `input.txt` file.

---

## Example Execution

### Input File (`input.txt`):
```
3
0
3
8
4
1
7
2
6
5
```

### Run Command:
```bash
node n_puzzle_solver.js
```

### Output:
```
70
RIGHT
DOWN
...
```

---

## Limitations

- Grid sizes are restricted to **3 \* 3** to **5 \* 5**.
- Assumes the puzzle is solvable; otherwise, it reports "No solution found."

---

## Future Improvements

- **Enhanced Performance**:
  - Optimize heuristic calculations.

- **Parallel Processing**:
  - Use worker threads for faster computation on larger grids.

- **Visualization**:
  - Add a graphical representation of moves.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.
