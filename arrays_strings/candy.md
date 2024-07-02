## Task ✍
There are n children standing in a line. 

Each child is assigned a rating value given in the integer array ratings.

You are giving candies to these children subjected to the following requirements:

* Each child must have at least one candy.
* Children with a higher rating get more candies than their neighbors.
  
Return the minimum number of candies you need to have to distribute the candies to the children.

#### Example 1:
Input: ```ratings = [1,0,2]```

Output: ```5```

Explanation: You can allocate to the first, second and third child with 2, 1, 2 candies respectively.

#### Example 2:
Input: ```ratings = [1,2,2]```

Output: ```4```

Explanation: You can allocate to the first, second and third child with 1, 2, 1 candies respectively.

The third child gets 1 candy because it satisfies the above two conditions.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I initally thought about iterating through the array from left to right and keeping a counter of the candies being distributed to each child. 

I then thought about creating an array to keep count of the candies distributed to each child instead. 

I then realised that instead of just iterating through the array from left to right, I will also need to check from right to left as I will need to make sure that if the current child has a higher rating than the child on the right, they will need to have more candies. 
