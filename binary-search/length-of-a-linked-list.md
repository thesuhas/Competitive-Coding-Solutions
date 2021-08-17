# Length Of A Linked List

Given a singly linked list `node`, return its length. The linked list has fields `next` and `val`.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Length-of-a-Linked-List

**Difficulty:** :green_circle: Easy

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):
        counter = 0

        while node != None:
            counter += 1
            node = node.next

        return counter
```

## Approach

`None` is used to represent when a pointer points to `NULL` in Python. <br>
A `counter` variable is used to keep track of length. <br>
The list is iterated through till we reach `None` (which indicates the entire list has been traversed) and the `counter` is incremented simultaneously.

**Time Efficiency:** _O(n)_

