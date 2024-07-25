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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called left and initiated this to 0 which would act as my left pointer in my sliding window solution
2. I created a variable called right and initiated this to 0 which would act as my right pointer
3. I created a variable called length and initiated this to 0 which would keep track of the length of the longest substring with no repeating characters
4. I created a HashSet called sHashSet that would hold the substring
5. I used a while loop that would iterate through s whilst right was less than the length of s
6. Inside of the while loop, an if statement checked that if sHashSet did not contain the character at the index of right
7. If so, the character at the index of right would be added to sHashSet
8. The variable right was incremented by 1
9. Inside of this if statement was another if statement that checked if the size of sHashSet was larger than length
10. If so, the size of sHashSet was assigned to length
11. Outside of this inner if statement, an else statement meant the character at the index of left was removed from sHashSet and the left pointer is incremented by 1 to move the sliding window along
12. Outside of the while loop, length is returned 
