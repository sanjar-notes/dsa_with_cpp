# 1. BackTracking
Created Monday 22 June 2020

## Lecture
- Backtracking is an approach where we explore all possible paths efficiently.

e.g There are 10 bags with some items.
Print the name on the bag if a ball exists in the bag.

- Backtracking is a kind of thinking(approach), not an algorithm.
- Backtracking and recursion are different. Backtracking is an approach and recursion is the algorithm used to solve the problem.
- Backtracking is implemented using recursion.

## Common backtracking problems
The common thing in all backtracking problems is the "decision you make".
1. Subset generation - to include given element or not, at the moment.
2. Permutation gen - "which element" to choose, at the moment.

Another thing in backtracking is the order of output - so if the answer needs to be in sorted order, we must use recursion instead of bitwise-gen (suppose problem is subset gen), since recursion maintains sorted order by default.

Note:
- Usually, we want to traverse over all possible solutions, instead of storing them. This may mean keeping a max size array (i.e. max candidate size) and doing operations on it as we traverse through the solution
- Backtracking means enumeration, but it should be efficient - we should backtrack as soon as we know forward solutions in the current path are doomed to fail, or have already been seen. i.e. *early backtrack and avoid duplicate is important in backtracking*.