# Valid Anagram

## Problem
Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.

## Intuition
If two strings are anagrams, they contain the same characters with the same frequencies.

## Approach
Count characters in one string and subtract counts using the other.
If every frequency ends at zero, the strings are anagrams.

## Complexity
- Time: O(n)
- Space: O(k), where k is the number of distinct characters

## Python
```python
def is_anagram(s: str, t: str) -> bool:
    if len(s) != len(t):
        return False

    count = {}
    for ch in s:
        count[ch] = count.get(ch, 0) + 1

    for ch in t:
        if ch not in count:
            return False
        count[ch] -= 1
        if count[ch] < 0:
            return False

    return True
```

## What to remember
- always check lengths first
- hashmap frequency counting is the default move here
- sort-based solution works too, but is slower: O(n log n)
