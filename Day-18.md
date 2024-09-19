## Random HackerRank Problem 
## Special Number 2
A number is said to be special if in its binary representation (with no leading zeroes), it has more ones than zeroes. Thus, 15 is Special, but 16 is Not Special. Given an input n, compute how many special numbers are there between 1 and N. Print that count as the output.

Input Format

An Integer n

Constraints

n <=10000

Output Format

Count of special numbers between 1 and n.

Sample Input 0

5
Sample Output 0

3
Explanation 0

Numbers 1 3 5 are special because in their binary representation we have more 1's than 0's. 1 - 1 3 - 11 5 - 101

##
## Solution
```
N=int(input())
sp=0
for i in range(0,N+1):
    B=bin(i)[2:]
    OC=B.count("1")
    ZO=B.count("0")
    if OC>ZO:
        sp+=1
print(sp)
```
