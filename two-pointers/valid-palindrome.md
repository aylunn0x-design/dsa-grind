# Valid Palindrome

## Problem
Given a string, return `true` if it is a palindrome after converting all uppercase letters into lowercase letters and removing non-alphanumeric characters.

## Intuition
A palindrome reads the same from both ends, so two pointers are enough.

## Approach
- use `left` and `right`
- skip non-alphanumeric characters
- compare lowercase characters
- move inward until pointers cross

## Complexity
- Time: O(n)
- Space: O(1)

## Python
```python
def is_palindrome(s: str) -> bool:
    left, right = 0, len(s) - 1

    while left < right:
        while left < right and not s[left].isalnum():
            left += 1
        while left < right and not s[right].isalnum():
            right -= 1

        if s[left].lower() != s[right].lower():
            return False

        left += 1
        right -= 1

    return True
```

## What to remember
- classic two-pointer pattern
- clean pointer movement matters more than fancy code
