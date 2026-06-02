# Best Time to Buy and Sell Stock

## Problem

Given stock prices:

Find maximum profit.

You can:

- Buy once
- Sell once

Buy before selling.

Example:

Input:

[7,1,5,3,6,4]

Output:

5

Buy at 1

Sell at 6

Profit = 5

---

## Main Idea

Keep track of:

minimum price seen so far

Calculate profit at every step.

Formula:

profit = currentPrice - minimumPrice

Store maximum profit.

---

## Algorithm

1. Take minimum price as first element

2. Traverse array

3. Update minimum price

4. Calculate profit

5. Store maximum profit

---

## Code

```java
class Solution {
    public int maxProfit(int[] prices) {

        int min = prices[0];
        int profit = 0;

        for(int i=1;i<prices.length;i++)
        {
            if(prices[i] < min)
            {
                min = prices[i];
            }

            int currProfit = prices[i] - min;

            profit = Math.max(profit, currProfit);
        }

        return profit;
    }
}
```

## Dry Run

prices:

[7,1,5,3,6,4]

Start:

min = 7

profit = 0

1:

min = 1

5:

profit = 5-1 = 4

3:

profit = max(4,2)

6:

profit = max(4,5)

profit = 5

4:

profit stays 5

Answer:

5

---

## Complexity

Time Complexity:

O(n)

Space Complexity:

O(1)

---

## Key Intuition

Keep track of cheapest buying price.

Check maximum selling profit every day.
