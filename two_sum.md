## Task
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

#### Example 1:
Input: ```nums = [2,7,11,15], target = 9```

Output: ```[0,1]```

Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

#### Example 2:
Input: ```nums = [3,2,4], target = 6```
Output: ```[1,2]```

#### Example 3:
Input: ```nums = [3,3], target = 6```
Output: ```[0,1]```

## Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts were to do a for loop to iterate through the array adding i and i + 1 but this didn't take into consideration that there can be numbers that can add up to the target that are not necessarily next to each other.

I started thinking about adding if statements to target numbers not next to each other but this became tedious and was clear I was overcomplicating a problem classified as Easy. 

## Approach
<!-- Describe your approach to solving the problem. -->
1. I initialised a new array called sumArray with the size of 2 as it will only hold 2 numbers, which will be the 2 indexes of the elements that add up to the target 
2. I took the approach of using a nested for loop to iterate through the nums array starting the outer for loop at index 0
3. I set the inner for loop to start at i + 1 which would be the number at index 1
4. Inside of the inner for loop, the conditional if statement checked to see if the number at i and j added to equal the target. If it did add to the target then index 0 of sumArray will be i and index 1 will be j and this is returned
5. In the case of nothing adding up to the target, sumArray is returned regardless 

## Code
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int [] sumArray = new int[2];
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j ++) {
                    if (nums[i] + nums[j] == target){
                        sumArray[0] = i;
                        sumArray[1] = j;
                        return sumArray;
                    }
            }
        }
        return sumArray;
    }
}
```
