## Task ✍
Given a string s containing just the characters ```(```, ```)```, ```{```, ```}```, ```[``` and ```]```, determine if the input string is valid.

An input string is valid if:

* Open brackets must be closed by the same type of brackets.
* Open brackets must be closed in the correct order.
* Every close bracket has a corresponding open bracket of the same type.

#### Example 1:
Input: ```s = "()"```

Output: ```true```

#### Example 2:
Input: ```s = "()[]{}"```

Output: ```true```

#### Example 3:
Input: ```s = "(]"```

Output: ```false```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I had initially thought to use a HashMap to keep track of the brackets and increase the value of each during the iteration through s.

However, I realised that I struggled to keep track of the order of the opening and closing brackets and therefore chose to use a character stack so when I pushed elements to the top of the stack, it would keep the order. 
