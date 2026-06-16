Project Overview

This project is a Sudoku Solver System developed in C++ using the Backtracking Algorithm. The program takes a 9×9 Sudoku puzzle as input, where empty cells are represented by 0, and automatically finds the correct solution if one exists.

Objective

The objective of this project is to solve a Sudoku puzzle by filling all empty cells while following Sudoku rules:

Each row must contain numbers 1–9 without repetition.
Each column must contain numbers 1–9 without repetition.
Each 3×3 sub-grid must contain numbers 1–9 without repetition.
Features
1. User Input
Accepts a 9×9 Sudoku puzzle from the user.
Uses 0 to represent empty cells.
2. Display Puzzle
Shows the entered Sudoku puzzle in a formatted grid.
Empty cells are displayed as ".".
3. Sudoku Validation
Checks whether a number can be placed safely in a specific position.
Verifies:
Row constraints
Column constraints
3×3 box constraints
4. Automatic Solver
Uses the Backtracking Algorithm to solve the puzzle.
Tries possible values recursively until a valid solution is found.
5. Display Solved Sudoku
Prints the completed Sudoku grid in a neat format.
Displays a success message after solving.
Functions Used
displayGrid()

Displays the solved Sudoku puzzle.

showPuzzle()

Displays the original puzzle entered by the user.

isRowSafe()

Checks if a number already exists in a row.

isColumnSafe()

Checks if a number already exists in a column.

isBoxSafe()

Checks if a number already exists in a 3×3 box.

isSafe()

Verifies whether a number can be placed in a specific cell.

findEmptyCell()

Finds the next empty cell (value 0).

solveSudoku()

Uses recursion and backtracking to solve the puzzle.

Algorithm Used
Backtracking Algorithm
Find an empty cell.
Try numbers from 1 to 9.
Check if the number is safe.
Place the number if valid.
Recursively solve the remaining puzzle.
If no solution is found, backtrack and try another number.
Continue until the puzzle is solved.
Sample Input
5 3 0 0 7 0 0 0 0
6 0 0 1 9 5 0 0 0
0 9 8 0 0 0 0 6 0
8 0 0 0 6 0 0 0 3
4 0 0 8 0 3 0 0 1
7 0 0 0 2 0 0 0 6
0 6 0 0 0 0 2 8 0
0 0 0 4 1 9 0 0 5
0 0 0 0 8 0 0 7 9
Sample Output
=================================
         SUDOKU SOLVED
=================================

+-------+-------+-------+
| 5 3 4 | 6 7 8 | 9 1 2 |
| 6 7 2 | 1 9 5 | 3 4 8 |
| 1 9 8 | 3 4 2 | 5 6 7 |
+-------+-------+-------+
| 8 5 9 | 7 6 1 | 4 2 3 |
| 4 2 6 | 8 5 3 | 7 9 1 |
| 7 1 3 | 9 2 4 | 8 5 6 |
+-------+-------+-------+
| 9 6 1 | 5 3 7 | 2 8 4 |
| 2 8 7 | 4 1 9 | 6 3 5 |
| 3 4 5 | 2 8 6 | 1 7 9 |
+-------+-------+-------+

Puzzle Solved Successfully!
How to Compile and Run
Compile
g++ sudoku_solver.cpp -o sudoku_solver
Run
./sudoku_solver
Advantages
Fast and efficient for standard Sudoku puzzles.
Easy to understand and implement.
Demonstrates recursion and backtracking concepts.
User-friendly console interface.
Future Improvements
Graphical User Interface (GUI).
Random Sudoku puzzle generator.
Difficulty levels (Easy, Medium, Hard).
Save and load puzzles from files.
Real-time Sudoku validation.

Concepts Used: Arrays, Functions, Recursion, Backtracking, Problem Solving, Console Programming.

Get smarter responses, upload files and images, and more.
