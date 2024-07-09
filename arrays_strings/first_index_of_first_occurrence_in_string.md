## Task ✍
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

#### Example 1:
Input: ```haystack = "sadbutsad", needle = "sad"```

Output: ```0```

Explanation: "sad" occurs at index 0 and 6.

The first occurrence is at index 0, so we return 0.

#### Example 2:
Input: ```haystack = "leetcode", needle = "leeto"```

Output: ```-1```

Explanation: "leeto" did not occur in "leetcode", so we return -1.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts on how to solve this problem was to iterate through haystack and compare the current character with the beginning of needle.

I would then continue through haystack and needle to make sure the whole of needle was present in haystack. 

I was thinking of creating a variable that would hold the index of the first occurrence of i, but I later decided that I could just return i if I used a separate for loop to continue to iterate through haystack and needle.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a boolean variable called haystackNeedle and initiated this to false
2. I used an if statement to check beforehand for any instances where needle is longer than haystack by checking if the length of haystack was shorter than the length of needle
3. If so, I return -1
4. I used a for loop to iterate until the length of haystack minus the length of needle as I am looking to check for a match in haystack with the first character of needle
5. Inside of the for loop, I used an if statement to check if the current character in haystack is equal to the 0th character in needle
6. If so, haystackNeedle is set to true
7. Another for loop is used to iterate through haystack until the length of needle as we have found where needle starts in haystack and therefore the loop starts at index 1
8. An if statement is used inside of the for loop to check if the current character doesn't equal the current character in needle
9. If so, haystackNeedle is set to false and we break out of the for loop
10. Outside of the for loop, an if statement checks if haystackNeedle is set to true
11. If so, i is returned for the index of the beginning of needle
12. Outside of this, -1 is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public int strStr(String haystack, String needle) {
        boolean haystackNeedle = false;
        
        if(haystack.length() < needle.length()){
            return -1;
        }
        
        for(int i = 0; i <= haystack.length() - needle.length(); i ++){
            if(haystack.charAt(i) == needle.charAt(0)){
                haystackNeedle = true;
                for(int k = 1; k < needle.length(); k ++){
                    if(haystack.charAt(i + k) != needle.charAt(k)){
                        haystackNeedle = false;
                        break;
                    }
                }
            }
            if(haystackNeedle == true){
                return i;
            }
        }
        return -1;
    }
}
```
