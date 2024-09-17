---
tags:
  - dnc
  - binary-search
---
# 1. Binary Search and related
Created Mon Jul 29, 2024 at 9:48 PM

*The mother of all divide-and-conquer algorithms is binary search.*

## Counting occurrences
- Naive algo uses "exact binary search" and then a simple loop

A complete logn solution is possible. We need to find left and right index of the block of keys (they will be continuous), i.e. use lower-bound and upper-bound.

Proof that lower and upper bound binary search is possible - lets prove only upper. Since we disregard one side (left or right) in binary search, we can keep disregarding values > key (but note it) as well as <= key. This way the upper bound will keep on improving (i.e. moving left).

Two binary searches are still logarithmic. So logn.
## One sided binary search
Suppose we have an array that has 0s at the beginning, and then an unbouned number of 1s afterwards.

Usual binary search (start + end/2) won't work here, since 1s are unbounded.

But binary search still applies here. Instead of partitioning the space, like usual, we need to start from some point (0 index is fine), and do jumps. And the place a jump lands at will decide which direction to jump next. We of course jump twice the distance as much as the previous jump.

This is called one sided binary search.


## Square root and solving equations
The 'bisection method' is a technique in numerical analysis based on binary search.

- Find square root. Assume r<sup>2</sup> = n, and n > 1 (lets ignore less than 1 args for now). We start `l` = 1 and `m` = n, we compute = `l` + `m`/2, and check if the square more/less than `n`, and update `l` or `m`, do this repeatedly, to arrive at an answer.
- Find roots of any equation - Suppose we have an equation `f(x)=0`. Assuming we know two args `l` and `r` such that `f(l)` and `f(r)` have different signs, then a loot must exist between `l` and `r`. We try `l + r`/2, than cut the window such that sign change is maintained. Repeatedly doing this yields the solution. *Works on continuous equations only*.

*Binary search and its variants are the quintessential divide-and-conquer algorithms.*