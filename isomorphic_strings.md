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
