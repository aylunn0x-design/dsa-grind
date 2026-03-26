# Best Time to Buy and Sell Stock

## Problem
Given an array where `prices[i]` is the price of a stock on day `i`, return the maximum profit you can make from one buy and one sell.

## Intuition
You want the cheapest price before the current day and the biggest gap after that.

## Approach
- track the minimum price seen so far
- at each step, compute profit if selling today
- keep the best profit

## Complexity
- Time: O(n)
- Space: O(1)

## Python
```python
def max_profit(prices):
    min_price = float('inf')
    best = 0

    for price in prices:
        min_price = min(min_price, price)
        best = max(best, price - min_price)

    return best
```

## What to remember
- this is really a running minimum pattern
- don’t overcomplicate it with nested loops
