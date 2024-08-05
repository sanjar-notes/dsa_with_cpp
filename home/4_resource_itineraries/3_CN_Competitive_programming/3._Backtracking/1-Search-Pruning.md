# 1. Search Pruning
Created Sat Aug 3, 2024 at 8:26 PM

## Search pruning
Pruning is the technique of abandoning a search direction the instant we can establish that a given partial solution cannot be extended into a full solution.

Usually pruning solves problems like:
1. Consider the same solution once. i.e. duplicates solutions are not handled. Fix: check if the current situation is symmetrical/equivalent to a past one.
2. Go to a final solution that's wrong. i.e. there's no early detect. Fix: check if some limit is exceeded, and there's no point moving forward.

Pruning usually works for small optimization problems, size 20-100.

## Sudoku example
When solving sudoku by backtracking, we have a choice - "which free cell to try next", this includes choosing initial cell, of course.

1. Which free cell next? One way is to choose in grid order (top-down left-right). Another way is to choose a free cell that has the least number of candidates. The second way is better because reduces candidates for other free cells (they would be higher if we chose them first instead of this "least" cell). *This is significant since each candidate of a cell starts a whole new search*.
2. Which candidate first (in current cell)? one way is to loop in order (1-9) that are not in row, column and sector, aka *look-count*. Another way is to try to sort/filter which candidate to go first/ignore, aka *look-ahead*. Lets do the filter first - can we identify candidates that are doomed to fail? *Actually the most-constrained-cell in point 1 automatically optimized this choice*.

This is the power of search pruning. Even simple pruning strategies can suffice to reduce running times from *impossible to instantaneous*.


## Importance of pruning
Consider a famous question of whether 8 pieces of chess (from the same team) - 1 king, 1 queen, 2 bishop, 2 rook and 2 knight, can be placed on the board such that all remaining positions are threatened. A piece doesn't threaten another, so ignore that.

Usual pruning, like choosing order and which position to select, didnt work here.

What worked was this - we defined a new problem, which is easier than the original, and solved that. There was a logical link between the easier and the original problem, that helped early detect bad boards. *We had to be novel in order to prune effectively*. Skiena 297-298.

## Take-Home Lesson
Clever pruning can make short work of surprisingly hard combinatorial search problems. Proper pruning will have a greater impact on search time than other factors like *data structures or programming language*.

Thought: The speedup is enormous since pruning attacks the search space itself.