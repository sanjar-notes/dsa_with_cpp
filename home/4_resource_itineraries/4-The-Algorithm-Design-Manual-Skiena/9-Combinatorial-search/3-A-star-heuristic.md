---
tags:
  - backtracking
  - A-star
---
# 3. A star heuristic
Created Sat Aug 3, 2024 at 11:44 PM

A\* is an elaboration of the Best-First search algorithm. works for positively edged problems only.

## Context
Best-First search considers only one value (start-to-node in our example) node-to-end heuristic value. This can lead to bad candidates being chosen (since they look like good candidates).


## Algorithm
So Best-First search chose the best candidate at the time (the cost in the previous example was start-to-node distance, but it can be heuristic and/or node-to-end too).

But one issue with Best-First search is that it chose based on current distance, and not future possible distance. The A-star algorithm considers both start-to-node and node-to-end distances.

It does so by introducing a hard lower bound, i.e. assuming the least possible value for node-to-end (i.e. edges left \* min_edge_weight). IT tries to pick candidates from PQ whose current length is least (PQ) and remaining length is within chosen bound, i.e. there are two criteria instead of one.
- If none of the current top solutions fit this hard bound, the bound is increased (actually we have been measuring least candidate in current poll, so we set that), and repeat the process.

## Clarification about PQ value
- In the example above (and Best-First search previously), problem was TSP, otherwise remaining length is a fixed number (not dependent on edges remaining since problem may not be a graph), in such cases the PQ value is a simple sum of start-to-node + node-to-end.

## Application - A\* vs Dijkstra
A\* proves useful in many A to B path finding algorithms.

For example, Dijkstra grows a single tree (in all directions). When the graph describes a road network on the surface of the earth, this known region should expand like a growing disk around s. But that means that half the growth is in a direction away from t, thus moving farther from the goal ("i.e. moving slowly").

Since A\* uses both Best-First-search and an deliberately strong bound, it moves in "as-the-crow-flies" direction from A to B, which is quicker than Dijkstra.