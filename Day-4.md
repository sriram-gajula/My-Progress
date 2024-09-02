# DAY-4 
## Pattern Half diamond using numbers
Given two numbers as input, print the half diamond as shown Input 3 4 Output 3 44 555 6666 555 44 3

Input : 4 5 Output: 4 55 666 7777 88888 7777 666 55 4

Input Format

Two numbers less than 10

Constraints

input is less than 10

Output Format

half diamond pattern

Sample Input 0

3 4
Sample Output 0

3
44
555
6666
555
44
3
Sample Input 1

4 5
Sample Output 1

4
55
666
7777
88888
7777
666
55
4

## Solution
```
def print_diamond(a, b):
    current_value = a
    for i in range(1, b + 1):
        print(str(current_value) * i)
        current_value += 1
    current_value -= 2
    for i in range(b - 1, 0, -1):
        print(str(current_value) * i)
        current_value -= 1
a, b = map(int, input().split())
print_diamond(a, b)


```


## Pascal's Triangle 
Given a non-negative integer numRows, generate the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it.

Example:

image

Input: 5 Output: [ [1], [1,1], [1,2,1], [1,3,3,1], [1,4,6,4,1] ]

Input Format

3

Constraints

1 <= n <= 10000

Output Format

1

1 1

1 2 1

Sample Input 0

3
Sample Output 0

1
1 1
1 2 1

## Solution
```
def p_triangle(Rows):
    triangle = []
    for i in range(Rows):
        row = [1]*(i + 1)
        row[1:-1]=[triangle[i-1][j-1]+triangle[i-1][j] for j in range(1, i)]
        triangle.append(row)
    for row in triangle:
        print(" ".join(map(str, row)))
Rows = int(input())
p_triangle(Rows)

```
​
