## Task ✍
Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. 

No two characters may map to the same character, but a character may map to itself.

#### Example 1:
Input: ```s = "egg", t = "add"```

Output: ```true```

#### Example 2:
Input: ```s = "foo", t = "bar"```

Output: ```false```

#### Example 3:
Input: ```s = "paper", t = "title"```

Output: ```true```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My instant thought when reading the task was to create 2 separate hashmaps containing s mapped to t and then t mapped to s to compare the pattern of mappings for both strings.

This is the approach I have taken to create my actual solution for the task.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a HashMap called sTot that mapped characters from the string s to characters from string t
2. I created another HashMap called Ttos that mapped characters from the string t to characters from string s
3. I used a for loop to iterate through the length of s which would also be the length of t
4. Inside of the for loop is a variable called sChar that holds the current character from s
5. Another variable called tChar holds the current character from t
6. Inside of the for loop, there is an if statement that checks that if sTot doesn't contain the key sChar
7. Then sChar is mapped with the value of tChar as sChar has not appeared before
8. An additional if statement also checks that if tTos doesn't contain the key tChar
9. Then tChar is mapped with the value of sChar as tChar has not appeared before
10. A final if statement checks that if sChar inside of sTot doesn't equal tChar or tChar inside of tTos doesn't equal sChar
11. Then false is returned as this means the strings are not isomorphic
12. Finally, true is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public boolean isIsomorphic(String s, String t) {
        
        HashMap<Character, Character> sTot = new HashMap<>();
        HashMap<Character, Character> tTos = new HashMap<>();
        
        for(int i = 0; i < s.length(); i ++){
            char sChar = s.charAt(i);
            char tChar = t.charAt(i);
            if(!sTot.containsKey(sChar)){
                sTot.put(sChar, tChar);
            }
            if(!tTos.containsKey(tChar)){
                tTos.put(tChar, sChar);
            }
            if(!sTot.get(sChar).equals(tChar) || !tTos.get(tChar).equals(sChar)){
                return false;
            }
        }
        return true;
    }
}
```
