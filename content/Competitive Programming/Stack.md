---
id: Stack
aliases: []
tags:
- stack
- monotonic stack
- leetcode
created: 19 July 2026
draft: false
title: Stack
---

# Keywords and Patterns

Usually things related to immediate paring ([valid parentheses](https://leetcode.com/problems/valid-parentheses/description/), [reverse polish notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/)); these are relatively simple as all you do is append or remove immediately at relatively simple conditions (comparing with existing mapping or from within the stack itself).

The more interesting form of the problem is monotonic stack; monotonic stacks involve some form of indexing (most of the time anyway). If a problem mentions _next greater_ or _next smaller/lesser_ alongside _overlap_ or _collide_, chances are, it's a monotonic stack problem.

The pattern (monotonic stack) goes as such,

```py

# this will hold the indices
stack = []
result = [] # [0] * len(argument) <- depends on the problem

for index, value in enumerate(argument):
    # > for greater than < for less than
    while stack and value > argument[stack[-1]]:
        # .pop() the latest added index (stack)
        # logical processes goes here

    # append the latest index
    stack.append(index)

return result

```

# Examples

## Daily Temperatures

Problem here: [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/description/)

> [!warning]- Solve the problem first!
>
> _Snippet_
>
> ```py
>
> stack = []
> result = [0] * len(temperatures)
> for index, temperature in enumerate(temperatures):
>   while stack and temperature > temperatures[stack[-1]]:
>       prev = stack.pop()
>       result[prev] = index - prev
>   stack.append(index)
> return result
> ```

# Problems

- [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)
- [Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/)
- [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/description/)
- [Car Fleet](https://leetcode.com/problems/car-fleet/description)
