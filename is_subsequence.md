## Task ✍
Given two strings s and t, return true if s is a subsequence of t, or false otherwise.

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. 

(i.e., "ace" is a subsequence of "abcde" while "aec" is not).

#### Example 1:
Input: ```s = "abc", t = "ahbgdc"```

Output: ```true```

#### Example 2:
Input: ```s = "axc", t = "ahbgdc"```

Output: ```false```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts were to use a for loop to iterate through t and s to check if the element at s was equal to the element at t.

Then outside of the loop, if the variable holding the index for s was the same as the length of s, then true could be returned as this would show all matches of s were found and in the correct order. 

This was the final approach I took in creating my solution, but tried to make the solution slightly shorter by using a while loop.
