##  EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 11/03/25

## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.

## Algorithm
1. Given an array a and a target sum.

2. Start from index 0 with initial sum 0.

3. For each element: Exclude the current element and recurse.

4. Include the current element and add its value to the sum, then recurse.

5. If current sum equals target, return True.

6. If end of array is reached or sum exceeds target, return False.

7. If any path returns True, a subset exists.
   
## Program:
Program to implement Subset sum problem.

Developed by: Dhivyapriya R

Register Number: 212222230032

```
def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if sum > target:
        return False
    if sum==target:
        return True
        
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```

## Output:

![image](https://github.com/user-attachments/assets/8fc44eeb-b65f-4316-a4aa-b8424d60fb8f)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
