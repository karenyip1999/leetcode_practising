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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called m which is the length of the nums1 array
2. I created a variable called n which is the length of the nums2 array
3. I created a new array called mergedArray which is the length of n and m combined
4. I created another variable called i and initiated this to 0 which acts as the index when we iterate through nums1
5. I created a variable called j and initiated this to 0 which acts as the index when we iterate through nums2
6. I created a variable called k and initiated this to 0 which acts as the index when we iterate through mergedArray
7. I used a while loop which continues iterating whilst i is less than m and j is less than n
8. Inside of this while loop, I used an if statement that checks if the current element at nums1 is smaller than the current element at nums2
9. If so, the element from nums1 is assigned to the the current element at mergedArray
10. i is incremented by 1
11. Else, the element from nums2 is assigned to the current element at mergedArray instead
12. j is incremended by 1
13. Outside of the if else statement, k is incremented by 1
14. Outside of this while loop, another while loop is iterating whilst i is less than m which checks for any remaining elements from nums1
15. The current element at nums1 is assigned to the current element at mergedArray
16. k is incremented by 1
17. i is incremented by 1
18. Another while loop is iterating whilst j is less than n which checks for any remaining elements from nums2
19. The current element at nums2 is assigned to the current element at mergedArray
20. k is incremented by 1
21. j is incremented by 1
22. A final variable is created called mid which has the mergedArray length divided by 2 assigned to it which finds the middle point in mergedArray
23. An if statement checks if mergedArray's length modulo 2 equals 0 which means the length of the array is even
24. If so, the value of the element in the middle of the array and the one previous it is added together and then divided by 2 and is returned
25. Else, the value of the element in the middle of the array is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        int[] mergedArray = new int[m + n];
        
        int i = 0; //Index for nums1
        int j = 0; //Index for nums2
        int k = 0; //Index for mergedArray[]
        while(i < m && j < n){
            if(nums1[i] < nums2[j]){
                mergedArray[k] = nums1[i];
                i++;
            }
            else{
                mergedArray[k] = nums2[j];
                j++;
            }
            k++;
        }
        
        while(i < m){
            mergedArray[k] = nums1[i];
            k++;
            i++;
        }
        while(j < n){
            mergedArray[k] = nums2[j];
            k++;
            j++;
        }

        int mid = mergedArray.length / 2;
        if(mergedArray.length % 2 == 0){
            return ((mergedArray[mid]) + (mergedArray[mid - 1])) / 2.0;
        }
        else{
            return mergedArray[mid];
        }
    }
}
```
