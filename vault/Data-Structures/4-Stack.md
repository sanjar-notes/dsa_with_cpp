# 4. Stack
Created Wed Jun 19, 2024 at 11:18 PM

## API
See [1-Containers](../STL/1-Containers.md#List)

## Conceptual use
- Recall stuff in order
- Used internally in recursion
- Store disjoint streaks of a problem efficiently - i.e. accumulate to-do (as opposed to done) parts of a problem without needing a all-loop.
	- [Monotonic stack pattern is uses this nature of stack.](https://leetcode.com/problems/daily-temperatures/submissions/1429625941/)

## Practical use
 - For undo operations in text editors
 - For back button in browser navigation
 - Very efficient, e.g. for batch jobs