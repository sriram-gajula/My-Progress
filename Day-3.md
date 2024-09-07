# DAY-3
## Remaining String Accenture
Given a string with only English alphabets, for each alphabet print how many more of the same alphabets are to its right.

For example if the input is: abaa

Output should be

2 0 1 0

because for first a there are two more a's, but for b there is no more b, then for next a there is one more a and for last a there is nothing.

Input Format

string with English alphabets

Constraints

length|string|<=10^5

Output Format

for each location print how many same alphabets are after it.

Sample Input 0

abbaa
Sample Output 0

2 1 0 1 0
Explanation 0

After first a there are two more a's

After first b there is one more b

After second b there is no more b

After second a there is one more a

After last a there is no more a.

```
A=input()
for i in range(len(A)):
    a=A[i+1:].count(A[i])
    print(a,end=" ")

```

## Accent Alice and Song
```
s=input()
k=int(input())
max_count=0
for i in range(len(s)-k+1):
    word=s[i:k+i]
    count=word.count("a")
    if count>max_count:
        max_count=count
print(count)
```

## Primes with Twist-[Accenture]

Given an integer n(1<=n<=10^4), you need to count the numbers, xi < n, which are co-prime to 'n', i.e.gcd(x,n)=1

Formally, given n, you need to find f(n) = [{x

Input Format

input1: the integer 'n'

Constraints

-

Output Format

return the count of the number of co-primes of 'n'.

Sample Input 0

4
Sample Output 0

2
Explanation 0

GCD of 4 with 1,3 are both 1. So there are two such numbers. Ans = 2.

```
def Gcd(n):
    result = n
    p=2
    while p*p <=n:
        if n%p==0:
            while n%p==0:
                n//=p
            result-=result//p
        p+=1
    if n>1:
        result-=result//n
    return result
n=int(input().strip())
print(Gcd(n))

```
