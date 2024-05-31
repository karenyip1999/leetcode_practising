## Task ✍
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. 

To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. 
nums2 has a length of n.

#### Example 1:
Input: ```nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3```

Output: ```[1,2,2,3,5,6]```

Explanation: The arrays we are merging are [1,2,3] and [2,5,6].

The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.

#### Example 2:
Input: ```nums1 = [1], m = 1, nums2 = [], n = 0```

Output: ```[1]```

Explanation: The arrays we are merging are [1] and [].

The result of the merge is [1].

#### Example 3:
Input: ```nums1 = [0], m = 0, nums2 = [1], n = 1```

Output: ```[1]```

Explanation: The arrays we are merging are [] and [1].

The result of the merge is [1].

Note that because m = 0, there are no elements in nums1. The 0 is only there to ensure the merge result can fit in nums1.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My first thoughts on solving this problem was to do a merge sort but as this problem was classified as Easy, I didn't want to overcomplicate it. 

I was thinking about potentially converting the array to an arraylist to make it easier to replace elements inside the arraylist and then converting it back to an array but that also complicated it.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I took the approach of defining the start index of the nums1 array which for me was where 0s began.
2. I set the outer for loop to begin at the index that held the first 0 in the nums1 array
3. I set the inner for loop to loop through the nums2 array and then replace each element at that index in the nums1 array to the element at the index of the nums2 array
4. After looping through both nums1 and nums2, I sorted the nums1 array
5. Finally, I printed out the nums1 array

## Code 📝
My solution to the task.
```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int startIndex = nums1.length - n;
        for (int i = startIndex; i < nums1.length; i++) {
            for (int j = 0; j < nums2.length; j++) {
                nums1[i] = nums2[j];
                i++;
            }
        }
        Arrays.sort(nums1);
        System.out.println(nums1);
    }
}
```
