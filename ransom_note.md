## Task ✍
Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.

Each letter in magazine can only be used once in ransomNote.

#### Example 1:
Input: ```ransomNote = "a", magazine = "b"```

Output: ```false```

#### Example 2:
Input: ```ransomNote = "aa", magazine = "ab"```

Output: ```false```

#### Example 3:
Input: ```ransomNote = "aa", magazine = "aab"```

Output: ```true```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on solving this task was to iterate through the magazine string to compare with the individual characters of ransomNote to see if there is a match.

I had also considered checking if magazine ```.contains``` the whole ransomNote without using a hashmap but through testing, I found that ransomNote could be arranged in any way but magazine just needed to use all of the ransomNote characters

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. ```if(ransomNote.length() > magazine.length())```
   
   I created an if statement that checked if the length of the ransomNote string was longer than the magazine string as this would mean ransomNote could not be constructed fully using the letters in magazine
   
2. ```return false;```

   False would be returned straight away if ransomNote was longer than magazine
   
3. ```HashMap<Character, Integer> magazineMap = new HashMap<>();```

   I created a hashmap called magazineMap to hold the characters in magazine with the frequency of the appearance of each character 
   
4. ```for(int i = 0; i < magazine.length(); i++)```
   
   I used a for loop to iterate through the magazine string
   
5. ```char magCharacter = magazine.charAt(i);```
   
   With each iteration, the current character was assigned to the variable magCharacter
   
6. ```if(!magazineMap.containsKey(magCharacter))```
   
   Inside of the for loop is an if statement that checked if the magazine hashmap called magazineMap did not contain the current character called magCharacter
   
7. ```magazineMap.put(magCharacter, 1);```
   
   The current character was added to magazineMap and the frequency integer was set to 1
   
8. ```magazineMap.put(magCharacter, magazineMap.get(magCharacter) + 1);```
   
   Else, the current character already existing in magazineMap has it's frequency key increased by 1

9. ```for(int j = 0; j < ransomNote.length(); j++)```
   
    Outside of the magazine for loop, a for loop is used to iterate through the ransomNote string

10. ```char ransomCharacter = ransomNote.charAt(j);```
    
    At each iteration, the current character is assigned to the ransomCharacter variable

11. ```if(magazineMap.containsKey(ransomCharacter))```
    
    Inside of the for loop is an if statement that checks if the hashmap contains a key for the current character called ransomCharacter 
        
12. ```if(magazineMap.get(ransomCharacter) == 1)```
    
    Inside of the if statement is another if statement that checks if the ransomCharacter frequency equals 1

13. ```magazineMap.remove(ransomCharacter);```
    
    If so, then the ransomCharacter is removed from the hashmap as there is a match of the same character appearing once in magazine and once in ransomNote

14. ```magazineMap.put(ransomCharacter, magazineMap.get(ransomCharacter) -1);```
    
    Else, the current character in the hashmap is appearing more than once so the frequency is reduced by 1

15. ```return false;```
    An else statement is used with the first if statement in the second for loop which returns false if the hashmap doesn't contain the current character from the ransomNote as this would show the ransomNote cannot be constructed by using the letters from magazine

16. ```return true;```

    Outside of the for loop, true is returned 
