## EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 04/03/25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm
1. Start

2. Create a solution matrix sol of size N x N, initialized with 0s.

3. Define a recursive function solveMazeUtil(maze, x, y, sol):

4. If (x, y) is the destination and is safe, mark it as 1 and return True.

5. If (x, y) is a valid move (within bounds and value is 1):

6. Mark sol[x][y] = 1

7. Move right: call solveMazeUtil(x, y + 1)

8. If that fails, move down: call solveMazeUtil(x + 1, y)

9. If both fail, backtrack: mark sol[x][y] = 0 and return False

10. Call solveMazeUtil(0, 0, sol).

11. If a path is found, print the sol matrix; otherwise, print "No solution".

12. End
    
## Program:

Program to implement Rat in a Maze.

Developed by: Dhivyapriya R

Register Number: 212222230032

```

N = 4

def printSolution(sol):
    for row in sol:
        print(" ".join(map(str, row)))

def isSafe(maze, x, y):
    return 0 <= x < N and 0 <= y < N and maze[x][y] == 1

def solveMaze(maze):
    sol = [[0 for _ in range(N)] for _ in range(N)]
    
    if not solveMazeUtil(maze, 0, 0, sol):
        print("Solution doesn't exist")
        return False
    
    printSolution(sol)
    return True

def solveMazeUtil(maze, x, y, sol):
    if x == N - 1 and y == N - 1:  # Destination reached
        sol[x][y] = 1
        return True
    
    if isSafe(maze, x, y):
        sol[x][y] = 1  # Mark cell as part of the path
        
        # Move right
        if solveMazeUtil(maze, x, y + 1, sol):
            return True
        
        # Move down
        if solveMazeUtil(maze, x + 1, y, sol):
            return True
        
        sol[x][y] = 0  # Backtrack if no path is found
        return False

if __name__ == "__main__":
    maze = [[1, 0, 0, 0],
            [1, 1, 0, 1],
            [0, 1, 0, 0],
            [1, 1, 1, 1]]

    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/59a6fbd4-dbd7-4133-abf7-278cccf6ccfc)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
