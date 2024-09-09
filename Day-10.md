# Day-10
## 228. Summary Ranges
You are given a sorted unique integer array nums.

A range [a,b] is the set of all integers from a to b (inclusive).

Return the smallest sorted list of ranges that cover all the numbers in the array exactly. That is, each element of nums is covered by exactly one of the ranges, and there is no integer x such that x is in one of the ranges but not in nums.

Each range [a,b] in the list should be output as:

"a->b" if a != b
"a" if a == b
 

Example 1:

Input: nums = [0,1,2,4,5,7]
Output: ["0->2","4->5","7"]
Explanation: The ranges are:
[0,2] --> "0->2"
[4,5] --> "4->5"
[7,7] --> "7"
Example 2:

Input: nums = [0,2,3,4,6,8,9]
Output: ["0","2->4","6","8->9"]
Explanation: The ranges are:
[0,0] --> "0"
[2,4] --> "2->4"
[6,6] --> "6"
[8,9] --> "8->9"
 

Constraints:

0 <= nums.length <= 20
-231 <= nums[i] <= 231 - 1
All the values of nums are unique.
nums is sorted in ascending order.
## 
## Solution
```
class Solution:
    def summaryRanges(self, nums: List[int]) -> List[str]:
        ans =[]
        i= 0
        while i < len(nums):
            start = nums[i]
            while i < len(nums)-1 and nums[i]+1 == nums[i+1]:
                i +=1
            if start != nums[i]:
                ans.append(str(start)+'->'+str(nums[i]))
            else:
                 ans.append(str(nums[i]))
            i +=1
        return ans
```
## Problem 2 
## 771. Jewels and Stones
You're given strings jewels representing the types of stones that are jewels, and stones representing the stones you have. Each character in stones is a type of stone you have. You want to know how many of the stones you have are also jewels.

Letters are case sensitive, so "a" is considered a different type of stone from "A".

 

Example 1:

Input: jewels = "aA", stones = "aAAbbbb"
Output: 3
Example 2:

Input: jewels = "z", stones = "ZZ"
Output: 0
 

Constraints:

1 <= jewels.length, stones.length <= 50
jewels and stones consist of only English letters.
All the characters of jewels are unique.
## 
## Solution
```
class Solution:
    def numJewelsInStones(self, jewels: str, stones: str) -> int:
        s=set(jewels) #set we can acgive O(n+m)
        count=0
        for stone in stones:
            if stone in s:
                count+=1
        return count 
        
        
```
