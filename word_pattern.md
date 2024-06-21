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
