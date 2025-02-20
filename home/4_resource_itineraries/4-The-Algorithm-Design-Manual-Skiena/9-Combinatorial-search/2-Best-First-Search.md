---
tags:
  - backtracking
  - best-first-search
---
# 2. Best First Search
Created Sat Aug 3, 2024 at 9:57 PM

Best-First Search is elaboration of backtracking.

## Context
In backtracking, two important decisions are "which free solution position to expand next" and "order of considering candidates for current solution position".

The second one is quite important, i.e. order of candidates, especially for optimization  problems (say min finding), since we not only want to get the lowest, we want to get it fast (i.e. before instead of later during the backtrack).

Backtracking didnt care about order of candidates since it was about enumeration/existence-finding (i.e. we look for one or all solutions). Optimization problems seek a solution that has the lowest (or highest) value of some objective function.

## Best-First Search (aka branch-and-bound)
As said, order of candidates is important for optimization problems. When we consider order in backtracking, the algorithm is called "Best-First search" - more jargon ;)

Here we assign a cost to every partial solution and store it in a "global" priority queue (min). At any moment, only the one with least cost is expanded. i.e. in a way we automatically ignore the current search if its cost increased (but was low earlier).

Two things here:
- Implementation detail - We shouldn't pop off any solution from the priority queue, since a currently less cost solution may increase its cost later, and we may need to resume a previous (in queue) path. *Of course, this doesn't mean we are guaranteed to consider all. It may be that we somehow always get a lower cost solution without needing to resume the largest solutions so far - i.e. our area of considerations remains fairly at the top of the queue*. IOW, candidate generation may be a local thing, but candidate picking is a global one (you still insert the local).
- Implementation detail - when do we stop? If all solutions have been generated, and queue top is greater than cost_found_until_now, then we can stop. *This is the meat of Best-First search it is able to disregard solutions at the end of its run - that other algorithms would have considered*.

Note:
- Jargon - Optimization function - in, Best-First search, the optimization function should happen to be a lower bound of the answer, i.e. all forward movements must add to the current path's cost, i.e. there are no negative edges in a way (graph terminology). Otherwise we would need to consider the queue (even if we have considered all lower ones already, since a negative edge in a high cost path may decrease overall cost too much). *Just a note, this just talks about jargon of Best-First search, if there are negative edges, then a full blown backtracking has to take place, it won't be called Best-First search anymore*.
- Space: Best-first search is sort of like breadth-first search. A disadvantage of BFS over DFS is the space required. A backtracking/DFS tree uses memory proportional to the height of the tree, but a best-first/BFS tree requires maintaining all partial solutions, more akin to the width of the tree.
- Usual cost function - the output of a heuristic function for (node-to-end) is usually used to inform Best-First search, unlike Skiena's example here (he's using known start-to-end as cost).

*Skiena doesn't say how to implement this*.


## maid
Best-First search is backtracking that advances the best partial solution so far, at every point.