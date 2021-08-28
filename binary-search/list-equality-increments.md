# List Equality with Increments

You are given a list of integers `nums`, and want to make the values equal. Consider an operation where you pick an integer in the list and increment every other value .

Return the minimum number of operations required to make integer values equal.

**Constraints:** `n ≤ 100,000` where `n` is the length of `nums`

**Link:** https://binarysearch.com/problems/List-Equality-with-Increments

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, nums):
        
        return sum(nums) - (len(nums) * min(nums))
```

## Approach

Incrementing every other value, is the same as decrementing all the values except the smallest value.<br>

The number of operations is equal to `sum of old list` - `sum of new list`. <br>

The `new list` contains only the smallest element in the old list.