# Central Linked List

Given a singly linked list `node`, return the value of the middle node. If there's two middle nodes, then return the second one.

**Bonus:** Solve using _O(1)_ space.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Central-Linked-List

**Difficulty:** :yellow_circle: Medium

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):
        # Get length of the list
        l = 0
        temp = node

        while temp != None:
            temp = temp.next
            l += 1

        # Reduce value by 1
        l -= 1
        mid = 0
        # If l is odd
        if (l % 2 != 0):
            mid = l // 2
            mid += 1
        # If l is even
        else:
            mid = l // 2
        # Counter variable
        c = 0
        temp = node
        while c < mid:
            temp = temp.next
            c += 1
        return temp.val
```

## Approach

`l` is used to store the length of the Linked List. It is decremented by one to find the last index.<br>
`mid` is used to find the index of the middle element. There are two possible values to `mid`:

- **Case 1:** `l` is odd.
  
  - In this case there are two middle nodes and the second one is taken.

- **Case 2:** `l` is even.
  
  - In this case there is only one middle node.

The list is then iterated till we reach the `mid` node.

**Time Efficiency:** _O(n)_