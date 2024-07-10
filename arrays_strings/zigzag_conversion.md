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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I made a base case using an if statement to check if numRows was equal to 1 or if numRows was greater than the length of s
2. If so, the whole of s is returned as iterating through it is redundant
3. I created a string array called zigzag that was the length of numRows as this simulates the rows of the zigzag pattern
4. I used ```Arrays.fill()``` so that each element of the array started as empty strings
5. I created a variable called i and initiated it to 0 as this would keep track of the current index when iterating through s
6. I used a while loop to iterate through s whilst i was less than the length of s
7. Inside of the while loop, I used a for loop to simulate the downwards pattern of the zigzag that continued whilst j was less than numRows and i was still less than the length of s
8. I assigned to the current element in the zigzag array, the current element from s added onto the end of the current element from the zigzag array
9. i is incremented by 1
10. Another for loop is used inside of the while loop that started at numRows -2 as this is now going backwards for the upwards pattern of the zigzag
11. I assigned to the current element in the zigzag array, the current element from s added onto the end of the current element from the zigzag array
12. i is incremented by 1
13. Outside of the while loop, I created a variable called conversion and initiated that to an empty string as this is what will hold the final pattern
14. I used a for loop to iterate through the zigzag array
15. I added the current element from zigzag onto the end of conversion and assigned this to conversion
16. Outside of the for loop, conversion is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public String convert(String s, int numRows) {        
        if(numRows == 1 || numRows >= s.length()){
            return s;
        }
        
        String[] zigzag = new String[numRows]; 
        Arrays.fill(zigzag, "");

        int i = 0;
        while(i < s.length()){
            for(int j = 0; j < numRows && i < s.length(); j ++){
                zigzag[j] = zigzag[j] + s.charAt(i);
                i++;
            }
            for(int k = numRows - 2; k > 0 && i < s.length(); k --){
                zigzag[k] = zigzag[k] + s.charAt(i);
                i++;
            }
        }
        
        String conversion = "";
        for(int l = 0; l < zigzag.length; l++){
            conversion += zigzag[l];
        }
        return conversion;
    }
}
```
