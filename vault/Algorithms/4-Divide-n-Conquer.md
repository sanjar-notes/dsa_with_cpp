# 4. Divide n Conquer
Created Sat May 18, 2024 at 1:31 PM

[Wikipedia](https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm)
## Steps
- Divide and conquer involves 3 steps:
  1. Divide (express it into smaller problems of the same type)
  2. Conquer (solve the instances)
  3. Combine (combine the solutions to form the complete solution)

## Notable info
### Decrease-and-conquer method (related)
In some problems, its possible to make the input smaller (i.e. without splitting into multiple inputs), after doing some (efficient) compute in each step. Since we don't have multiple inputs, there is no combine step. Code may be purely iterative (tail recursive) here.

Examples:
- Euclid's algorithm for GCD
- Binary search

### Parallelism
Since each input is solved in isolation, it's possible to employ multiple processors to make the work happen faster.

### Relation to recursion
Since subproblems are of the same type as the parent, recursion is the natural choice for programming.

### Relation to DP
For some problems, the branched recursion may end up evaluating the same sub-problem many times over. This can be made efficient by storing the subproblems (an encoding scheme on input may be needed), and reusing them, aka memoization.

Followed to the limit, it leads to "bottom-up divide-and-conquer" algorithms such as dynamic programming.