# Binary Search Tree Iterator

Implement a binary search tree iterator with the following methods:

- `next` returns the next smallest element in the tree
- `hasnext` returns whether there is a next element in the iterator

**Link:** https://binarysearch.com/problems/Binary-Search-Tree-Iterator

**Difficulty:** :yellow_circle: Medium

## Solution:

```python
# class Tree:
#     def __init__(self, val, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class BSTIterator:
    def __init__(self, root):
        self.tree = []
        self.count = -1

        def inorder(root):
            if root != None:
                inorder(root.left)
                self.tree.append(root.val)
                inorder(root.right)

        inorder(root)

    def next(self):
        self.count += 1
        return self.tree[self.count]

    def hasnext(self):
        return (self.count + 1) < len(self.tree)
```

## Approach

#### Initialisation

- Initialise an array `self.tree` to hold the elements in ascending order. This order is obtained by perform `inorder traversal` of the given BST.
- Initialise a counter `self.count` that keeps track of the current element being looked at.

#### Next

- Update counter to point to the next smallest element.
- Return the next smallest element.

#### Hasnext

- Check if the next index is in the proper bounds for `self.tree`.
