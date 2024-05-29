## Task
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

#### Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

#### Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]

#### Example 3:
Input: nums = [3,3], target = 6
Output: [0,1]

## Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts were to do a for loop to iterate through the array adding i and i + 1 but this didn't take into consideration that there can be numbers that can add up to the target that are not necessarily next to each other.

I started thinking about adding if statements to target numbers not next to each other but this became tedious and was clear I was overcomplicating a problem classified as Easy. 

