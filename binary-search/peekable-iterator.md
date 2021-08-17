# Peekable Iterator

Implement an iterator of a list of integers nums where
- `peek()` returns the next element, without moving the iterator
- `next()` polls the next element in the iterator
- `hasnext()` which returns whether the next element exists

**Constraints:** `n ≤ 100,000` where `n` is the number of calls to `peek`, `next` and `hasnext`

**Link:** https://binarysearch.com/problems/Peekable-Iterator

## Solution

```python
class PeekableIterator:
    def __init__(self, nums):
        self.nums = nums
        self.current = -1

    def peek(self):
        return self.nums[self.current + 1]

    def next(self):
        self.current += 1
        return self.nums[self.current]

    def hasnext(self):
        return (self.current + 1) < len(self.nums)
```

## Approach

### Initialisation

Store the array in the object as `self.nums`. <br>
Initialise the current position as `self.current = -1`. This is done as we have not gone to the `next` element yet, which in this case is the first element.

### Peek

Go to index `self.current + 1` which represents the next element and return it.

### Next

Go to the next element, i.e., `self.current += 1`. Then, return the element.

### HasNext

Checks if the next element is valid. It is valid if the next element's index is lesser than the length of `self.nums`.