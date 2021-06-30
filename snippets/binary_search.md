---
title: binary_search
tags: algorithm,array,beginner
firstSeen: 2021-06-30T00:47:09+17:00
---

Finds the index of a given element in a sorted array using the binary search algorithm.

- Declare the left and right search boundaries, `l` and `r`, initialized to `0` and to one minus the `len` of the array respectively.
- Use a `while` loop to repeatedly narrow down the search subarray, use the floor division operator `(l + r) // 2` to calculate where to cut it in half.
- Return the index of the element if found, otherwise return `-1`.
- **Note:** Does not account for duplicate values in the array.

```python
def binary_search(arr, item):
  l = 0
  r = len(arr) - 1
  while l <= r:
    mid = (l + r) // 2
    guess = arr[mid]
    if guess == item:
      return mid
    if guess > item:
      r = mid - 1
    else:
      l = mid + 1
  return -1
```

```python
binary_search([1, 2, 3, 4, 5], 1) # 0
binary_search([1, 2, 3, 4, 5], 5) # 4
binary_search([1, 2, 3, 4, 5], 6) # -1
```
