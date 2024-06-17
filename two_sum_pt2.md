## Task ✍
Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. 

Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length.

Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

#### Example 1:
Input: ```numbers = [2,7,11,15], target = 9```

Output: ```[1,2]```

Explanation: The sum of 2 and 7 is 9. 

Therefore, index1 = 1, index2 = 2. 

We return [1, 2].

#### Example 2:
Input: ```numbers = [2,3,4], target = 6```

Output: ```[1,3]```

Explanation: The sum of 2 and 4 is 6. 

Therefore index1 = 1, index2 = 3. 

We return [1, 3].

#### Example 3:
Input: ```numbers = [-1,0], target = -1```

Output: ```[1,2]```

Explanation: The sum of -1 and 0 is -1. 

Therefore index1 = 1, index2 = 2. 

We return [1, 2].

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I had initially thought about removing the larger elements at the end of the array that were greater than the target number which I thought would remove any unnecessary iterations of just comparing 2 numbers greater than the target.

I tried to limit down the range of elements being checked using a binary search which inspired my solution to the task.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called index1 and initiated it to 0 which was used to hold the index of the element towards the beginning of the numbers array and counted upwards
2. I created a variable called index2 and initiated it to the final element in the numbers array and this decreased through the numbers array
3. I used a while loop to iterate through the numbers array whilst the element held at index1 was less than the element held at index2
4. Inside of the while loop was an if statement that checked if the sum of the element at index1 and index2 was greater than the target value
5. If the sum was larger than the target then index2 would decrease as it would mean the element being used at the end of the array was too large 
6. An if else statement was used to check if the sum of the element at index1 and index2 was less than the target value
7. If the sum was less than the target then index1 would increase as it would mean the element being used at the beginning of the array was too small
8. A final if else statement was used to check if the sum of the element at index1 and index2 was equal to the target value
9. If the sum was equal to the target then the index1 value and index2 value were both increased by 1 as it is a 1- indexed array, before being returned
10. Finally, index1 increased by 1 and index2 increased by 1 were returned 

## Code 📝
My solution to the task.
```java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int index1 = 0;
        int index2 = numbers.length -1;
        
        while(numbers[index1] < numbers[index2]){
            if(numbers[index1] + numbers[index2] > target){
                index2 --;
            }
            else if(numbers[index1] + numbers[index2] < target){
                index1 ++;
            }
            else if(numbers[index1] + numbers[index2] == target){
                return new int [] {index1 + 1, index2 + 1};
            }
        }
        return new int[] {index1 + 1, index2 + 1};
    }
}
```
