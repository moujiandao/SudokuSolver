The program parses the input Sudoku puzzle using Extended Backus-Naur Form (EBNF). It then uses a backtracking algorithm to fill in the empty cells in the grid. The algorithm tries numbers from 1 to 9 and recursively checks for validity based on Sudoku rules. If a conflict arises, it backtracks and tries a different number until the puzzle is solved or determined to be unsolvable.

The program outputs the solved Sudoku grid or displays an error message if no solution is found.

--------------------------------------------------------

Input Format (EBNF)
The program expects the following format for the input:
<input> ::= <puzzle> <eof>
<puzzle> ::= 81*<value> "\n"
<value> ::= "." | "1" | ... | "9"

Output Format (EBNF)
The program expects the following format for the input:
<output> ::= <result> <eof>
<result> ::= <error> | <nosolution> | <puzzle> <puzzle>*
<error> ::= "ERROR: expected " <expected> " saw " <saw> "\n"
<expected> ::= "<value>" | "\\n" | "<eof>"
<saw> ::= "<eof>" | "\\n" | <printable> | "\\x" 2*<hex-digit>
<printable> ::= (* all characters c where isprint(c) is true *)
<hex-digit> ::= '0' | '1' | ... | 'a' | 'b' | 'c' | 'd' | 'e' | 'f'
<nosolution> ::= "No solutions.\n"
<puzzle> ::= 81*<value> "\n"
<value> ::= "." | "1" | ... | "9"
