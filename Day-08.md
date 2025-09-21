## Balanced Parantheses!
Problem Description

Given a string A consisting only of '(' and ')'.

You need to find whether parantheses in A is balanced or not ,if it is balanced then return 1 else return 0.

Problem Constraints
1 <= |A| <= 105

Input Format
First argument is an string A.

Output Format
Return 1 if parantheses in string are balanced else return 0.

Example Input
Input 1:

 A = "(()())"
Input 2:

 A = "(()"

Example Output
Output 1:

 1
Output 2:

 0

Example Explanation
Explanation 1:

 Given string is balanced so we return 1
Explanation 2:

 Given string is not balanced so we return 0

## Solution 

```
def solveQ(A):
    stk=[]
    for a in A:
        if(a=='('):
            stk.append(a)
            continue
        if(len(stk)==0):
            return False
        if(a==')'):
            x=stk[-1]
            stk.pop(-1)
            if(x!='('):
                return False
    if(len(stk)==0):
        return True
    return False
        
class Solution:
    # @param A : string
    # @return an integer
    def solve(self, A):
        if(solveQ(A)==False):
            return 0
        return 1
```


## Problem 2
## 392. Is Subsequence
Given two strings s and t, return true if s is a subsequence of t, or false otherwise.

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

 

Example 1:

Input: s = "abc", t = "ahbgdc"
Output: true
Example 2:

Input: s = "axc", t = "ahbgdc"
Output: false
 

Constraints:

0 <= s.length <= 100
0 <= t.length <= 104
s and t consist only of lowercase English letters.
 

Follow up: Suppose there are lots of incoming s, say s1, s2, ..., sk where k >= 109, and you want to check one by one to see if t has its subsequence. In this scenario, how would you change your code?

## Solution

```
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        #p=pointer
        s_p,t_p=0,0
        while s_p<len(s) and t_p<len(t):
            if s[s_p]==t[t_p]:
                s_p+=1
            t_p+=1
        return s_p==len(s)
```
