# Minimum Stack

Implement a stack with the following methods:

- `MinimumStack()` constructs a new instance of a minimum stack
- `append(int val)` appends val to the stack
- `peek()` retrieves the last element in the stack
- `min()` retrieves the minimum value in the stack
- `pop()` pops and returns the last element in the stack

<br>Each method should be done in _O(1)_ time. You can assume that for `peek`, `min` and `pop`, the stack is non-empty when they are called.

**Constraints:** `n ≤ 100,000` where `n` is the number of calls to `append`, `peek`, `min`, and `pop`.

**Link:** https://binarysearch.com/problems/Minimum-Stack

**Difficulty:** :green_circle: Easy

## Solution

```python
class MinimumStack:
    def __init__(self):
        self.stack = list()
        self.mini = math.inf

    def append(self, val):
        if val < self.mini:
            self.mini = val
        self.stack.append(val)

    def peek(self):
        return self.stack[-1]

    def min(self):
        return self.mini

    def pop(self):
        el = self.stack.pop()
        if len(self.stack) > 0:
            if el == self.mini:
                self.mini = min(self.stack)
        else:
            self.mini = math.inf
        return el
```

## Approach

Initialise the Minimum Stack with:

- `self.stack` representing a stack.
- `self.mini` represents the current minimum element in the stack, initialised to infinity.

On appending an element to the stack, you check if that element is lesser than `self.mini`, it is assigned to it if it is indeed lesser.<br>

On popping an element,

- if the stack has elements, `self.mini` is updated to the new minimum.
- if the stack is empty, `self.mini` is updated to infinity.

