## Task ✍
Given a string s consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

#### Example 1:
Input: ```s = "Hello World"```

Output: ```5```

Explanation: The last word is "World" with length 5.

#### Example 2:
Input: ```s = "   fly me   to   the moon  "```

Output: ```4```

Explanation: The last word is "moon" with length 4.

#### Example 3:
Input: ```s = "luffy is still joyboy"```

Output: ```6```

Explanation: The last word is "joyboy" with length 6.
 
## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I immediately saw through the examples that each one included spaces to split up each word so I knew I would have to use the ```.split()``` method to create an array of strings 

I also noticed that it did not specify that only a single space would be used so I would need to use the regex version of ```.split()``` to remove 1 or more spaces 

I also noticed that there can be leading and trailing spaces which can cause issues when selecting the last element in an array if the trailing space can be considered the final element

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I used the ```.trim()``` method to remove leading and trailing spaces, as well as the ```.split()``` method which removed spaces, but implementing the regex version through ```“\\s+”``` meant one or more spaces could be removed and then this was assigned to the string array called sArray
2. Finally a return statement returned the length of the final element in the array 
