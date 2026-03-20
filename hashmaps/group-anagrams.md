# Group Anagrams

## Problem
Given an array of strings, group the anagrams together.

## Intuition
Words that are anagrams share the same sorted-character signature.

## Approach
- sort each word
- use the sorted word as a hashmap key
- append the original word into that group

## Complexity
- Time: O(n * k log k)
- Space: O(nk)

## Python
```python
from collections import defaultdict

def group_anagrams(strs):
    groups = defaultdict(list)
    for word in strs:
        key = ''.join(sorted(word))
        groups[key].append(word)
    return list(groups.values())
```

## What to remember
- this is a hashmap-pattern problem
- the key trick is choosing a stable signature
- sorted-string and frequency-count keys are both common
