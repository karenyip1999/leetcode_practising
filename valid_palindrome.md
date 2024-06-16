## Task ✍
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. 

Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

#### Example 1:
Input: ```s = "A man, a plan, a canal: Panama"```

Output: ```true```

Explanation: "amanaplanacanalpanama" is a palindrome.

#### Example 2:
Input: ```s = "race a car"```

Output: ```false```

Explanation: "raceacar" is not a palindrome.

#### Example 3:
Input: ```s = " "```

Output: ```true```

Explanation: s is an empty string "" after removing non-alphanumeric characters.

Since an empty string reads the same forward and backward, it is a palindrome.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My immediate thoughts were that I could remove all non-alphanumeric characters, reverse the string and then compare with the input to check if they are a match.

This is the approach I pursued to solve the problem.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I modified the input string s by replacing all instances of non-alphanumeric characters with an empty string and then set it to lowercase
2. I created a char variable named character used to store individual characters when iterating through s
3. I created a string variable named reverseS initiated as an empty string that was used to hold the reversed s
4. I used a for loop to iterate through s
5. I assigned the element at index i to the character variable
6. I concatenated character to the values already being held in reverseS before assigning it to the reverseS variable
7. Outside of the for loop is an if statement that checks if the input string s is equal to reverseS
8. If the condition is met, true is returned otherwise false is returned

