# Unobstructed Buildings

You are given a list of integers heights representing building heights. A building `heights[i]` can see the ocean if every building on its right has shorter height. Return the building indices where you can see the ocean, in ascending order.

**Constraints:** `0 ≤ n ≤ 100,000` where `n` is the length of `heights`

**Link:** https://binarysearch.com/problems/Unobstructed-Buildings

## Solution

```python
class Solution:
    def solve(self, heights):

        if len(heights) == 0:
            return []

        ans = []
        s = 0

        for i in range(len(heights) - 1, -1, -1):
            if heights[i] > s:
                ans.append(i)
                s = heights[i]
        
        return ans[::-1]   
```

## Approach

Traverse `heights` from **right to left**. Check if `heights[i]`, i.e., the current building, is the tallest building so far. If yes, add `i` to the required list of buildings and also update the height of the tallest bui;ding encountered so far, which is `s`.

**Time Efficiency**: _O(n)_
