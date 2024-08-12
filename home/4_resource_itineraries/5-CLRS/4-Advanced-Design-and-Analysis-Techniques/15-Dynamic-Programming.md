[See Skiena](../../4-The-Algorithm-Design-Manual-Skiena/10-Dynamic-Programming/index.md)

## Elements of DP
Problems solvable by DP have two characteristics:
1. Optimal substructure - optimal solutions to a problem incorporate optimal solutions to related subproblems, which we may solve Independently.
2. Overlapping subproblems - two different problems share some common subproblems (i.e. params are identical). This is where storage helps.

Note:
- It may seem strange that dynamic programming relies on subproblems being both independent and overlapping. Although these requirements may sound contradictory, they describe two different notions, rather than two points on the same axis. Two subproblems of the same problem are independent if they do not share resources. Two subproblems are overlapping if they are really the same subproblem that occurs as a subproblem of different problems. *i.e. siblings are independent, cousins may overlap*.

## DnC vs DP
To compare them, think of a problem being solved recursively, and a total of n subproblems are generated. The number of generated subproblems are the same in both solution approaches, DnC and DP.

The difference is that all subproblems in the DnC case are distinct. But in the DP case some are the exact same, so memoization is possible.


## DP problems list
- Rod cutting: given a long rod and a length-based price list. How to cut the rod?
- Edit distance
- Longest common subsequence
- Optimal binary tree - i.e. need to optimize a session searches, instead of each search. Probability of searches is known.
-  Longest simple path (no cycle) in a DAG
- Longest palindrome subsequence
- Bitonic euclidean TSP (traveling-salesman problem)
- Printing text neatly (no continuation hyphens)
- Viterbi algorithm - DP on graph for voice recognition
- Image compression by seam carving
- Breaking a string maximize cost. Break a string into give pieces (sum pieces = length). Breaking into two parts (break anywhere) is O(current_size).
- Planning an investment strategy