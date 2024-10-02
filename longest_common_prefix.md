# Problem : Longest Common Prefix

Link - https://leetcode.com/problems/longest-common-prefix/description/

### Problem Statement:

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

```
Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"

Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

#### Constraints:

Constraints:

1 <= strs.length <= 200 \
0 <= strs[i].length <= 200 \
strs[i] consists of only lowercase English letters.

**Difficulty**: Easy  
**Tags**: String, Trie

### Approach:

1. Initial check: If the input list is empty, we return "".
2. Prefix assumption: We start by assuming the first string is the common prefix.
3. Iterate through each string: For every subsequent string in the list, we compare it with the current prefix. If the prefix is not found at the start of the current string, we reduce the prefix by chopping off the last character (i.e., prefix = prefix[:-1]) until we find a match.
4. Early return: If at any point the prefix becomes empty, we return "" since no common prefix exists.
   Final return: After checking all strings, whatever is left in prefix is the longest common prefix.

#### The time complexity is O(S), where S is the sum of the lengths of all strings in the list. In the worst case, we compare each character of each string.

### Solution (Python):

```python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if not strs:
            return ""

        # Assume the first string is the common prefix
        prefix = strs[0]

        # Iterate over the remaining strings in the list
        for string in strs[1:]:


            while string[:len(prefix)] != prefix:
                prefix = prefix[:-1]

                if not prefix:
                    return ""

        return prefix
```
