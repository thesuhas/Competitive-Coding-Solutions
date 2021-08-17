# Linked List To Integer

Given a single linked list `node`, representing a binary number with most significant digits first, return it as an integer.

**Constraints:** `n ≤ 30` where `n` the number of nodes in `node`

**Link:** https://binarysearch.com/problems/Linked-List-to-Integer

**Difficulty:** :green_circle: Easy

## Solution

```python
# class LLNode:
#     def __init__(self, val, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def solve(self, node):
        num = 0

        # Convert to integer form (still binary representation)
        while node != None:
            num = (num * 10) + node.val
            node = node.next
        
        count = 0
        ans = 0
        while num > 0:
            ans += (num % 10) * math.pow(2, count)
            num = num // 10
            count += 1
        
        return ans
```

## Approach:

`num` represents the number stored in the linked list in integer form.<br>
The first while loop is user to convert the number to integer form (still binary). <br>
`ans` is used to store the number in base 10.<br>
`count` is used to check the power that the current binary digit represents.

In the second while loop:

- The rightmost digit of `num` is extracted and multiplied with the respective power of 2 using `count` and added to `ans`.
- The rightmost digit of `num` is removed via truncating division.
- The power of the binary digit stored in `count` is incremented.

**Time Efficiency:** _O(n)_