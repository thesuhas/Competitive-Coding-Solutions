# Unix Path Resolution

Given a Unix `path`, represented as a list of strings, return its resolved version.<br>

In Unix, `".."` means to go to the previous directory and `"."` means to stay on the current directory. By resolving, we mean to evaluate the two symbols so that we get the final directory we're currently in.

**Constraints:** `n ≤ 100,000` where `n` is the length of `path`

**Link:** https://binarysearch.com/problems/Unix-Path-Resolution

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, path):
        s = list()

        for i in path:
            if i == '..':
                if len(s) != 0:
                    s.pop()
            elif i != '.':
                s.append(i)
            
        return s
```

## Approach

A stack can be used.<br>
When a previous directory, i.e., `..` is encountered, we pop an element from the stack, i.e., we go up by a directory.<br>
When current directory, i.e., `.` is encountered, nothing is done as we are in the current directory.<br>
When other path elements are encountered, we go to that directory, i.e., it is added to the stack.