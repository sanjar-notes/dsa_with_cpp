---
tags:
  - dnc
---
# 4. Largest subrange and closest pair
Created Tue Jul 30, 2024 at 12:14 AM

page 173-174
## Largest subrange (aka max subarray sum)
The block must be on the left, right or straddling-the-middle.

Note:
- Her, Kadane's algorithm is better than DnC. O(n), O(1) vs O(nlogn), O(logn)

## Closest pair
Assume a number line with some points. We need to find a pair of points with the shortest distance.

- Naive solution - convert points to edges, sort and choose the min. This is O(nlgn) and O(n), time and space.
- DnC: We draw a middle line, the pair is on the left, the right or straddling the center. The subproblem solution gives us a pair. Choosing between left, right and straddling the center (we just get the two middle points, O(1) since array) is O(1), so T(n) = 2 T(n/2) + O(1). By master theorem, complexity is O(n).

So DnC is better here, O(n) and O(lgn), time and space.

This may seem insignificant for time, but the solution works for 2D as well, so it is significant.