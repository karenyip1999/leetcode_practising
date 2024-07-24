## Task ✍
You are given two non-empty linked lists representing two non-negative integers. 

The digits are stored in reverse order, and each of their nodes contains a single digit. 

Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

#### Example 1:
Input: ```l1 = [2,4,3], l2 = [5,6,4]```

Output: ```[7,0,8]```

Explanation: 342 + 465 = 807.

#### Example 2:
Input: ```l1 = [0], l2 = [0]```

Output: ```[0]```

#### Example 3:
Input: ```l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]```

Output: ```[8,9,9,9,0,0,0,1]```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on solving this problem were to tackle the quirks that come with addition such as carrying 1 when addition makes the single digit turn into a double digit.

I also thought about placement of the integers when carrying out the addition as there is nothing to stop the addition from being between different length integers which would need 0 placed in front of the shorter integer.
