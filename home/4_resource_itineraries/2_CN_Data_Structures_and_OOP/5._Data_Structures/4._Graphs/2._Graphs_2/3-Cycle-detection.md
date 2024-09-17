---
tags:
  - graphs
  - cycles
---
# 3. Cycle detection
Created Tue Jul 16, 2024 at 5:47 PM

## Undirected graphs - DFS
Back edges are the key to finding a cycle in an undirected graph. Cycle detection is based on watching the back edges of DFS. So the forward edge and back-edge-but-parent is benign, but back-edge-not-parent is a cycle. We are just looking for this to happen.

Note:
- If specified, would need to check for self cycles too.

## Directed graphs - DFS with extra array
Cycle detect using DFS on a undirected graph just checks if it encounters an already visited node (not a parent). But it will incorrectly detect a cycle for the below directed graph as well, at node '2'.
![](../../../../../../assets/3-Cycle-detection-image-1-1a642cda.png)

The realization here is that not only do we need to encounter a visited node, but it must be in the same path as the current path (i.e. same direction). In the above picture, 0 -> 3 -> 4 -> 2 is one path and 0 -> 1 -> 2 is another, so its not really a cycle. It needs to be a full circle. *i.e. We need to mark the current trail.*

Implementation wise, we can just keep an extra array called pathVisited. We will populate the visited array as usual, but for pathVisited we will mark a node as 1 when we start processing the node, and mark it as 0 when we are done processing. This means the descendants will always see their ancestors in the same path as 1, but when the subtree changes, the other subtrees pathVisited would have become 0. If we find pathVisited and visited both to be 1, that means we found a proper cycle.

Note: 
- parent check is not needed for undirected graphs, as cycle with a parent is possible (2 edges going either ways from node to parent).
- If specified, would need to check for self cycles too.

## Code
[Problem](https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1)

```cpp
class Solution {
  public:
    // Function to detect cycle in a directed graph.
    // returns true if find a cycle
    // DFS
    bool helper(int start, int V, vector<int> adj[], vector<int>& vis, int parent) {
        vis[start] = 2; // add self to trail

        bool isCycle = false;
        for(auto nbr: adj[start]) {
            // if(nbr == parent) continue; // false cycle.
            // WRONG, parent means a valid cycle node
            // ... in directed (nodes have both ways connection)

            if (vis[nbr] == 2 || nbr == start || (!vis[nbr] && helper(nbr, V, adj, vis, start))) {
                // true cycle and on same path
                // self cycle
                // new node discover
                isCycle = true;
                break;
            }
        }

        vis[start] = 1; // leave trail, but remain visited

        return isCycle;
    }
    bool isCyclic(int V, vector<int> adj[]) {
        // can be unconnected, so check all graphs (whole forest)
        vector<int> vis (V, 0);
        for(int i = 0; i < V; i++) {
            if(!vis[i] && helper(i, V, adj, vis, -1)) return true;
        }

        return false;
    }
};
```

Minor optimization: instead of two arrays, use a single visited arrays whose values are 0 (undiscovered), 1 (node visited, not in current path) and 2 (node visited and in current path).