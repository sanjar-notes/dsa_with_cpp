---
tags:
  - strings
  - kmp
  - old
---
# 2. KMP algorithm
Created Monday 27 July 2020

Knuth-Morris-Pratt algorithm
Does efficient pattern searching.
T.C O(m)+O(n)
How → It selects a prefix(from the pattern) and marks it's occurrences throughout the pattern, this way, we can start the search somewhere midway instead of the start. This also ensures that we don't have to backtrack in the original string. This way we can search out pattern in one pass.
![](../../../../../assets/0_index-image-1-81a2d2be.png)
Building the pi table:

```cpp
for(int i=0; i<l; i++)
{
	while(char at i!=char at j)
		j = arr[j -1];
	arr[i] = ++j;
}
```
