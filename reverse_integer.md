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

However, as it is an int I found that I could do this without a for loop by dividing x by 10 to get the last digit of x as the modulo.

A quick Google search found that the 32 bit range I needed would be between -214748364 and 214748364.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called xReverse and initiated this to 0 as this will hold the reverse of x
2. I used a while loop which iterated through x whilst x did not equal to 0
3. Inside of the while loop, I used an if statement that checked if xReverse was less than -214748364 or greater than 214748364, meaning it is no longer in the 32 bit integer range
4. 0 would be returned
5. Outside of the if statement but still inside of the while loop, I created a variable called remainder which had x modulo 10 assigned to it
6. xReverse then has xReverse multiplied by 10 with remainder added to it, so instead of having 2 single digits added together, the remainder will go at the end of xReverse
7. x is then divided by 10 which therefore removes the last digit we have placed in xReverse
8. Outside of the while loop, xReverse is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public int reverse(int x) {
        int xReverse = 0; 
        
        while(x != 0){
            if(xReverse < -214748364 || xReverse > 214748364){
                return 0;
            }
            int remainder = x % 10;
            xReverse = xReverse * 10 + remainder;
            x = x / 10;
        }
        return xReverse;
    }
}
```
