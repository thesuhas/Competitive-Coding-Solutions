# Length of Longest Balanced Subsequence

Given a string `s` containing brackets `"("` and `")"`, return the length of the longest subsequence of balanced brackets.

**Constraints:** `n ≤ 100,000` where `n` is length of `s`.

**Link:** https://binarysearch.com/problems/Length-of-Longest-Balanced-Subsequence

**Difficulty:** :yellow_circle: Medium

## Solution

```python
class Solution:
    def solve(self, s):
        
        stack = []

        count = 0

        for i in s:
            if i == '(':
                stack.append(i)
            elif i == ')':
                if len(stack) > 0:
                    if stack[-1] == '(':
                        stack.pop()
                        count += 2
        return count
```

## Approach

A stack is used to keep track of the opening and closing brackets.<br>

When an open bracket `(` is encountered, it is added to the stack.<br>

When a closing bracket `)` is encountered, if the stack is not empty and contains an opening bracket `(` is the last element in the stack, it is a part of the longest balanced subsequence and the `counter` is updated to reflect the same.

**Time Efficiency:** _O(n)_ where `n` is the length of the string `s`.