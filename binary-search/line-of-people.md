# Line Of People

You are given integers `n`, `a` and `b`. You are standing in a line of `n` people. You don't know which position you're in, but you know there are at least `a` people in front of you and at most `b` people behind you.

Return the number of possible positions you could be in.

**Link:** https://binarysearch.com/problems/Line-of-People

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, n, a, b):
        count = 0
        end = min(b, (n - 1 - a))
        return end + 1
```

## Approach

If the possible positions are looked at as an array of indices:

- **in front** means to the right
- **behind** means to the left

The viable solutions have to meet both of these constraints:

- Cannot be at an index greater than `b` (distance from left, or people behind)
- Cannot be at an index greater than `n - 1 - a` where `n-1` is the last index (distance from right, or people in front).

Appropriate number of positions can be found via `min(b, n - 1 - a) + 1`. The `1` is added to ensure last possible index is included.