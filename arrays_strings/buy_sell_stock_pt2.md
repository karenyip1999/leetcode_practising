## Task ✍
You are given an integer array prices where ```prices[i]``` is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. 

You can only hold at most one share of the stock at any time. 

However, you can buy it then immediately sell it on the same day.

Find and return the maximum profit you can achieve.

#### Example 1:
Input: ```prices = [7,1,5,3,6,4]```

Output: ```7```

Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.

Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.

Total profit is 4 + 3 = 7.

#### Example 2:
Input: ```prices = [1,2,3,4,5]```

Output: ```4```

Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.

Total profit is 4.

#### Example 3:
Input: ```prices = [7,6,4,3,1]```

Output: ```0```

Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
I inititally thought that I could solve this task by iterating through the array to find the 2 highest profits, storing these into 2 variables and then adding them together to make the max profit.

However, I realised that there is potential for there to be more than 2 profits and the only thing I need to look out for is if there is a chance to make a profit later down the array.

I decided to find a solution that when iterating through the array, checks if the current element is higher than the previous element.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I created a variable called maxProfit that is initiated at 0 which stores the maximum profit of the array
2. I used a for loop to iterate through the array which starts at index 1 as the current element will be compared with the previous element
3. Inside of the for loop, I used an if statement to check if the current element is higher than the previous element which would indicate a profit
4. The current element's value has the previous element's value minused from it and is then added to the variable maxProfit's value and the total is assigned to maxProfit
5. Outside of the for loop, maxProfit is returned

## Code 📝
My solution to the task.
```java
class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit = 0;
        
        for(int i = 1; i < prices.length; i ++){
            if(prices[i] > prices[i - 1]){
                maxProfit = maxProfit + (prices[i] - prices[i - 1]);
            }
        }
        return maxProfit;
    }
}
```
