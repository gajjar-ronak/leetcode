# Problem : Display the First Three Rows

Link - https://leetcode.com/problems/display-the-first-three-rows/description/

### Problem Statement:

```DataFrame: employees
+-------------+--------+
| Column Name | Type   |
+-------------+--------+
| employee_id | int    |
| name        | object |
| department  | object |
| salary      | int    |
+-------------+--------+
Write a solution to display the first 3 rows of this DataFrame.
```

```
Example 1:

Input:
DataFrame employees
+-------------+-----------+-----------------------+--------+
| employee_id | name      | department            | salary |
+-------------+-----------+-----------------------+--------+
| 3           | Bob       | Operations            | 48675  |
| 90          | Alice     | Sales                 | 11096  |
| 9           | Tatiana   | Engineering           | 33805  |
| 60          | Annabelle | InformationTechnology | 37678  |
| 49          | Jonathan  | HumanResources        | 23793  |
| 43          | Khaled    | Administration        | 40454  |
+-------------+-----------+-----------------------+--------+

Output:
+-------------+---------+-------------+--------+
| employee_id | name    | department  | salary |
+-------------+---------+-------------+--------+
| 3           | Bob     | Operations  | 48675  |
| 90          | Alice   | Sales       | 11096  |
| 9           | Tatiana | Engineering | 33805  |
+-------------+---------+-------------+--------+

Explanation:
Only the first 3 rows are displayed.
```

### Solution (Python):

```Python
import pandas as pd

def selectFirstRows(employees: pd.DataFrame) -> pd.DataFrame:
    df = pd.DataFrame(employees)
    first_three_rows = df.head(3)

    return first_three_rows

```
