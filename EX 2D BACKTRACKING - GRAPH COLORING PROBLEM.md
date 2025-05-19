# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 15/03/25
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Given a graph with V vertices and m colors.

2. Start coloring from vertex 0.

3. For each vertex:

4. Try all colors 1 to m:

5. If no adjacent vertex has the same color, assign it.

6. Recurse to color the next vertex.

7. If coloring fails, backtrack.

8. If all vertices are colored, print the color assignment.

9. Else, print "No solution exists".
    
## Program:
Program to implement Graph Coloring Problem using backtracking.

Developed by: Vidhyasri k

Register Number: 212222230170

```
class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.Graph=[[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False  
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=c
        return False
     
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColouringUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end=' ')
        print()
        return True
```
## Output:
![image](https://github.com/user-attachments/assets/888235ab-54b0-4be9-bb1d-337f94418339)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
