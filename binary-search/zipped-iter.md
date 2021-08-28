# Zipped Iterator

Implement a zip iterator of two lists of integers `a` and `b` where

- `next()` polls the next element in the iterator, alternating between `a` and `b`
- `hasnext()` which returns whether the next element exists

**Constraints:** `n ≤ 100,000` where `n` is the number of calls to `next` and `hasnext`

**Link:** https://binarysearch.com/problems/Zipped-Iterator

**Difficulty:** :yellow_circle: Medium

## Solution

```python
class ZippedIterator:
    def __init__(self, a, b):
        self.a = a
        self.b = b
        if len(a) > 0:
            self.it = 'a'
        else:
            self.it = 'b'
        self.next_a = -1
        self.next_b = -1

    def next(self):
        if self.it == 'a':
            if self.next_b + 1 < len(self.b):
                self.it = 'b'
            self.next_a += 1
            return self.a[self.next_a]
        else:
           if self.next_a + 1 < len(self.a):
               self.it = 'a'
           self.next_b += 1
           return self.b[self.next_b] 

    def hasnext(self):
        if self.it == 'a':
            return (self.next_a + 1) < len(self.a)
        else:
            return (self.next_b + 1) < len(self.b)
```

## Approach

Initiate the object with the following:

- The list `a`
- The list `b`
- The first list to be iterate, it is assigned as `a` unless it is empty, in that case, it is `b`
- `next` variable for both is `-1`

`next` is implemented as:

- If the current iterator is `a`, check if there is an element in `b`, change iterator to `b` and return next element in `a` and vice versa

`hasnext` is implemented as:

- If iterator is `a`, check if next element in `a` exists and the same for `b`.