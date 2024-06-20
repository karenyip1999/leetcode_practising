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
