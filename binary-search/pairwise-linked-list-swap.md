# Pairwise Linked List Swap

Given a singly linked list `node`, swap each pair of nodes and return the new head.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Pairwise-Linked-List-Swap

**Difficulty:** :yellow_circle: Medium

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):
        
        # If empty list
        if node == None:
            return None

        # If list length one
        if node.next == None:
            return node

        # Two pointers
        first = node
        second = node.next

        # Temp pointer
        head = node.next
        temp = None
        prev = None

        while first != None and second != None:
            # Point first to successor of second
            first.next = second.next
            # Successor of second is now first
            second.next = first
            # Swap first and second
            temp = first
            first = second
            second = temp
            # If prev exist
            if prev != None:
                prev.next = first
            # Go to next nodes
            if second.next and first.next:
                prev = second
                second = second.next.next
                first = first.next.next
            else:
                break

        return head
```


## Approach

Two pointers to traverse the linked list:

- `first` representing the first node in each pair.
- `second` representing the second node in each pair.

Two temporary pointers:

- `temp` used to swap the two pointers to get the new `first` and `second`.
- `prev` used to get the previous node (second node from last iteration) to update its pointer.

On every iteration of the loop:

- Change `first` so that it points to the `next` of `second`.
- Change `second` so that its next node is now `first`.
- Swap `first` and `second` to get the updated order (post pointer re-assignment).
- If it is not the first iteration, need to update the pointer of `prev`, i.e., **new** `second` of the **last iteration** to point to the **new** `first`.
- Check if another pair exists, if yes, go to next iteration.
