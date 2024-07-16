# 3. Cycle detection
Created Tue Jul 16, 2024 at 5:47 PM

## Undirected graphs - DFS
Back edges are the key to finding a cycle in an undirected graph. Cycle detection is based on watching the back edges of DFS. So the forward edge and back-edge-but-parent is benign, but back-edge-not-parent is a cycle. We are just looking for this to happen.

For directed graphs, simple DFS is not enough since there may be a node that has no out degree but multiple in-degrees, and since visited keeps just a boolean we can't know whether this cycle forming node has no out degree or not. Simplest example is a cyclic triangle with one edge reversed. Its cyclic by normal DFS but not really cyclic (directed).

## Directed graphs