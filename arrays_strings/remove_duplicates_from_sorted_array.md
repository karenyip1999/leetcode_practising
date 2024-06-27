## Task ✍
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. 

The relative order of the elements should be kept the same. 

Then return the number of unique elements in nums.

Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:

* Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially.
* The remaining elements of nums are not important as well as the size of nums.
* Return k.
  
#### Custom Judge:

The judge will test your solution with the following code:
```java
int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}
```
If all assertions pass, then your solution will be accepted.

#### Example 1:
Input: ```nums = [1,1,2]```

Output: ```2, nums = [1,2,_]```

Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.

It does not matter what you leave beyond the returned k (hence they are underscores).

#### Example 2:
Input: ```nums = [0,0,1,1,1,2,2,3,3,4]```

Output: ```5, nums = [0,1,2,3,4,_,_,_,_,_]```

Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.

It does not matter what you leave beyond the returned k (hence they are underscores).

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts about this task was that I could use a for loop to iterate through the nums array and compare the current i element with the next element using i + 1.

I quickly found the issue of falling out of bounds of the array.

In fixing this issue, I changed the for loop condition to end when it reached the second to last element in the array but that produced an incorrect array with an incorrect k result.

I changed my focus to compare the current i element with the previous element using i - 1 instead.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable k that counted the unique elements and by assuming the 0th element in the array would be unique, it is set to 1.
2. I created a for loop that started at the 1st element with the understanding that the 0th element was unique.
3. Inside of the for loop, an if statement checks if the previous element is not the same as the current element, meaning the element at i is a unique element.
4. The element at i replaces the element in the array at the count of k to keep the array sorted in ascending order.
5. The counter for k is then incremented.
6. Finally, k is returned.

## Code 📝
My solution to the task.
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int k = 1;
        for(int i = 1; i < nums.length; i ++){
            if(nums[i - 1] != nums[i]){
                nums[k] = nums[i];
                k++;
            }

        }
        return k;
    }
}
```
