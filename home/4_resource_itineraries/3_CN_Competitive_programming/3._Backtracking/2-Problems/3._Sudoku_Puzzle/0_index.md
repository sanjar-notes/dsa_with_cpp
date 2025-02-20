---
tags:
  - backtracking
---
# 3. Sudoku Puzzle
Created Friday 26 June 2020

Given:

- A 9x9 sudoku, with the well known rules.
- Has only one solution.

---

- It is a typical backtracking problem.
- Store the missing numbers in a pair vector. This is better than reiterating on the list. Do it while taking the input.
- We first produced a locally possible list, after checking the rows, columns and the 3x3 cell. **This is better than checking for all 1 to 9**, space vs time tradeoff. We just have to maintain a 1 to 9 boolean array, used as a map.
- In this approach a config is wrong **iff** the local possible list is empty.
- Used bool for the sudoku function. The reason is simple, we should return true and end the solution, as there's only one solution. There's only one **positive **base case.
- **This **algorithm's running time is independent of the difficulty of the sudoku problem, assuming a single solution exists.
- Time complexity depends only on the number of missing values.

Parikh's solution:
![](../../../../../../assets/0_index-image-1-801e2dae.png)s

---

**Jargon - Only used in case of Backtracking**

1. Positive Base case: Indicates that the intended task is successfully completed. e.g a successful config for N-queens, sudoku
2. Negative Base case: Indicates that the task is stuck, won't be able to proceed further. e.g An n-queens config which is in the middle of completing a config but a queen is impossible to place.

Note:

1. There may be multiple postive and negative base cases.
2. Number of times positives base case evoked = number of successful configs(if known/given before hand). All other are negative ones.
