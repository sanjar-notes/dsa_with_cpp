# 2. Check bipartite
Created Tue Jul 16, 2024 at 12:02 PM

## What's a bipartite graph
A graph that can be divided into two groups such that edges connect only the groups among each other and not within themselves.

![](../../../../../../assets/2-Check-bipartite-image-1-1a642cda.png)
## Observation
Observe that if 2-coloring is attempted on a bipartite graph (i.e. all neighbors of a node are of different color), then it be possible. For a non bipartite graph it won't be possible.

We can augment breadth-first search so that whenever we discover a new vertex, we color it the opposite of its parent. We check whether any non-tree edge links two vertices of the same color. Such a conflict means that the graph cannot be two-colored. If the process terminates without conflicts, we have constructed a proper two-coloring.

## Implementation
Q: Coloring is OK. But should checking be done during the traversal (aka coloring) phase, or separately?
A: No. A single phase run should do. Proof: since BFS trav is a tree and only 2 kinds of edges exist - forward edges (discover new nodes) will always be Ok (since they do the coloring). Conflict detection happens using the back-edges (already visited) only.

https://leetcode.com/problems/is-graph-bipartite