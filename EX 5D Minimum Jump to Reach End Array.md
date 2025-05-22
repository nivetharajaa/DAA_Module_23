# EX 5D Minimum Jump to Reach End Array
## DATE: 19.04.2025
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.

## Algorithm
 1. If the first element is 0 or the array is empty, return infinity because you can't move.
2. Create an array jumps where each element represents the minimum jumps needed to reach that position.
3. For each position, check if you can jump from any previous position that can reach it and update the jumps accordingly.
4. For each valid jump, keep track of the minimum jumps needed.
5. Return the minimum number of jumps to reach the last position.   

## Program:
```
/*
To implement the program to finding the minimum number of jumps needed to reach end of the array.

Developed by: Nivetha A
Register Number: 212222230101
*/
```
```
def minJumps(arr, l, h):
    #Start here
    if (h == l):
        return 0
    if (arr[l] == 0):
        return float('inf')
    min = float('inf')
    for i in range(l + 1, h + 1):
        if (i < l + arr[l] + 1):
            jumps = minJumps(arr, i, h)
            if (jumps != float('inf') and
                       jumps + 1 < min):
                min = jumps + 1
    return min
    #End here
arr = []
n = int(input()) 
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr, 0, n-1))
 ```
## Output:
![image](https://github.com/user-attachments/assets/991496c8-636d-459b-baf0-5adf9a6ff3f7)

## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
