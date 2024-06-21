## Task ✍
Given a pattern and a string s, find if s follows the same pattern.

Here follow means a full match, such that there is a bijection between a letter in pattern and a non-empty word in s.

#### Example 1:
Input: ```pattern = "abba", s = "dog cat cat dog"```

Output: ```true```

#### Example 2:
Input: ```pattern = "abba", s = "dog cat cat fish"```

Output: ```false```

#### Example 3:
Input: ```pattern = "aaaa", s = "dog cat cat dog"```

Output: ```false```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts were to split s into a string array and then create a HashMap using the string array, with the value as the frequency of each element from the array.

After, I would create another HashMap for the pattern string that had the key as the individual characters and then the value as the frequency of each character.

Trying to solve the problem like this however did not check if s followed the same pattern as pattern.

I therefore modified my solution so that I would still have 2 HashMaps, but had both s and pattern in each HashMap.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a new string array called sArray to hold all of the elements of the s string after I split it at the single spaces using the ```.split()``` method
2. I created an if statement that checked if the sArray length was not equal to the pattern length then this would immediately return false as s will not follow the same pattern as the pattern string
3. I created a hashmap called characterToStringMap that was to hold the individual characters of pattern and the element from s
4. I created another hashmap called stringToCharacterMap that was to hold the element from s and the individual character from pattern
5. I used a for loop to iterate through the characters in pattern
6. I created a variable called patternChar to hold the current character
7. I created a variable called sString to hold the current element inside the sArray
8. Inside of the for loop, I used an if statement to check that if the characterToStringMap did not contain the key patternChar
9. characterToStringMap would then have patternChar added, with the corresponding sString
10. Another if statement checked if the stringToCharacterMap did not contain the key sString
11. stringToCharacterMap would then have sString added, with the corresponding patternChar
12. Another if statement checked if the patternChar inside the characterToStringMap did not equal sString or if the sString inside of stringToCharacterMap did not equal patternChar
13. false would be returned, as this would mean an element in sArray did not match the correct pattern character 
14. Outside of the for loop, true was returned

## Code 📝
My solution to the task.
```java
class Solution {
    public boolean wordPattern(String pattern, String s) {
        String[] sArray = s.split(" ");
        
        if(sArray.length != pattern.length()){
            return false;
        }
        
        HashMap<Character, String> characterToStringMap = new HashMap<>();
        HashMap<String, Character> stringToCharacterMap = new HashMap<>();
        
        for(int i = 0; i < pattern.length(); i ++){
            char patternChar = pattern.charAt(i);
            String sString = sArray[i];
            if(!characterToStringMap.containsKey(patternChar)){
                characterToStringMap.put(patternChar, sString);
            }
            if(!stringToCharacterMap.containsKey(sString)){
                stringToCharacterMap.put(sString, patternChar);
            }
            if(!characterToStringMap.get(patternChar).equals(sString) || !stringToCharacterMap.get(sString).equals(patternChar)){
                return false;
            }
        }
        return true;
    }
}
```
