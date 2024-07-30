# 5. Divide and Conquer
Created Mon Jul 29, 2024 at 9:39 PM

## Breaking down problems
Two important algorithm design paradigms are based on breaking problems down into smaller problems. 
- Dynamic programming - typically removes one element from the problem, solves the smaller problem, and then adds back the element to the solution of this smaller problem in the proper way.
- Divide and conquer (DnC) - instead splits the problem into (say) halves, solves each half, then stitches the pieces back together to form a full solution.


## When is DnC useful?
*Whenever the merging takes less time than solving the two subproblems, we
get an efficient algorithm.* 

Merge sort is an example, since merging is linear while sorting two halves has a log factor.


## Info about DnC
- DnC is used in many important algorithms like mergesort, fast fourier transform and Strassen's matrix multiplication.
- Beyond binary search and its variants, it becomes difficult to apply DnC.
- Ability to use DnC depends on solving recurrence relations.
- Combining efficiently is important too, not just solving the subproblems. The efficiency of conquering (aka combining) determines if DnC will be useful or not. Conquering should take less time.