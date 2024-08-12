# 6. Limitations of DP TSP
Created Fri Aug 9, 2024 at 12:45 AM

## TSP
page 339

## When is Dynamic Programming Correct?
DP won't work if
- Recurrences don't mitigate direct cycles (in some way). Direct meaning not about subproblems, but just representing the problem itself.
- Not a DAG - There's no clear evaluation order (LR, or small-large). i.e. the subproblems if seen as a graph are not a DAG (there are cycles). i.e. the nature of the problem itself is so. DP wont work.
- Does not obey Principle of optimality: the value (scalar) of a partial solution matters, not its history. i.e. in edit distance we just had to save the costs, not the history of edits. If a problem requires the history for each partial solution, then DP won't work.

p340


## When is Dynamic Programming Efficient?
Two things decide efficiency of a DP solution:
1. Storage space. This is the major reason. If problems have a firm order (i.e. changing them would change the problem), then DP might work. But if elements of the problem can be reordered, then we get exponential solutions.
2. Time to evaluate one partial solution. Usually all predecessors is just fine. i for i.

Take-Home Lesson: *Without an inherent left-to-right ordering on the ob- jects, dynamic programming is usually doomed to require exponential space and time.*