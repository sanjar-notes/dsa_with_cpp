# 1. Equalize CodeForces
Created Tuesday 30 June 2020

<https://codeforces.com/problemset/problem/1037/C>

Approach 1 - Use only flips
We traverse the list and do the following:

1. If the elements are the same, do nothing.
2. If an element does not match, flip it.	

Cost: n worst case
Is this the fastest, don't seem to be:
e.g 0110 and 1001
Our cost = 4
If we flipped = 2

* Note swapping is to be used iff its cost is less than flip. A flip makes a character correct in cost 1. A swap makes two adjacent characters(which are wrong) in cost 1(which is better than doing 2 flips - 2).
* If we have two characters which are swappable and have are not adjacent, it is better to just use flipping.
* Conclusion: We do only adjacent swaps and flips.


*****

[equalize.cpp](1._Equalize_CodeForces/equalize.cpp)

