# Linked List Deletion

Given a singly linked list `node`, and an integer `target`, return the same linked list with all nodes whose value is `target` removed.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Linked-List-Deletion

**Difficulty:** :green_circle: Easy

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node, target):
        
        # temp pointer
        temp = node
        prev = None

        while temp != None:
            if temp.val == target:
                # if not first node
                if prev != None:
                    # Next of new previous is next of temp
                    prev.next = temp.next
                # If first node
                elif prev == None:
                    node = temp.next
            else:
                # Move by to temp if it is to not be deleted
                prev = temp
            temp = temp.next

        return node
```

## Approach

The following pointers are used:

- `temp`: a temp pointer used to traverse `node`
- `prev`: a pointer used to represent the previous node in the new list

