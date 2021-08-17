# Minimum Bracket Addition

Given a string s containing brackets `(` and `)`, return the minimum number of brackets that can be inserted so that the brackets are balanced.

**Constraints:** `n ≤ 100,000` where `n` is the length of `s`

**Link:** https://binarysearch.com/problems/Minimum-Bracket-Addition

**Difficulty:** <span style="color: green">Easy</span>

## Solution

```python
class Solution:
    def solve(self, s):
        stack = []

        count = 0

        for i in s:
            if i == ')':
                # If no opening brackets in stack
                if '(' not in stack:
                    count += 1
                else:
                    stack.pop()
            elif i == '(':
                stack.append('(')

        # Check for remaining '('
        if len(stack) > 0:
            count += len(stack)
        
        return count
```

## Approach

The `count` is used to keep track of the number of brackets required.<br>
A stack is used to keep track of all the opening brackets `(`.<br>

The following cases are encountered in each iteration:

- **Case 1:** If the current character is `(`. 
   
   - Add it to the stack.

- **Case 2:** If the current character is `)`.

   - **Case 2a:** If there is no `(` in the stack.
      
      - Increment `count` as we would require a `(` to balance the current `)`.
    
    - **Case 2b:** If there is a `(` in the stack.

      - Pop the `(` from the stack as it is used to balance the current `)`.

At the end, the number of `(` left in the stack (if any) are added as we would require an equal number of `)` to balance them.

**Time Efficiency:** _O(n)_ as we only iterate through the input string once.