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

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a new int array called candyArray to hold the candies of each child and set it to the length of the ratings array
2. I used ```Arrays.fill()``` on the candyArray to set all elements to 1
3. I created a variable called candyCount which is initiated to 0 that will hold the amount of candies distributed to all children
4. I used a for loop that starts at 1 to iterate through the ratings array from left to right
5. Inside of the for loop is an if statement that checks if the current element in the ratings array is greater than the previous element
6. The value of the previous element in the candyArray incremented by 1 is assigned to the element in the candyArray at the current index
7. Another for loop is used to iterate from right to left in the ratings array and starts at the penultimate element in the ratings array
8. Inside of this second for loop is an if statement that checks if the current element in the ratings array is greater than the previous element and if the value at the current index in candyArray is less than the previous element in candyArray incremented by 1
9. If this is the case, the current element in candyArray is set to the value of the previous element in candyArray, incremented by 1
10. Outside of this for loop, another for loop increments through the candyArray
11. The value of the current element in candyArray is added and assigned to candyCount
12. Outside of this for loop, candyCount is returned
