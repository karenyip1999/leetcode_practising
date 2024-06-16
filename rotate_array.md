## Task ✍
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

#### Example 1:
Input: ```nums = [1,2,3,4,5,6,7], k = 3```

Output: ```[5,6,7,1,2,3,4]```

Explanation:

Rotate 1 steps to the right: [7,1,2,3,4,5,6]

Rotate 2 steps to the right: [6,7,1,2,3,4,5]

Rotate 3 steps to the right: [5,6,7,1,2,3,4]

#### Example 2:
Input: ```nums = [-1,-100,3,99], k = 2```

Output: ```[3,99,-1,-100]```

Explanation: 

Rotate 1 steps to the right: [99,-1,-100,3]

Rotate 2 steps to the right: [3,99,-1,-100]

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts were to reverse the array and then from the middle of the array, I would attempt to place the end elements in ascending order.

I tried to do so with two separate for loops to handle the front and the end of the array separately but this did not work.

Instead I tried to write a reverse method that would do this in multiple steps.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. Starting with the reverse method I created, it takes in an array called nums, an int called start and an int called end
2. I used a while loop that ran whilst the start value is less than the end value 
3. An int variable called temp held the element at the index of start
4. The element of start then gets the element of end assigned to it
5. The element of end is then assigned the value held by temp
6. With each iteration, the value of start then increased by 1 and the value of end decreased by 1
7. Inside the rotate method, I reassigned k to be the modulus of the length of the array to remove any unnecessary iterations if k was a number larger than the length of the array
8. I used the reverse method to reverse the whole array nums shown by the start value of 0 and the end value being the final element in the nums array
9. I then reversed the beginning of the array using the reverse method with the start value being 0 and the end value of k - 1
10. Finally, the end of the array is reversed using the reverse method taking k as the start value and the end value being the final element in the nums array 
