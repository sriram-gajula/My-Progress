# Day-5
## Electrostatics[Accenture]
Doug is fond of change, every now and then he tries to do new things. This time, he caught up with a rod comprising of negative(N) and positive(P) charges. He is asked to calculate the maximum net electrostatic field possible in the region due to the rod.

Note: Assume, Electrostatic Field = Total Charge * 100

Input Format

input1: integer array denoting the magnitude of each charge

input2: String denoting nature of each charge, ith entry represents a sign of charge at ith location in input1

input3: No of charges it holds(length of input1)

Sample Input:

input1: 4 3 5 input2: PNP input3: 3

Constraints

_

Output Format

return the maximum electrostatic field possible in the rod.

sample output:

600

Sample Input 0

4 3 5
PNP
3
Sample Output 0

600

## Sloution 
```
n1=list(map(int,input().split()))
n2=input()
n3=int(input())
netcharge=0
for i in range(0,n3):
    if n2[i]=="P":
        netcharge+=n1[i]
    elif n2[i]=="N":
        netcharge-=n1[i]
print(netcharge*100)
```
