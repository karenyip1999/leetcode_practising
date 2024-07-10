## Task ✍
The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this:

```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: ```"PAHNAPLSIIGYIR"```

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows);

#### Example 1:
Input: ```s = "PAYPALISHIRING", numRows = 3```

Output: ```"PAHNAPLSIIGYIR"```

#### Example 2:
Input: ```s = "PAYPALISHIRING", numRows = 4```

Output: ```"PINALSIGYAHRPI"```

Explanation:
```
P     I    N
A   L S  I G
Y A   H R
P     I
```
#### Example 3:
Input: ```s = "A", numRows = 1```

Output: ```"A"```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on how to solve this task was to iterate through s and add each character to a string.

The way I have decided to approach this task is to do this using an array, where I would later for loop through it and concatenate the strings together to produce one string.
