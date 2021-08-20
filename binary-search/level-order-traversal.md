# Level Order Traversal

Given a binary tree `root` return a level order traversal of the node values.

**Constraints:** `n ≤ 100,000` where `n` is the number of nodes in `root`

**Link:** https://binarysearch.com/problems/Level-Order-Traversal

**Difficulty:** :yellow_circle: Medium

## Solution

```python
# class Tree:
#     def __init__(self, val, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def solve(self, root):
        
        if root == None:
            return []

        # queue for bfs
        q = []

        # Add first element to q
        q.append(root)

        # Level order traversal
        traversal = list()

        while len(q) > 0:
            
            # Get element
            el = q.pop(0)

            traversal.append(el.val)

            if el.left != None:
                q.append(el.left)
            
            if el.right != None:
                q.append(el.right)

        return traversal
```

## Approach

Used BFS to do Level Order Traversal. 
[Reading Material](https://www.geeksforgeeks.org/level-order-tree-traversal/)

**Time Efficiency:** _O(n)_ where `n` is the number of `nodes` in `root`