# Palindrome Count

You are given a string `s` and an integer `k`. Return the number of palindromes you can construct of length `k` using only letters in `s`. Letters can be used more than once.

**Constraints:** `n ≤ 100,000` where `n` is the length of `s`

**Link:** https://binarysearch.com/problems/Palindrome-Count

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, s, k):
        
        return len(set(s)) ** math.ceil(k/2)
```

## Approach

Every unique letter can be stored in every **spot**. The number of spots are `k/2` as a palindrome is a mirror.<br>
At every **spot**, `no of possible characters = no of unique characters`. Hence, you multiply `no of unique characters` with itself **spot** times.