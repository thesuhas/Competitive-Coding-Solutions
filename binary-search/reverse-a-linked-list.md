# Reverse A Linked List

Given a singly linked list node, return its reverse.

**Bonus:** Can you do this in _O(1)_ space?

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Reverse-a-Linked-List

**Difficulty:** <span style="color: yellow">Medium</span>

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):
        
        # If length 0
        if node == None:
            return None

        # If length 1, return
        if node.next == None:
            return node
        
        prev = None
        temp = node
        n = None

        while temp != None:
            n = temp
            temp = temp.next
            n.next = prev
            prev = n

        return n
```

## Approach

- `prev` refers to previous node
- `temp` refers to a temp pointer
- `n` refers to current node

At each iteration, do the following steps:

- assign `n` to `temp`, i.e., set the current node
- move `temp` to point to the next node, i.e., `temp.next`
- assign current node's next to the previous node, i.e., `prev`
- update previous node to point to the current node (to be used in the next iteration)

**Time Efficiency:** _O(n)_ as the linked list is traversed once

**Space Efficiency:** _O(1)_ as only 3 extra pointers are used irrespective of input size