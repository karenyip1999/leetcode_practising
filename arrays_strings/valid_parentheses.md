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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I initiated a character stack called charStack which would help me keep track of the opening brackets and their order
2. I used a for loop to iterate through s
3. Inside of the for loop, I created a variable called sChar that would hold the current character
4. I used an if statement that checked if the current character was any of the open brackets
5. If so, I pushed the current character to the top of the character stack
6. Else, this would be a closing bracket so I wrapped the remaining if statements in an else bracket
7. I used an if statement to check if the character stack was empty as this would mean there are no open brackets to match to the closing bracket so is appearing out of order
8. If so, return false
9. Another if statement was used to check if the current character was equal to ) and the character popped from the top of the character stack is not equal to the opening bracket (
10. Then false is returned
11. An if statement was used to check if the current character was equal to } and the character popped from the top of the character stack is not equal to the opening bracket {
12. Then false is returned
13. A final if statement is used to check if the current character was equal to ] and the character popped from the top of the character stack is not equal to the opening bracket [
14. Then false is returned
15. Outside of the for loop, the character stack is checked to see if it is empty as if the stack is empty then all open brackets have been closed, which returns a boolean 

## Code 📝
My solution to the task.
```java
class Solution {
    public boolean isValid(String s) {
        Stack <Character> charStack = new Stack <>();
        for(int i = 0; i < s.length(); i ++){
            char sChar = s.charAt(i);
            if(sChar == '(' || sChar == '{' || sChar == '['){
                charStack.push(sChar);
            }
            else{
                if(charStack.empty()){
                    return false;
                }
                if(sChar == ')' && charStack.pop() != '('){
                    return false;
                }
                if(sChar == '}' && charStack.pop() != '{'){
                    return false;
                }
                if(sChar == ']' && charStack.pop() != '['){
                    return false;
                }
            }
        }
        return charStack.empty();
    }
}
```
