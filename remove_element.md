## Task
Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. 

The order of the elements may be changed. 

Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

* Change the array nums such that the first k elements of nums contain the elements which are not equal to val.
* The remaining elements of nums are not important as well as the size of nums.
* Return k.

#### Custom Judge:
The judge will test your solution with the following code:
```
int[] nums = [...]; // Input array
int val = ...; // Value to remove
int[] expectedNums = [...]; // The expected answer with correct length.
                            // It is sorted with no values equaling val.

int k = removeElement(nums, val); // Calls your implementation

assert k == expectedNums.length;
sort(nums, 0, k); // Sort the first k elements of nums
for (int i = 0; i < actualLength; i++) {
    assert nums[i] == expectedNums[i];
}
```
If all assertions pass, then your solution will be accepted.

#### Example 1:
Input: ```nums = [3,2,2,3], val = 3```

Output: ```2, nums = [2,2,_,_]```

Explanation: Your function should return k = 2, with the first two elements of nums being 2.

It does not matter what you leave beyond the returned k (hence they are underscores).

#### Example 2:
Input: ```nums = [0,1,2,2,3,0,4,2], val = 2```

Output: ```5, nums = [0,1,4,0,3,_,_,_]```

Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.

Note that the five elements can be returned in any order.

It does not matter what you leave beyond the returned k (hence they are underscores).

## Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts were that this was going to be an easy problem to solve. 

I started thinking about making another array that would store all elements from the nums array which did not equal val, and then increase the counter called k. I would then copy this new array and name it as nums, and then return.

I was also thinking of focusing on the elements in the array which did equal the val and using a sorting algorithm to place those elements at the end of the array.

I really struggled with this task and placed my focus on elements inside of the array which did equal the val and tried to place these at the end of the array using a nested for loop with a decrementing counter to handle instances where the final element is already equal to the val.

## Approach
<!-- Describe your approach to solving the problem. -->
After struggling with placing elements at the end of the array that equaled val, I flipped my approach and looked at elements in the array which did not equal the val and placing them at the beginning of the array
1. I create the variable k and set it to 0
2. I use a for loop to iterate through the nums array
3. Inside of the for loop is an if statement that checks if the element is not equal to val
4. If the element is not equal to val, I set the element to the position inside of the nums array based on the k count and then increment the k count by 1
5. The k counter is then returned 


