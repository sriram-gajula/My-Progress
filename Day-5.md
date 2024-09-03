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

## TCS NINJA MIXED SERIES 

Consider the following series: 1,1,2,3,4,9,8,27,16,81,32,243,64,729,128,2187... This series is a mixture of 2 series – all the odd terms in this series form a geometric series and all the even terms form yet another geometric series. Write a program to find the Nth term in the series. The value N in a positive integer that should be read from STDIN. The Nth term that is calculated by the program should be written to STDOUT. Other than value of n th term,no other character / string or message should be written to STDOUT. For example , if N=16, the 16th term in the series is 2187, so only value 2187 should be printed.

Input Format

16

Constraints

Input is less than 30

Output Format

2187

Sample Input 0

10
Sample Output 0

81
Explanation 0

The tenth term is composed of the series 1 3 9 27 81. So the term is 81.

```
def find_nth_term(N):
    if N % 2 == 1:
        k = (N + 1) // 2
        term = 2 ** (k - 1)
    else:
        k = N // 2
        term = 3 ** (k - 1)
    return term
N = int(input())
print(find_nth_term(N))


```

## Placement Season Begins_[Accenture]

The placement season has begun in a college. There are N number of students standing outside an interview room in a line. It is given that a person who goes in first has higher chances of getting selected.

Each student has a number associated with them known as the problem-sloving capability(PSC). The higher the capability the higher the chances of selection. Now, each student wants to know the number of students ahead of him/her who have more problem-sloving capability than him/her.

Find this number for each student.

Input Format

input1: An integer N, which denotes the number of students present.

input2: An array of size N, denoting the problem-sloving capability of the students.

Constraints

_

Output Format

An array of size N denoting the required answer for each student.

Sample Input 0

5 7 9 4 11 16 8
Sample Output 0

0 0 0 3 0 0 3
Explanation 0

There are 0 persons before first one, 0 before second who have more than 7, but 3 people before one who has a value 4 and so on.


```
N=input()
arr=[int(num) for num in N.split()]
result=[]
for i in range(len(arr)):
    count=0
    for j in range(i):
        if arr[j]>arr[i]:
            count+=1
    result.append(count)
print(" ".join(map(str, result)))

```
## TCS_24_Oct2020_Slot1[Q2]

There is a JAR full of candies for sale at a mall counter. JAR has the capacity N, that is JAR can contain maximum N candies when JAR is full. At any point of time. JAR can have M number of Candies where M<=N. Candies are served to the customers. JAR is never remain empty as when last k candies are left. JAR if refilled with new candies in such a way that JAR get full. Write a code to implement above scenario. Display JAR at counter with available number of candies. Input should be the number of candies one customer can order at point of time. Update the JAR after each purchase and display JAR at Counter. Output should give number of Candies sold and updated number of Candies in JAR. If Input is more than candies in JAR, return: “INVALID INPUT”

Given, N=10, where N is NUMBER OF CANDIES AVAILABLE K =< 5, where k is number of minimum candies that must be inside JAR ever.

Example 1:(N = 10, k =< 5)

Input Format

Enter No.ofcandies

Constraints

-

Output Format

Print no.of candies sold and no.of candies available

Sample Input 0

3
Sample Output 0

NUMBER OF CANDIES SOLD : 3
NUMBER OF CANDIES AVAILABLE : 7
Sample Input 1

0
Sample Output 1

INVALID INPUT
NUMBER OF CANDIES LEFT : 10
Sample Input 2

6
Sample Output 2

NUMBER OF CANDIES SOLD : 6
NUMBER OF CANDIES AVAILABLE : 10

```
N = 10
K = 5 
order = int(input())
if order <= 0 or order > N:
    print("INVALID INPUT")
    print("NUMBER OF CANDIES LEFT : " + str(N))
else:
    N -= order
    print("NUMBER OF CANDIES SOLD : " + str(order))
    if N < K:
        N = 10
        print("NUMBER OF CANDIES AVAILABLE : " + str(N))
    else:
        print("NUMBER OF CANDIES AVAILABLE : " + str(N))

```
