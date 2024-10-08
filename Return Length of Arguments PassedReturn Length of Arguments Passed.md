# Problem : Return Length of Arguments Passed

Link - https://leetcode.com/problems/return-length-of-arguments-passed/description/

### Problem Statement:

Write a function argumentsLength that returns the count of arguments passed to it.

```
Example 1:

Input: args = [5]
Output: 1
Explanation:
argumentsLength(5); // 1

One value was passed to the function so it should return 1.

Example 2:

Input: args = [{}, null, "3"]
Output: 3
Explanation:
argumentsLength({}, null, "3"); // 3

Three values were passed to the function so it should return 3.
```

#### Constraints:

args is a valid JSON array \
0 <= args.length <= 100

**Difficulty**: Easy  
**Tags**: Array

### Approach:

1. return args length.

#### The time complexity is O(1)

### Solution (Javascript):

```Javascript
var argumentsLength = function(...args) {
    return args.length
};
```
