# 2. Union Find structure
Created Monday 20 April 2020

## Context
A "set partition" parcels out the elements of some universal set (say the integers 1 to n) into a collection of disjoint subsets, where each element is in exactly one subset.

Set partitions naturally arise in graph problems such as connected components (each vertex is in exactly one connected component) and vertex coloring (a vertex may be white or black in a bipartite graph, but not both or neither).

The union find data structure is a way to represent and work with these subsets.
Union find structure is also called DSU (disjoint set union).

## Approach
Initially, all objects exist in isolation. There are two operations:
- is same component ?aka `find (a, b)`  returns true if they are in the same set.
- `union (a, b)` - attach sets containing a and b to form a single set. i.e. merge two connected components together

## Efficiency
- Naively, both ops take O(log(N)) and O(N), time and space, where N is the total number of nodes/objects.
- If the path compression optimization is used, ops take α(n) time and O(N) space. Practically this is constant time. The alpha function is called 'inverse ackermann function' and it grows very slowly.

Note:
- Why log(n)? Suppose we have N nodes, and we start combining them such that we combine a smaller tree onto a larger. how big of a tree could we make. Ans: observe that height increases if you combine two trees of the same height (since in UnionFind the attaching is at root), otherwise the height stays the same. To maximize height, we'll need to make trees of the same sort, and the maximum you can make using N is height log(N) + 1 trees (just do the math). So O(log(N)).
- Why α(n) ? If observed carefully, the parent doesn't matter to node if they're connected to the root, so one can update all nodes parent except the root to be the root (there would be no need for traversal). This is done in a incremental and query bound way instead of "at query time itself". This combined with "direct root attachment" leads to a "weird" (i.e. to me) function that grows slowly. This happens to be the inverse Ackermann function.

## Implementation
All we need is an array (of size n) that stores the parent and rank (height) of a component. Or u can use two different arrays.

Initially, since all are isolated, all parent values are self, and rank is 1. After that suppose there were some find and union calls. We implement three functions:
1. getRoot(node) - this does a repeated lookup to get current node's root.
2. find(a, b) - we get roots of both are compare them. If same, this returns true (i.e. both nodes are in the same connected component).
3. union(a, b) - we get roots of both. Then check height (i.e. rank) and attach the smaller to the larger. The op is only done on roots. i.e. smaller root's parent is set to larger root, and larger root rank increases by one (if rank is same).

Note:
- N isn't needed in code - it can be observed that N (as a variable) is not needed in the code, since everything is a lookup, simple variable set or addition by 1. This is weird.
- If an insert operation happens its fine, since new nodes are isolated.

## Code
[Problem](https://www.geeksforgeeks.org/problems/union-find)
```cpp
// Observation: there's no need for knowing number of vertex (n) here, since UnionFind starts as forest
class Solution
{
    public:
    //Function to merge two nodes a and b.
    void union_(int a, int b, int par[], int rank[]) 
    {
        int rootA = rootOf(a, par, rank);
        int rootB = rootOf(b, par, rank);
        
        int bgNode = rank[rootA] > rank[rootB] ? rootA : rootB;
        int smNode = bgNode == rootA ? rootB : rootA;
        
        // no need to update nodes of of smaller tree, just update the root
        // all updates happen at the root
        par[smNode] = bgNode;
        rank[bgNode] += 1;
    }
    
    // helper
    int rootOf(int a, int par[], int rank[]) {
        int root = a;
        while(par[root] != root)
            root = par[root];
        return root;
    }
    
    //Function to check whether 2 nodes are connected or not.
    bool isConnected(int x, int y, int par[], int rank[])
    {
        return rootOf(x, par, rank) == rootOf(y, par, rank);
    }
};
```

## Usage
- Cycle detection in graphs
- Kruskal's algorithm for MST generation


- Its a very fast (almost O(1)) structure to work with disjoint sets or multiple connected components.
- UnionFind is not available in STL. But [Boost](https://stackoverflow.com/a/43561791/11392807) has it.

## General usage
- Online Social Networks: Manages friend groups or user connections dynamically.
- Network connectivity, check if nodes are connected.
- Image processing - for clustering
- Equivalence Classes: Manages sets of equivalent items, useful in language processing or computational biology.