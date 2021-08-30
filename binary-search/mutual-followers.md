## Mutual Followers

You are given a two-dimensional list of integers `relations`. Each element `relations[i]` contains `[a, b]` meaning that person `a` is following person `b` on Twitter.

Return the list of people who follow someone that follows them back, sorted in ascending order.

**Constraints:** `0 ≤ n ≤ 100,000` where `n` is the length of `relations`

**Link:** https://binarysearch.com/problems/Mutual-Followers

**Difficulty:** :green_circle: Easy

## Solution

```python
class Solution:
    def solve(self, relations):
        
        maps = dict()
        ans = set()

        for i in relations:
            if i[0] not in maps:
                maps[i[0]] = [i[1]]
            else:
                # Add to list of people being followed by i[1]
                maps[i[0]].append(i[1])
            # Checks if i[1] also follows i[0]
            if i[1] in maps and i[0] in maps[i[1]]:
                # Both i[0] and i[1] follow someone who follows them back
                ans.add(i[0])
                ans.add(i[1])

        return list(ans)
```

## Approach

Maintain the following structures:

- `maps` which is a dictionary where `maps[i]` is a list of all the people that `i` follows
- `ans` which is a set of all people that follow someone that follows them back

