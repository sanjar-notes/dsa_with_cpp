# 1. AVL trees
Created Wednesday 12 February 2020

#### Intro
* AVL stands for Adelson-Velsky Landis (named after its inventors **A**delson-**V**elsky and **L**andis)
* An AVL tree is a self-balancing binary search tree.
* Invention of AVL tree was published in the **1962** paper "*An algorithm for the organization of information*" in Russia.

#### Why AVL trees
* They support all the usual operations - addition, deletion and searching  in O(log n) time.
* Additionally, Two trees can be merged in O(log(m+n)) time.
* Space taken - θ(n)
* Height is always ~log(n). To be precise it is between log(n) and 1.45*log(n)

#### What is 'balance'
* Each node stores an extra number in the range -2 to 2, inclusive.
* This number is called the balance factor. b = |left_subtree_height - right_subtree_height|

#### What is 'imbalance'
If atleast one node with a balance factor of 2 or -2 exists, then the tree is said to 'not balanced'.

#### How to re-balance
* During deletion/insertion, a leaf node is added or removed. Traverse up from there and change the balance factor for the parents.
* The first node where balance factor is unacceptable is called the pivot.
* Do a rebalancing on this pivot.

#### Insertion
* Insert like BST
* Rebalance if required

#### Deletion
* Remove like BST
* Rebalance if required

Important facts about rebalancing:
* One rebalance(i.e with one pivot) is always enough. Reason: Height of a tree after rebalancing(on insertion) = Height of the original tree. And as the other subtree of the pivot was comparable, it will remain so after the rebalancing operation. Works for deletion too.
* At most 3 nodes are changed in a rebalance operation.
* Both insert/delete use the same balancing algorithm.

[Reference](https://skerritt.blog/avl/)

#### Proof of AVL operations
**Note**
* There are 4 cases which describe all possible cases of an AVL tree insertion.
* The parameters T1, T2, T3, T4 may be ε, leaf or a tree themselves.
* The 4 operations are called **rotations** and they are very simple to tell, just by observation.

**To prove** - After being unbalanced, we can rebalance the tree and still retain being BST.
Situation: we start traversing the tree during insertion/deletion, we do the op (i.e. delete/add node) at the proper place, then recursion back steps start. During these back steps we check the "delta" at each node.

Mem aid: 
- the double circle represents the first point of imbalance (i.e. nearest to node that is deleted/added), all points moving will obviously be unbalanced. i.e. balancing takes place at the first point of imbalance (which can be known in the recursion-back-step of the insert/delete operation).
- The variation, i.e. LL, LR, RL or RR can be known during the recursion-back-step, just keep track of last two back steps.
- To easily assure equivalence after rebalancing, just check if range for all nodes is valid or not. It is valid.
- I've omitted unaffected branches here. To check just make sticks and see if they still hold in after balancing.
- To help avoid ambiguous moves, label the nodes as 10, 20, 30. In all cases, and you'll see that only a unique move is possible in every case.

![](../../../../../../../../assets/0_index-image-1-af7e3102.svg)