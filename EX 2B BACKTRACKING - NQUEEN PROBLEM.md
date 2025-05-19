# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 08/03/25
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm
1. Start

2. Create an N x N board initialized with 0s.

3. Define solveNQUtil(board, col):

4. If col >= N, all queens are placed → return True.

5. For each row i from 0 to N-1:

6. If placing a queen at (i, col) is safe:

7. Place queen (board[i][col] = 1)

8. Recursively call solveNQUtil(board, col + 1)

9. If success, return True

10. Else, backtrack (board[i][col] = 0)

11. In isSafe(board, row, col):

12. Check left side of row, upper-left diagonal, and lower-left diagonal for conflicts.

13. Call solveNQUtil(board, 0):

14. If True, print board

15. Else, print "No solution"

16. End

## Program:
Program to implement N-Queen problem using backtracking.

Developed by: Dhivyapriya R

Register Number: 212222230032

```
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if(col>=N):
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if(solveNQUtil(board,col+1)):
                return True
            board[i][col]=0
    return False
    
def solveNQ():
    board = [ [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0]]
 
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()
```

## Output:
![image](https://github.com/user-attachments/assets/7dcde4df-ab66-4027-b41d-bfa89694bd30)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
