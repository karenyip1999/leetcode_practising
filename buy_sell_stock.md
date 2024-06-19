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

I was also thinking of comparing a variable called sell and setting the larger element in this variable.

I would then return a variable called maxProfit that would be calculated by decreasing the buy variable from sell.

This was the approach I led with but ultimately found that I didn't need to compare both buy with the current element and then sell with the current element as calculating the maximum profit using the smallest buy value would solve the problem. 
