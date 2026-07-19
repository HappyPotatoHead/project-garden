---
id: Binary Search
aliases: []
tags:
- binary search
- array
- leetcode
created: 19 July 2026
draft: false
title: Binary Search
---

# Keywords and Patterns

It is an extension of [[Two Pointers]], except that the input array has to be in a sorted manner (but not always the case!)

The basic binary search is simple,

```py
left = 0
right = len(l) - 1

while left <= right:
    middle = left + (right - left) // 2

    if l[middle] == target:
        return #answer
    elif l[middle] < target:
        left = middle + 1
    else:
         right = middle -1
```

## Narrowing Search Space

But, we can tweak this to serve one other purpose - the reduction of search space for other purposes

```py
left = 0
right = len(l) - 1

while left <= right:
    middle = left + ((right - left) // 2)

    if l[middle] < target:
        left = middle + 1
    else: right = middle - 1
```

As the loop executes, iteration after iteration, the search space will become smaller. This is especially useful in 2D matrices

## Binary Search on Answer Space

One other mind-boggling form of binary search is _binary search on answer space_.

This patter can easily be spotted with **a couple** of indicators:

1. Finding minimum / maximum
2. The arguments provided are an integer and a list

The template is as such:

```py
# these are boundaries, but for simplicity sake, I call them low and high
low = 0
high = max(l)

res = high

while low <= high:
    middle = low + ((high - low) // 2)

    total = 0
    for x in l:
      total += math.ceil(x/middle)

    if total <= k:
        res = mid
        high = mid - 1
    else:
        low = mid + 1

return res
```

There also exists a pattern within the logic block (_generally the for loop_):

1. Minimising the maximum
    - _Does the remainder carry over to the next?_
    - _Is any fractional leftover automatically counts as 1 whole unit of resource._
    - `math.ceil()` or integer trick (_just more trackers, really_)
2. Maximising the minimum
    - _Are the remainders essentially garbage?_
    - `//` is generally used

# Problems

- [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/description/)
- [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/description/)
- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/)
- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/description/)
