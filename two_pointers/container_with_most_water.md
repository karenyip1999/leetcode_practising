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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called left and initiated this to 0 which will hold the value on the left side of the array as I am using a two pointer method
2. I created a variable called right and initiated this to the last element in the array as this will hold the value on the right side of the array
3. I created another variable called area and initiated this to 0 as this will hold the value of the largest area
4. I used a while loop that would iterate through the array whilst the left value was less than the right value
5. Inside of the while loop, I used an if statement that checked if the current area using the right side's height, was greater than the area variable, and that the left side's height was larger than the right side's height
6. If this was the case then the area calculated using the right side's height is assigned to the area variable
7. Else if the current area using the left side's height was greater than the area variable, and the right side's height was larger than the left side's height
8. The area calculated using the left side's height is assigned to the area variable
9. Another if statement checked if the left height was greater than or equal to the right height
10. If this was the case then the right index was decreased
11. Else if the right height was larger than the left height
12. The left index was increased 
13. Outside of the while loop, area is returned
