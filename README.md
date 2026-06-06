# Sudoku-solver-
Sudoku solver using C++

Project Overview:

This project is a Sudoku Solver developed in C++ using the Backtracking Algorithm. The program takes an incomplete 9×9 Sudoku puzzle as input, where empty cells are represented by 0, and automatically finds a valid solution if one exists.

Objective:

The objective of this project is to demonstrate the use of:

Recursion
Backtracking Algorithm
Arrays
Functions
Problem-solving techniques in C++
Features
Solves standard 9×9 Sudoku puzzles.
Uses recursion and backtracking.
Accepts user input from the console.
Displays the solved Sudoku grid.
Detects puzzles with no valid solution.
How the Program Works
1. Input Sudoku Grid

The user enters a 9×9 Sudoku puzzle. Empty cells are represented by 0.

Example Input:

5 3 0 0 7 0 0 0 0
6 0 0 1 9 5 0 0 0
0 9 8 0 0 0 0 6 0
8 0 0 0 6 0 0 0 3
4 0 0 8 0 3 0 0 1
7 0 0 0 2 0 0 0 6
0 6 0 0 0 0 2 8 0
0 0 0 4 1 9 0 0 5
0 0 0 0 8 0 0 7 9
2. Validation Check

The program checks whether a number can be safely placed in an empty cell by ensuring:

The number does not already exist in the same row.
The number does not already exist in the same column.
The number does not already exist in the corresponding 3×3 subgrid.
3. Backtracking Algorithm

The solver:

Finds an empty cell.
Tries numbers from 1 to 9.
Places a valid number.
Recursively solves the remaining puzzle.
If no solution is found, it backtracks and tries another number.
4. Output

If a solution exists, the completed Sudoku grid is displayed.

Example Output:

5 3 4 6 7 8 9 1 2
6 7 2 1 9 5 3 4 8
1 9 8 3 4 2 5 6 7
8 5 9 7 6 1 4 2 3
4 2 6 8 5 3 7 9 1
7 1 3 9 2 4 8 5 6
9 6 1 5 3 7 2 8 4
2 8 7 4 1 9 6 3 5
3 4 5 2 8 6 1 7 9
Technologies Used
C++
Standard Input/Output Library (iostream)
Recursion
Backtracking Technique
Functions Description
isSafe()

Checks whether a number can be placed in a specific cell according to Sudoku rules.

solveSudoku()

Uses recursion and backtracking to solve the Sudoku puzzle.

printGrid()

Prints the solved Sudoku grid to the console.

Compilation and Execution
Compile
g++ sudoku_solver.cpp -o sudoku_solver
Run
./sudoku_solver

Advantages:

Efficient for standard Sudoku puzzles.
Demonstrates recursion and backtracking concepts.
Easy to understand and implement.
No external libraries required.

Limitations:

Works only for 9×9 Sudoku puzzles.
Input validation is limited.
Performance may decrease for extremely complex puzzles.
Future Improvements
Graphical User Interface (GUI).
Support for different Sudoku sizes.
Random Sudoku puzzle generator.
Faster solving techniques and optimizations.
File input/output support.

Conclusion:


This Sudoku Solver project is a practical implementation of the Backtracking Algorithm in C++. It efficiently solves Sudoku puzzles by recursively exploring possible solutions and backtracking whenever an invalid state is reached. The project helps students understand recursion, algorithm design, and constraint satisfaction problems.
