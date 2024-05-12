# 2. Algorithms
Created Sun May 12, 2024 at 7:35 PM

![](../../assets/Pasted%20image%2020240512193624.png)
## sort
`std::sort` works for any container (except strict ADTs like stack, queue, or already sorted ones)
```c++
sort(startI, endI) // natural sort, i.e. increasing order, alphabetical order
sort(startI, endI, greater<int>()) // decreasing order. 
	// Remember: greater is a call here, min PriorityQueue declaration is not a call.

sort(starI, endI, [] -> bool (auto a, auto b){ return is_should_swap; })
```


## Permutations and combinations
TBD
