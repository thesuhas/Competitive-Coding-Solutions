# Level Order Binary Search Tree to Linked List

Given a binary tree `root`, convert it to a singly linked list using level order traversal.

**Constraints:** `1 ≤ n ≤ 100,000` where `n` is the number of nodes in `root`

**Link:** https://binarysearch.com/problems/Level-Order-Binary-Tree-to-Linked-List

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
    def solve(self, root):
        
        q = [root]

        head = LLNode(root.val)
        temp = head.next
        p = head

        while len(q) > 0:
            el = q.pop(0)

            # Assign value to linked list
            temp = LLNode(el.val)
            if p != None:
                p.next = temp
            p = temp
            temp = temp.next

            if el.left != None:
                q.append(el.left)
            if el.right != None:
                q.append(el.right)

        return head.next
```

## Approach

Apply BFS to the BST to get **Level Order Traversal**. As nodes are being popped out of the queue, add to the linked list.

**Note:** `head.next` is returned as the head of the tree is copied to the linked list twice.