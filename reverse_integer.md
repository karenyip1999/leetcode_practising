## Task ✍
Given a signed 32-bit integer x, return x with its digits reversed. 

If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

#### Example 1:
Input: ```x = 123```

Output: ```321```

#### Example 2:
Input: ```x = -123```

Output: ```-321```

#### Example 3:
Input: ```x = 120```

Output: ```21```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I had initally thought to use a for loop to iterate through x to reverse the digits.

However, as it is an int I found that I could do this without a for loop by dividing x by 10 to get the last digit of x.

A quick Google search found that the 32 bit range I needed would be between -214748364 and 214748364.
