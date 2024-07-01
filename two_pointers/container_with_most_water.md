## Task ✍
You are given an integer array height of length n. 

There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.

#### Example 1:
Input: ```height = [1,8,6,2,5,4,8,3,7]```

Output: ```49```

Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. 

In this case, the max area of water the container can contain is 49.

#### Example 2:
Input: ```height = [1,1]```

Output: ```1```

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I initially thought about iterating through the array to find the largest heights using a nested for loop but this is inefficient.

I then decided that in order to find the largest height with the largest length, I will need to keep track of the largest area as this will combine these two together when the largest area is not necessarily the highest height or the longest length. 

