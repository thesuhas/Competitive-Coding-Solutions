# Linked List to Zig Zag Tree Path

Given a singly linked list `node`, convert it to a binary tree path using these rules:

- The head of the linked list is the root.
- Each subsequent node is the left child of the parent if its value is smaller, otherwise it's the right child.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Linked-List-to-ZigZag-Tree-Path

**Difficulty:** :yellow_circle: Medium

## Solution

```python
# class Tree:
#     def __init__(self, val, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):

        if node == None:
            return None

        root = Tree(node.val)

        tempL = node.next
        prev = node
        tempR = root

        while tempL != None:
            if tempL.val < prev.val:
                tempR.left = Tree(tempL.val)
                tempR = tempR.left
            else:
                tempR.right = Tree(tempL.val)
                tempR = tempR.right
            prev = tempL
            tempL = tempL.next

        return root
```

## Approach

`tempL` refers to next node of the Linked List and `tempR` refers to the next node of the BST.<br>
`prev` is used to refer to the previous node of the Linked List.<br>
If the next node is lesser than the previous node, it is added as the left child. Else, it is added as the right child.

**Time Efficiency:** _O(n)_ where `n` is the length of the Linked List.