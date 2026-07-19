---
id: Two Pointers
aliases: []
tags:
- arrays
- two pointers
- leetcode
created: 19 July 2026
draft: false
title: Two Pointers
---

# Keywords and Patterns

Whenever you have to keep track of two things at once, this is probably the _go-to_. Of course there are _n-pointers_ problems, but in principle, most of them are the same.

> An evolution of the _two pointers_ problem would be _binary search_

The pattern goes as such,

```py

# based on the defined search space
# in this case, the entire list
left = 0
right = len(some_list) - 1

while left < right:
    if condition_left:
        left += 1
    elif condition_right:
        right -= 1
    else:
        # set of condition
        left += 1
        right -= 1
```

> The condition to move the pointers is the tricky part

# Examples

## Valid Palindrome

Problem here: [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

> [!warning]- Solve the problem first!
>
> _Snippet_
>
> ```py
>
> string = list(s.lower())
> left = 0
> right = len(s) - 1
>
> while left < right:
>     if not string[left].isalnum():
>         left += 1
>     elif not string[right].isalnum():
>         right -= 1
>     else:
>         if string[left] != string[right]:
>             return False
>         left += 1
>         right -= 1
>
> return True
> ```
>
> We update both left and right **simultaneously** because we're checking letters from both ends **simultaneously**

This is a relatively short but important topic, so make sure this is understood well.

# Problems

- [Container With Most Water](https://leetcode.com/problems/container-with-most-water/description/)
- [3Sum](https://leetcode.com/problems/3sum/description)
- [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description)
