# Problem : Roman to Integer

Link - https://leetcode.com/problems/roman-to-integer/description/

### Problem Statement:

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

```Symbol Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. \
X can be placed before L (50) and C (100) to make 40 and 90. \
C can be placed before D (500) and M (1000) to make 400 and 900. \
Given a roman numeral, convert it to an integer.

```
Example 1:

Input: s = "III"
Output: 3
Explanation: III = 3.

Example 2:

Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.

Example 3:

Input: s = "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.

```

#### Constraints:

1 <= s.length <= 15 \
s contains only the characters ('I', 'V', 'X', 'L', 'C', 'D', 'M'). \
It is guaranteed that s is a valid roman numeral in the range [1, 3999].

**Difficulty**: Easy  
**Tags**: Hash Table, string, Math

### Approach:

1. Index Bounds: if index + 1 < len(s) ensures we don't access beyond the valid range of the string. \
2. Valid Comparison: dic[s[index + 1]] properly fetches the integer value from the dictionary for comparison. \
3. Correct Subtraction Rule: The condition if dic[i] < dic[s[index + 1]] follows the Roman numeral rule for subtracting smaller values placed before larger values.

#### The time complexity of this approach is O(n), where n is the length of the Roman numeral string, and the space complexity is O(1), as only a fixed amount of extra space is used regardless of the input size.

### Solution (Python):

```python
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        dic = {
            "I": 1,
            "V": 5,
            "X": 10,
            "L": 50,
            "C": 100,
            "D": 500,
            "M": 1000
        }

        result = 0

        for index, i in enumerate(s):
            # Check if the next element exists before accessing it
            if index + 1 < len(s) and dic[i] < dic[s[index + 1]]:
                result -= dic[i]  # Subtract if the current value is less than the next one
            else:
                result += dic[i]  # Otherwise, add the value

        return result
```
