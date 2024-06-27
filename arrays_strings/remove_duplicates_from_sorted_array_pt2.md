## Task ✍
Given an integer array nums sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. 

The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array nums. 

More formally, if there are k elements after removing the duplicates, then the first k elements of nums should hold the final result. 

It does not matter what you leave beyond the first k elements.

Return k after placing the final result in the first k slots of nums.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

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
Input: ```nums = [1,1,1,2,2,3]```

Output: ```5, nums = [1,1,2,2,3,_]```

Explanation: Your function should return k = 5, with the first five elements of nums being 1, 1, 2, 2 and 3 respectively.

It does not matter what you leave beyond the returned k (hence they are underscores).

#### Example 2:
Input: ```nums = [0,0,1,1,1,1,2,3,3]```

Output: ```7, nums = [0,0,1,1,2,3,3,_,_]```

Explanation: Your function should return k = 7, with the first seven elements of nums being 0, 0, 1, 1, 2, 3 and 3 respectively.

It does not matter what you leave beyond the returned k (hence they are underscores).

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I began thinking about comparing ```i``` against ```i - 1``` and ```i + 1``` (The previous and next elements in the array) but this obviously causes some array out of bounds issues. 

I thought about having a counter that kept track of elements that had been encountered previously, making it easier to remove elements duplicated more than twice.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
I realised that instead of just comparing i against an element before it or 2 elements before it, I could go further and keep track of the specific index to place non duplicated elements through k.
1. I created the variable k and set it to 2 as it is accepted that the same element can be duplicated twice
2. I used a for loop to iterate through the nums array, starting from the 2nd index as this is the first element we want to  check for uniqueness
3. I used an if statement to check if the current element at i is not equal to the element at the position of ```k - 2```. ```k - 2``` keeps track of the unique elements in nums
4. If the condition is met, then the current element will replace the element in the nums array at the position of the number of k
5. k count is then increased
6. Finally, k is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int k = 2;
        for(int i = 2; i < nums.length; i++){
            if(nums[i] != nums[k - 2]){
                nums[k] = nums[i];
                k++;
            }
        }
        return k;
    }
}
```
