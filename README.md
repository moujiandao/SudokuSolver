# Sudoku Solver

A command-line Sudoku solver written in C++ in 2014.

The program reads an 81-character puzzle, applies candidate elimination and hidden-single simplification, then uses backtracking when deterministic progress stops. It prints every solution it finds or reports that the puzzle has no solution.

## Build

A C++11-compatible compiler is sufficient:

```bash
c++ -std=c++11 main.cpp Puzzle.cpp Cell.cpp -o sudoku-solver
```

## Input

The program reads exactly 81 values followed by a newline and end-of-file. Digits `1` through `9` represent fixed cells, and `.` represents an empty cell.

```ebnf
input = grid, newline, end-of-file ;
grid = value, { value } ;          (* exactly 81 values *)
value = "." | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9" ;
newline = "\\n" ;
```

Example:

```bash
printf '53..7....6..195....98....6.8...6...34..8.3..17...2...6.6....28....419..5....8..79\n' \
  | ./sudoku-solver
```

## Output

Each solution is written as 81 digits followed by a newline. Invalid input produces an error describing the unexpected character. A valid puzzle with no solution produces:

```text
No solutions.
```

## Implementation

- [`Cell.cpp`](Cell.cpp) tracks a cell value and its remaining candidates.
- [`Puzzle.cpp`](Puzzle.cpp) owns the 9 by 9 grid and Sudoku constraints.
- [`main.cpp`](main.cpp) validates input, applies simplification, manages alternatives, and prints solutions.

## Project status

This repository is an archived early programming project. The implementation and commit history are retained as evidence of the original work rather than modernized into a new solver.
