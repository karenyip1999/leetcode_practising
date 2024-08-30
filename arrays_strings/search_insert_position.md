## Task ✍
Given a sorted array of distinct integers and a target value, return the index if the target is found. 

If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

#### Example 1:
Input: ```nums = [1,3,5,6], target = 5```

Output: ```2```

#### Example 2:
Input: ```nums = [1,3,5,6], target = 2```

Output: ```1```

#### Example 3:
Input: ```nums = [1,3,5,6], target = 7```

Output: ```4```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My thoughts as soon as I saw this task was to use binary search due to the specification that the solution had to have a logarithmic runtime complexity.

For me, binary search seemed like the fastest solution.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called left which would hold the index of the lower value in the nums array, so I initiated this to 0
2. I created a variable called right which would hold the index of the higher value in the nums array, so I initiated this to the index of the final element in nums
3. I created a variable called mid which would hold the index of the middle value in the nums array, so I initiated this to 0 just to hold a value before I used it within the while loop
4. I used a while loop that would continue iterating whilst left was less than or equal to right
5. Inside of the while loop, I set mid to equal right minus left, added to left, and this is divided by 2 to find out the index of the middle number in the array
6. An if statement checks if the value inside the nums array at the index of mid is equal to the target value
7. If so, mid is returned
8. Another if statement checks if the target is less than the value inside the nums array at the index mid
9. If so, mid decreases by 1 and this is assigned to right
10. Else, mid is incremented by 1 and this is assigned to left as the target is greater than the value inside the nums array at index mid
11. Finally, left is returned as this is where the target should be inserted within the nums array if it does not already exist

## Code 📝
My solution to the task.
```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        int mid = 0;
        while(left <= right){
            mid = left + (right - left) / 2;
            if(nums[mid] == target){
                return mid;
            }
            if(target < nums[mid]){
                right = mid - 1;
            }
            else{
                left = mid + 1;
            }
        }
        return left;
    }
}
```
