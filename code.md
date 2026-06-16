#include <iostream>
using namespace std;

const int SIZE = 9;

void displayGrid(int grid[SIZE][SIZE])
{
    cout << "\n=================================\n";
    cout << "         SUDOKU SOLVED\n";
    cout << "=================================\n\n";

    for(int i = 0; i < SIZE; i++)
    {
        if(i % 3 == 0)
            cout << "+-------+-------+-------+\n";

        for(int j = 0; j < SIZE; j++)
        {
            if(j % 3 == 0)
                cout << "| ";

            cout << grid[i][j] << " ";
        }

        cout << "|\n";
    }

    cout << "+-------+-------+-------+\n";
}


bool isRowSafe(int grid[SIZE][SIZE], int row, int num)
{
    for(int col = 0; col < SIZE; col++)
    {
        if(grid[row][col] == num)
            return false;
    }
    return true;
}

// Check if number exists in column
bool isColumnSafe(int grid[SIZE][SIZE], int col, int num)
{
    for(int row = 0; row < SIZE; row++)
    {
        if(grid[row][col] == num)
            return false;
    }
    return true;
}


bool isBoxSafe(int grid[SIZE][SIZE], int startRow, int startCol, int num)
{
    for(int row = 0; row < 3; row++)
    {
        for(int col = 0; col < 3; col++)
        {
            if(grid[row + startRow][col + startCol] == num)
                return false;
        }
    }
    return true;
}

// Check valid placement
bool isSafe(int grid[SIZE][SIZE], int row, int col, int num)
{
    return isRowSafe(grid, row, num) &&
           isColumnSafe(grid, col, num) &&
           isBoxSafe(grid,
                     row - row % 3,
                     col - col % 3,
                     num);
}


bool findEmptyCell(int grid[SIZE][SIZE], int &row, int &col)
{
    for(row = 0; row < SIZE; row++)
    {
        for(col = 0; col < SIZE; col++)
        {
            if(grid[row][col] == 0)
                return true;
        }
    }
    return false;
}


bool solveSudoku(int grid[SIZE][SIZE])
{
    int row, col;

    if(!findEmptyCell(grid, row, col))
        return true;

    for(int num = 1; num <= 9; num++)
    {
        if(isSafe(grid, row, col, num))
        {
            grid[row][col] = num;

            if(solveSudoku(grid))
                return true;

            grid[row][col] = 0;
        }
    }

    return false;
}


void showPuzzle(int grid[SIZE][SIZE])
{
    cout << "\n=================================\n";
    cout << "         SUDOKU PUZZLE\n";
    cout << "=================================\n\n";

    for(int i = 0; i < SIZE; i++)
    {
        if(i % 3 == 0)
            cout << "+-------+-------+-------+\n";

        for(int j = 0; j < SIZE; j++)
        {
            if(j % 3 == 0)
                cout << "| ";

            if(grid[i][j] == 0)
                cout << ". ";
            else
                cout << grid[i][j] << " ";
        }

        cout << "|\n";
    }

    cout << "+-------+-------+-------+\n";
}

int main()
{
    int grid[SIZE][SIZE];

    cout << "=================================\n";
    cout << "      SUDOKU SOLVER SYSTEM\n";
    cout << "=================================\n\n";

    cout << "Enter Sudoku Puzzle\n";
    cout << "(Use 0 for empty cells)\n\n";

    for(int row = 0; row < SIZE; row++)
    {
        for(int col = 0; col < SIZE; col++)
        {
            cin >> grid[row][col];
        }
    }

    showPuzzle(grid);

    cout << "\nSolving Sudoku...\n";

    if(solveSudoku(grid))
    {
        displayGrid(grid);

        cout << "\nPuzzle Solved Successfully!\n";
    }
    else
    {
        cout << "\nNo Solution Exists For This Puzzle!\n";
    }

    return 0;
}
