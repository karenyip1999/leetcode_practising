## Task ✍
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

#### Example 1:
Input: ```nums1 = [1,3], nums2 = [2]```

Output: ```2.00000```

Explanation: merged array = [1,2,3] and median is 2.

#### Example 2:
Input: ```nums1 = [1,2], nums2 = [3,4]```

Output: ```2.50000```

Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
Whilst reading the task, I instantly thought that I would have to do a merge of the two arrays and sort it first before I could start to calculate the median.

I decided to take the approach of the merge sort which uses two pointers to combine the two arrays, whilst sorting.
