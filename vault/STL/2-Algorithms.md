# 2. Algorithms
Created Sun May 12, 2024 at 7:35 PM

![](../../assets/2-Algorithms-image-1-388ac0a2.png)

## Linear search
`find` is a function (not method) that can be used on any container. 
*BUT, we'll avoid giving this too much precedence since most container have a method named find (method, not function), that's much faster.* *Less confusion.*
```cpp
vector<int> v;
auto it = find(v.begin(), v.end(), 20);
```

## Binary search
### Existence
```cpp
binary_search(startIt, endIt, key); // existence check
// e.g 10 10 10 20 20 20 30 30
// key=20 => true
// key=21 => false
```
### Lower bound (left side = || >)
```cpp
// Lower bound means "left side" (<=)
lower_bound (startIt, endIt, key);
lower_bound(v.begin(), v.end, 20); // v is a vector

// e.g 10 10 10 20 20 20 30 30, key=20
// Result  is ..., 10, ^20
```
### Upper bound (right side >)
```cpp
// upper bound means "right side" (>)
upper_bound (startIt, endIt, key);
upper_bound(v.begin(), v.end, 20); // v is a vector

// e.g 10 10 10 20 20 20 30 30, key=20
// Result  is ..., 20, ^30, ...
```

### Range (range from left to right side)
Get "equivalent" range.
```cpp
// left side >=, right side >
equal_range(startIt, endIt, key);

// e.g 10 10 10 20 20 20 30 30, key=20
// range is [20, 20, 20, 30]
```
## Sorting
## sort (non stable)
`std::sort` works for any container (except strict ADTs like stack, queue, or already sorted ones)
```cpp
sort(startI, endI) // natural sort, i.e. increasing order, alphabetical order
	sort(startI, endI, greater<int>()) // decreasing order. 
	// Remember: greater is a call here, min PriorityQueue declaration is not a call.
	
	sort(starI, endI, [] -> bool (auto a, auto b){ return is_should_swap; }); // custom
```

## stable_sort
```cpp
stable_sort(startIt, endIt);
	stable_sort(startIt, endIt, greater<int>()); // decreasing order
	stable_sort(starI, endI, [] -> bool (auto a, auto b){ return is_should_swap; }); // custom
```

## Check if sorted
```cpp
is_sorted(startIt, endIt);

vector<int> v;
bool isSorted = is_sorted(v.begin(), v.end());
```

## Permutations and combinations
TBD