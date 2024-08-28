# DAY -2
## Majority Element

Problem Description
 
 Given an array of size N, find the majority element. The majority element is the element that appears more than floor(N/2) times.
You may assume that the array is non-empty and the majority element always exist in the array.

Problem Constraints
1 <= |A| <= 106
1 <= Ai <= 109

Input Format
The first argument is an integer array A.

Output Format
Return the majority element.

Example Input
A = [2, 1, 2]

Example Output
2

Example Explanation
2 occurs 2 times which is greater than 3/2.
```
class Solution:
    def majorityElement(self, A):
        candidate = None
        count = 0
        for num in A:
            if count == 0:
                candidate = num
                count = 1
            elif num == candidate:
                count += 1
            else:
                count -= 1
        return candidate
if __name__ == "__main__":
    obj = Solution()
    A = list(map(int, input().split()))
    print(obj.majorityElement(A))
```

## Max Sum Contiguous Subarray

Problem Description
 
Find the contiguous subarray within an array, A of length N which has the largest sum.

Problem Constraints
1 <= N <= 106
-1000 <= A[i] <= 1000

Input Format
The first and the only argument contains an integer array, A.

Output Format
Return an integer representing the maximum possible sum of the contiguous subarray.

Example Input
Input 1:
A = [1, 2, 3, 4, -10]
Input 2:
A = [-2, 1, -3, 4, -1, 2, 1, -5, 4]

Example Output
Output 1:
10
Output 2:
6

Example Explanation
Explanation 1:
The subarray [1, 2, 3, 4] has the maximum possible sum of 10.
Explanation 2:
The subarray [4,-1,2,1] has the maximum possible sum of 6.

```
class Solution:
    def maxSubArray(self, A):
        maxSub=A[0]
        curSum=0
        for n in A :
            if curSum < 0:
                curSum=0
            curSum+=n
            maxSub=max(maxSub,curSum)
        return maxSub

```


## Acc sum xor
```
N = int(input())
arr =list(map(int,input().split()))
even=[]
odd,evn=0,0
for i in range(0,len(arr)):
    if i%2==0:
        even.append(arr[i])
    else:
        odd= odd+arr[i]
for j in even :
    evn=evn^j
print(odd-evn)
```
## Acc Snakewatergun
```
n,s,i,arr=int(input()),input(),0,[]
while(i<len(s)):
    if(s[i]=="w"):
        arr.append("water")
        i+=5
    elif(s[i]=="g"):
        arr.append("gun")
        i+=3
    else:
        arr.append("snake")
        i+=5
count=0
for j in range(0,2*n,2):
    if (arr[j]=="water" and arr[j+1]=="gun"):
        count+=1
    elif (arr[j]=="snake" and arr[j+1]=="water"):
        count+=1
    elif (arr[j]=="gun" and arr[j+1]=="snake"):
        count+=1
print(count)
```
