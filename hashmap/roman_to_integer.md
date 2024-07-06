## Task ✍
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
For example, 2 is written as II in Roman numeral, just two ones added together. 

12 is written as XII, which is simply X + II. 

The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. 

However, the numeral for four is not IIII. 

Instead, the number four is written as IV. 

Because the one is before the five we subtract it making four. 

The same principle applies to the number nine, which is written as IX. 

There are six instances where subtraction is used:

* I can be placed before V (5) and X (10) to make 4 and 9. 
* X can be placed before L (50) and C (100) to make 40 and 90. 
* C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer.

#### Example 1:
Input: ```s = "III"```

Output: ```3```

Explanation: III = 3.

#### Example 2:
Input: ```s = "LVIII"```

Output: ```58```

Explanation: L = 50, V= 5, III = 3.

#### Example 3:
Input: ```s = "MCMXCIV"```

Output: ```1994```

Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I had initially thought that I could iterate through s backwards to check if the character after it would be lower than the current character.

I realised however that I could check this iterating through s normally, and if I found a character that was smaller than the next character, I could just decrement it from the total.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a new hashmap called numeralsMap and placed each roman numeral character into it
2. I created a variable called total and initiated it to 0 which would hold the integer conversion of the roman numerals
3. I used a for loop to iterate through s starting at index 0
4. Inside of the for loop, I created a variable called numeralChar that would hold the current character as I iterated through s
5. I used an if statement to check if i was smaller than the current length of s minus 1, and that the current character was less than the next character
6. If so, the current character value would be decremented from total
7. Else, the current character value was added to the total
8. Outside of the for loop, the total is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public int romanToInt(String s) {
        HashMap<Character, Integer> numeralsMap = new HashMap<>();
        numeralsMap.put('I', 1);
        numeralsMap.put('V', 5);
        numeralsMap.put('X', 10);
        numeralsMap.put('L', 50);
        numeralsMap.put('C', 100);
        numeralsMap.put('D', 500);
        numeralsMap.put('M', 1000);

        int total = 0;
    
        for(int i = 0; i < s.length(); i++){
            char numeralChar = s.charAt(i);
            if(i < s.length() - 1 && numeralsMap.get(numeralChar) < numeralsMap.get(s.charAt(i + 1))){
                total -= numeralsMap.get(numeralChar);
            }
            else{
                total += numeralsMap.get(numeralChar);
            }
        }
        return total;
    }
}
```
