# Binary Search

## Problem
Given a sorted array of integers and a target value, return the index of the target if it exists, otherwise return `-1`.

## Intuition
Because the array is sorted, each comparison lets us eliminate half the search space.

## Approach
Use two pointers, `left` and `right`, and repeatedly check the middle element.
- if `nums[mid] == target`, return `mid`
- if `nums[mid] < target`, search the right half
- otherwise search the left half

## Complexity
- Time: O(log n)
- Space: O(1)

## Python
```python
def binary_search(nums, target):
    left, right = 0, len(nums) - 1

    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        if nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1
```

## What to remember
- works only when the search space is ordered in a useful way
- watch the loop condition: usually `left <= right`
- this pattern comes up everywhere, not just arrays
