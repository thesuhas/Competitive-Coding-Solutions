# Sum Of The Digits

Given a positive integer `num`, return the sum of its digits.

**Bonus:** Can you do it without using strings?

**Constraints:** `0 ≤ num < 2 ** 31`

**Link:** https://binarysearch.com/problems/Sum-of-the-Digits

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, num):
        ans = 0

        while num > 0:
            ans += num % 10
            num = num // 10

        return ans
```

## Approach

`ans` is the variable used to hold the sum of the digits of the number.<br>

In each iteration of the loop:

- `num % 10` which is the rightmost digit of `num` is added to `ans`
- `num // 10` is done to remove the rightmost digit via truncating division

**Time Efficiency:** _O(n)_ where `n` is the number of digits in the number.