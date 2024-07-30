# 5. Data parallelism
Created Tue Jul 30, 2024 at 12:15 AM

## Why parallel algorithms
There are situations when runtime speed is needed, if not complete speed;
- Animations and games
- Search engine results

Here breaking down a problem so it can be solved by multiple computers/processors and combining the outputs is essential.


## Principle of parallel algorithms
We distribute the problem into parts, solve them and recombine. Each step has a cost. If the sum this is lower than sequential algorithm, significantly, then use parallel algorithms.


## Data parallelism (heterogeneous speedup)
Suppose a task involves working on independent aspects, then parallelism is a good fit here because:
- No need of managing communication between parts of the program
- Guaranteed speedup

Note: this kind of parallelism differs from the more involved algorithms where parts of the program communicate and synchronize to build the output.


## Pitfalls of parallelism
- Embarrassingly parallel problems - problems that can be trivially solved using parallelism. *These are thought of as uninteresting, but they work fine.*
- Hard to parallelize problems - suppose a problem involved looking at all pairs of a data. Here a parallel algorithm would not be good since not all pairs can be on the same processor. So parallelism shouldn't be considered here.

<br />

- Naive parallelism - sometimes an algorithm/problem may be parallelizable. But it could be that the sequential algorithm can be on par or even better than the parallel algo. E.g. minmax game-tree search. This can be parallelized easily (one branch one processor), but its better to alpha-beta pruning, which is almost on par with sequential. *Try to better the sequential algorithm before assuming parallelization is always better*.
- Cost - even if adding cores increases speedup, cores aren't inexpensive.
- Tooling is bad - Performance-tuning tools such as profilers are better developed for sequential machines/programs than for parallel models.
- Tough to debug - since parallel algorithms have a component of communication that needs to be managed by the programmer, multiple runs with the same input could lead to different executions.