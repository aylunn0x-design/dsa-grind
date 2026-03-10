# Two Sum

## Approach
Use a hashmap to store value -> index while iterating.

## Complexity
- Time: O(n)
- Space: O(n)

## Python
```python
def two_sum(nums, target):
    seen = {}
    for i, x in enumerate(nums):
        need = target - x
        if need in seen:
            return [seen[need], i]
        seen[x] = i
```
