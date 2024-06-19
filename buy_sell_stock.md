## Task ✍
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. 

If you cannot achieve any profit, return 0.

#### Example 1:
Input: ```prices = [7,1,5,3,6,4]```

Output: ```5```

Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.

Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

#### Example 2:
Input: ```prices = [7,6,4,3,1]```

Output: ```0```

Explanation: In this case, no transactions are done and the max profit = 0.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on how to solve this problem involved iterating through the prices array to compare the previous element with the current element, with the smaller element being held within a variable called buy.

I was also thinking of comparing a variable called sell and setting the larger element as the value in this variable.

I would then return a variable called maxProfit that would be calculated by decreasing the buy variable from sell.

This was the approach I led with but ultimately found that I didn't need to compare both buy with the current element and then sell with the current element as calculating the maximum profit using the smallest buy value would solve the problem. 

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a buy variable and initiated it to the 0th element in the prices array
2. I created a maxProfit variable and initiated it to 0
3. I used a for loop that started at index 1 to iterate through the prices array and this would account for a sell value
4. Inside of the for loop is an if statement that compared the current element in the prices array to the buy variable
5. If the current element was less than the buy variable then the current element was assigned to buy
6. Else if the current element minus the buy value was more than the maxProfit value
7. The value of the current element minus the buy value was assigned to maxProfit
8. Outside of the for loop, the value of maxProfit was returned 
