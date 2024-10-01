# Problem : Palindrome Number

Link - https://leetcode.com/problems/palindrome-number/description/

### Problem Statement:

Given an integer x, return true if x is a
palindrome
, and false otherwise.

```
Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

```

**Difficulty**: Easy  
**Tags**: Math

### Approach:

Let's say x = 121.

Convert to string: s = "121". \
Reverse the string: s[::-1] = "121". \
Compare: "121" == "121", which is True. \
The function returns True, so 121 is a palindrome.

#### Time Complexity: O(d), where d is the number of digits in the integer x.

#### Space Complexity: O(d), due to the storage of the original and reversed string.

### Solution (Python):

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        s = str(x)
        return s == s[::-1]
```
