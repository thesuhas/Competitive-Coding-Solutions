# A Strictly Increasing Linked List

Given the head of a singly linked list `head`, return whether the values of the nodes are sorted in a strictly increasing order.

**Constraints:** `1 ≤ n ≤ 100,000` where `n` is the number of nodes in `head`

**Link:** https://binarysearch.com/problems/A-Strictly-Increasing-Linked-List

**Difficulty:** :green_circle: Easy

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, head):
        
        # If length of linked list is 1
        if (head.next == None):
            return True

        # If not
        first = head
        second = head.next

        while first != None and second != None:
            if first.val >= second.val:
                return False
            second = second.next
            first = first.next

        return True
```

## Approach

Two pointers are used:

- `first` indicating the first element being looked at.
- `second` indicating the second element being looked at. `first.next == second`

At every iteration of the loop:

- `first` and `second` are compared to see if `second` is greater than `first`, i.e., whether they are **strictly increasing** or not

  - If `second` is not greater than `first`, then it is not strictly increasing.

**Time Efficiency:** _O(n)_ as the given Linked List is traversed only once.
