# Kth Last Node Of A Linked List

Given a singly linked list `node`, return the value of the `kth` last node (0-indexed). `k` is guaranteed not to be larger than the size of the linked list.

This should be done in _O(1)_ space.

**Constraints:** `n ≤ 100,000` where `n` is the length of `node`

**Link:** https://binarysearch.com/problems/Kth-Last-Node-of-a-Linked-List

**Difficulty:** :yellow_circle: Medium

## Soltuion

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node, k):
        
        # First obtain length of the list
        l = 0

        temp = node

        while temp != None:
            temp = temp.next
            l += 1
        
        # Now get appropriate index
        l -= 1
        temp = node
        while l > k:
            temp = temp.next
            l -= 1

        return temp.val
```

## Approach

`l` represents the length of the Linked List. `temp` is a temporary pointer. <br>
The first while loop is used to get the length of the linked list.<br>
The second while loop starts from the last index and goes till the `l == k` which is the required value.

**Time Efficiency:** _O(n)_