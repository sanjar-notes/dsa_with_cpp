---
tags:
  - dsa-model
---
# 7. Logarithms and their applications
Created Tue May 7, 2024 at 10:55 AM

## Logarithms and Binary search
Binary search is one of the most powerful ideas in algorithm design.
Its time complexity is logn

## Logarithms and Trees
For a binary tree with n leaves, h = log<sub>2</sub>n
For a d-ary (each node has d children) tree with n leaves, h = log<sub>d</sub> (n)

The punch line with trees is that short trees can have very many leaves, which is the main reason why binary trees prove fundamental to the design of fast data structures. Note: by fast ig he means guided-quick-jump.

## Logarithms and Bits
Given size w, total number of bit patterns possible are 2<sup>w</sup>

## Fast exponentiation
Suppose that we need to exactly compute the value of a<sup>n</sup> for some reasonably large n.

The simplest algorithm would take `n` steps, doing serial multiplication.

But, the problem can be expressed in a better way. If n is even, we can write the product as a<sup>n/2</sup> squared (so one multiplication). And we can repeat the same for this number. If n is odd, we need to do an extra multiplication, and then we can reuse the pattern.

So T(n) = T(n/2) + 1, i.e. T(n) = O(log n). So we can fast multiply in logarithm time instead of linear time, assuming the RAM model of computation.

## Logarithms and Summations
Harmonic series sum is log(n), for n terms.

The Harmonic numbers prove important, because they usually explain “where
the log comes from” when one magically pops out from algebraic manipulation.

The Harmonic numbers prove important, because they usually explain “where
the log comes from” when one magically pops out from algebraic manipulation. For example, thekey to analyzing the average-case complexity of quicksort is such a summation.