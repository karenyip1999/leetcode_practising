## Task ✍
Given a string s, find the length of the longest substring without repeating characters.

#### Example 1:
Input: ```s = "abcabcbb"```

Output: ```3```

Explanation: The answer is "abc", with the length of 3.

#### Example 2:
Input: ```s = "bbbbb"```

Output: ```1```

Explanation: The answer is "b", with the length of 1.

#### Example 3:
Input: ```s = "pwwkew"```

Output: ```3```

Explanation: The answer is "wke", with the length of 3.

Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts about this problem was to either use a character stack to keep track of all the characters in s that were part of the substring with no repeated characters, or to use the sliding window technique.

When I wrote my solution for it using a character stack, I found that although there was a low memory usage of 43.2MB, I had a very high runtime of 658ms.

I decided to use a Hashset and the sliding window technique which ended up having a runtime of 6ms and very little change in memory usage of 44.8MB.
