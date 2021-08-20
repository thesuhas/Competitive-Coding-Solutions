# Count Substring With All 1s

You are given a string `s` containing `"1"`s and `"0"`s. Return the number of substrings that contain only `"1"`s. Mod the result by `10 ** 9 + 7`.

**Constraints:** `0 ≤ n ≤ 100,000` where `n` is the length of `s`

**Link:** https://binarysearch.com/problems/Count-Substrings-With-All-1s

**Difficulty:** :yellow_circle: Medium

## Solution

```python
class Solution:
    def solve(self, s):
        
        count = 0

        for i in range(len(s)):
            if s[i] != '0':
                for j in range(i + 1, len(s) + 1):
                    if s[j - 1] == '0':
                        break
                    count += 1

        return (count % (10 ** 9 + 7))
```

## Approach

Initialise a `count` variable to keep track of all the substrings that meet the desired conditions.<br>

For a given starting character of a substring, if it is a `"0"`, it fails the required conditions.<br>

For a given ending character of a substring, if it is a `"0"`, the substring and all strings that this is a substring of fail the required conditions.<br>

**Time Efficiency:** _O(n<sup>2</sup>)_ as there are two nested loops looking at each possible start and end character combinations to generate all the substrings.
