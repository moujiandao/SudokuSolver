# Sudoku Solver

A Sudoku puzzle solver using Extended Backus-Naur Form (EBNF) and backtracking algorithm.

## Overview

The program parses the input Sudoku puzzle using Extended Backus-Naur Form (EBNF). It then uses a backtracking algorithm to fill in the empty cells in the grid. The algorithm tries numbers from 1 to 9 and recursively checks for validity based on Sudoku rules. If a conflict arises, it backtracks and tries a different number until the puzzle is solved or determined to be unsolvable.

The program outputs the solved Sudoku grid or displays an error message if no solution is found.

---

## Input Format (EBNF)
The program expects the following format for the input:
```ebnf
 ::=  
 ::= 81* "\n"
 ::= "." | "1" | ... | "9"
```

## Output Format (EBNF)
The program expects the following format for the input:
```ebnf
 ::=  
 ::=  |  |  *
 ::= "ERROR: expected "  " saw "  "\n"
 ::= "" | "\\n" | ""
 ::= "" | "\\n" |  | "\\x" 2*
 ::= (* all characters c where isprint(c) is true *)
 ::= '0' | '1' | ... | 'a' | 'b' | 'c' | 'd' | 'e' | 'f'
 ::= "No solutions.\n"
 ::= 81* "\n"
 ::= "." | "1" | ... | "9"
```
