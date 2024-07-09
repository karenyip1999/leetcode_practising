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
