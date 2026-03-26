# Number of Islands

## Problem
Given a grid of `1`s and `0`s, count how many islands there are.

## Intuition
Every time you find land that hasn't been visited, you can flood-fill the entire island.

## Approach
- loop through the grid
- when you see unvisited land, increment count
- run DFS/BFS to mark the full island as visited

## Complexity
- Time: O(m * n)
- Space: O(m * n) worst case because of recursion/stack

## Python
```python
def num_islands(grid):
    if not grid:
        return 0

    rows, cols = len(grid), len(grid[0])
    seen = set()

    def dfs(r, c):
        if (
            r < 0 or r >= rows or
            c < 0 or c >= cols or
            grid[r][c] == '0' or
            (r, c) in seen
        ):
            return
        seen.add((r, c))
        dfs(r + 1, c)
        dfs(r - 1, c)
        dfs(r, c + 1)
        dfs(r, c - 1)

    islands = 0
    for r in range(rows):
        for c in range(cols):
            if grid[r][c] == '1' and (r, c) not in seen:
                islands += 1
                dfs(r, c)

    return islands
```

## What to remember
- classic graph traversal in disguise
- grids often turn into DFS/BFS problems fast
