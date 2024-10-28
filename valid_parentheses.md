# Problem : Valid Parantheses

Link - https://leetcode.com/problems/valid-parentheses/description/

### Problem Statement:

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

#### Constraints:

1 <= s.length <= 104 \
s consists of parentheses only '()[]{}'.

#### Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

```
Example 1:

Input: s = "()"
Output: true


Example 2:

Input: s = "()[]{}"
Output: true


Example 3:

Input: s = "(]"
Output: false


Example 4:

Input: s = "([])"
Output: true
```

**Difficulty**: Easy  
**Tags**: Array, Stack

### Approach:

- **Time Complexity**: O(n)
- **Space Complexity**: O(n)
- This solution has a time complexity of 𝑂(𝑛), where 𝑛 n is the length of the string, since we iterate through it once, and a space complexity of 𝑂(𝑛) due to the stack.


### Solution (Python):

```python
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        # Dictionary to hold matching pairs
        matching_bracket = {')': '(', ']': '[', '}': '{'}
        stack = []

        for char in s:
            # If it's a closing bracket
            if char in matching_bracket:
                # Check if the stack is empty or the top element doesn't match
                if not stack or stack[-1] != matching_bracket[char]:
                    return False
                stack.pop()
            else:
                # If it's an opening bracket, push onto the stack
                stack.append(char)

        # If stack is empty, all brackets were matched
        return not stack
```
