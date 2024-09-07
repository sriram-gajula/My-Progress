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
