# 4. Articulation vertex
Created Tue Jul 16, 2024 at 11:20 PM

## Naive
For each node, delete it, and do a DFS/BFS to check if the graph remains connected. If it is not connected at some point, then it has an articulation point.

Time: O(V \* (V + E))

## Linear
