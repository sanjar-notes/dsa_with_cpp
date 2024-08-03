# 3. A start heuristic
Created Sat Aug 3, 2024 at 11:44 PM

A\* works for positively edged problems only. Its an elaboration of the Best-First search algorithm.md 

## Context
cost proprotional to length causes bad solutions to be considered before.


## A\* heuristic
TBD - from tablet


## Application - A\* vs Dijkstra
A\* proves useful in many A to B path finding algorithms.

For example, Dijkstra grows a single tree (in all directions). When the graph describes a road network on the surface of the earth, this known region should expand like a growing disk around s. But that means that half the growth is in a direction away from t, thus moving farther from the goal ("i.e. moving slowly").

Since A\* uses both Best-First-search and an deliberately strong bound, it moves in "as-the-crow-flies" direction from A to B, which is quicker than Dijkstra.