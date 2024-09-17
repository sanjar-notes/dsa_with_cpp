---
tags:
  - dp
---
# 1. Edit Distance
Created Tue Aug 6, 2024 at 11:16 PM

aka Approximate-String-Matching (Skiena page 314)
## Edit distance
We see that a naive solution would take long, since we need to consider all possibilities. We want to minimize edits while considering all possibilities, so DP may be applicable.

We start from the right side. And make ops on P. Ops are M (match), S (substitute), I (Insert) and D (delete).
Lets try to figure out a recurrence relation.

diff(P, i, T, j) =
- M: diff(P, i-1, T, j-1). Since both characters matched, move both pointers, in P and T by one.
- S: 1 + diff(P, i-1, T, j-1). Substitute to match, move both pointers, in P and T by one.
- I: 1 + diff(P, i, T, j-1). Insert at end of P to match T. Move point in T by one.
- D: 1 + diff(P, i-1, T, j). Move point in T by one.

Lets trace how diff(P, 5, T, 4) would look.
(5, 4) -> \[(4, 4), (4, 4), (5, 3), (4, 4)]. Already 3 times repeat.
(4, 4) -> \[(3, 3), (3, 3), (4, 3), (3, 4)]. Repeat 2 times.

So we can see there's a lot of potential recompute in normal recursion.
- Storage - we need both i-1 and j-1. So a n<sup>2</sup> matrix is needed for sure.
- Recursion - can we get rid of it, if we look closely in a reverse way, smaller values can be used to generate larger, ones, and they are adjacent. So we can linearize the order. So, don't need recursion.

O(n<sup>2</sup>), O(n) time and space.

Note:
- Q: Why do we start from the right?
	- A: Well, it doesn't matter, we can start from the left too. Starting from the right has the advantage that the recursion params decrease (length decreases), which is familiar. Going left to right, we need to track indexes which increase, and are less familiar.
- Q: Why do we start from an end instead of considering a window i-to-j?
	- A: Suppose a window is more interesting, but we still would need to consider both (remaining) sides right? We'd need to either add on both, or the window itself has changes, causing matches on the sides. In any case: for the sides, either we blindly add, or we get matches - both cases can still happen had we started from an end. And we're considering all ops anyway. So we choose to start from an end since it's simpler without loss of generality.
- Q: Why settling prefixes (i.e. an end) is better than ignoring it (i.e. consider a between window first).
	- A: Suppose we don't settle a prefix, and handle a window in it. In the end, we would still need to process the ignored path - in the best case the window matches, and we do additions on the ignored part. But this possibility is already covered if we do all additions for the prefixes. And we're considering all edit ops, so this is already taken into account. We can simply focus on the prefixes, and addition op will automatically take care of windows.
- Q: Why don't we actually edit the string for the 3 ops? 
	- A: We do ops delete, insert and substitute to match the elements. And therefore the two elements in question are already settled. So the change isn't relevant to upcoming candidates. Another possible question is, why don't we just do the ops in a non matching way? There's no point to senseless adding, since it'll surely increase the cost. Senseless deletion will also increase the cost (one of the string remains the same length that could have matched) for sure. Senseless substitution will also just increase the cost (length wont change, we are solving the same problem again). so it doesn't make sense to do ops unless they help with matching. 
- The window questions above are automatically solved since any insertion op automatically creates a window (i.e. our prefix is not same as original string after insertion).
- Noting parent - we keep a `parent` field in each cell of the dp matrix. We also update it if the cell if needed.

## Stubs of edit distance
Stubs of edit-distance:
- Table initialization - 
- Penalty costs - 
- Goal cell identification - 
- Traceback actions


## Reusing edit-distance to solve other problems
The stubs for edit-distance when modified can solve many problems (they happen to be special cases of edit-distance):
- Substring matching - finding a misspelt word in a long paragraph (the goal is somewhere in the middle)
- Longest common subsequence - Perhaps we are interested in finding the longest scattered string of characters included within both strings, without changing their relative order.
- Maximum monotone subsequence - The maximum monotone subsequence problem seeks to delete the fewest number of elements from an input string S to leave a monotonically increasing subsequence. A maximum monotone subsequence of 243517698 is 23568.
