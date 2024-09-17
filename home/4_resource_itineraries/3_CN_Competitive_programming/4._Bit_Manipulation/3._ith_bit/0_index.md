---
tags:
  - bitman
---
# 3. ith bit
Created Monday 29 June 2020

1. **Return** ith bit.
A simple way to do this would be
```cpp
N = 100010101 // suppose we need 2nd bit - zero based counting
```
Approach 1 - Shift+Modulus:

1. Shift by k to the right
2. Check last bit
```cpp
return (n >> i)%2; // Booth's algorithm - O(n)
```
Approach 2 - Shift and AND:
We can produce pow(2, i) using the left shift operator
```cpp
return (n >> i) & 1; // returns 1 if set and 0 if unset
```
---
## Bit Ops
1. Get ith bit - `(n & (1 << i)) != 0`
2. Set ith bit - `(n | (1 << i)`
3. Unset/clear - `(n & ~(1 << i))`
4. Update bit - `value ? set : unset`
