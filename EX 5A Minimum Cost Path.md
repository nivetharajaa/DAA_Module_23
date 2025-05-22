# EX 5A Minimum Cost Path
## DATE:08.04.2025
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.
## Algorithm
1. Make a table to store minimum costs to reach each cell.
2. Set the starting cell's cost as the first cost.
3. Fill the first row and first column by adding costs from left and top.
4. For other cells, choose the smallest cost from left, top, or diagonal, and add the current cell's cost.
5. The last cell will have the minimum total cost to reach the end. 

## Program:
```
/*
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by: Nivetha A
Register Number: 212222230101
*/
```
```
import sys
V = 5
INF = sys.maxsize
def minimumCostSimplePath(u, destination, visited, graph):
    ########  Add your code here ##############
    if (u == destination):
        return 0
    visited[u] = 1
    ans = INF
    for i in range(V):
        if (graph[u][i] != INF and not visited[i]):
            curr = minimumCostSimplePath(i, destination,visited, graph)
            if (curr < INF):
                ans = min(ans, graph[u][i] + curr)
    visited[u] = 0
    return ans

if __name__=="__main__":
    graph = [[INF for j in range(V)]
                  for i in range(V)]
    visited = [0 for i in range(V)]
    graph[0][1] = -1
    graph[0][3] = 1
    graph[1][2] = -2
    graph[2][0] = -3
    graph[3][2] = -1
    graph[4][3] = 2
    s = 0
    t = 2
    visited[s] = 1
    print(minimumCostSimplePath(s, t, visited, graph))
  ```
## Output:
![image](https://github.com/user-attachments/assets/7b22f71b-376f-49ae-8fdf-be78a8395561)

## Result:
Thus the above program was executed successfully for finding the minimum cost.
