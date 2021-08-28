# Ugly Number

Given an integer `n`, return whether its prime factors only include `2`, `3` or `5`.

**Constraints:** `0 ≤ n < 2 ** 31`

**Link:** https://binarysearch.com/problems/Ugly-Number

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, n):
        
        if n == 0:
            return False

        while n % 2 == 0:
            n = n // 2

        while n % 3 == 0:
            n = n // 3

        while n % 5 == 0:
            n = n // 5

        return n == 1
```

## Approach

If the number is 0, return `False`.<br>
Removing all the `2`, `3`, `5` from the number. If the number is not `1`, it has other factors.