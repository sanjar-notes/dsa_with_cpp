# 2. Searching
Created Sunday 03 May 2020

1. For sorted arrays, do **binary_search**(begin_it, end_it, key) - returns true if found, else false.
2. Find the index of the key, we use **lower_bound**(arr, arr+l, key) - returns the iterator if found. Iterator is arr.end() if not found. **Search from left side.**
   1. For finding the index as integer, do `lower_bound() - arr.begin()`
   2. `lower_bound` - first element that is greater or equal.
      1. If key > maximum, then .end() is returned.
      2. If key exists, iterator to first occurrence of is returned.
   3. `higher_bound` returns the iterator to an element > key.
      1. If key is the last, returns `.end()`

Note: The names are correct and to the point.
![](/assets/2._Searching-image-1.png)

3. **equal_range(**begin_it, end_it, key**) **returns a pair of iterators to the first and the last item equal to the key. This can be used to get the number of repeated key values. **It is used for getting the first iterator to a key(even if there's just one key)**

```cpp
vector<int> A;
int key;
equal_range(A.begin(), A.end(), key).first; // iterator to first instance of key
```

4. For **linear search** - use **find(**begin_it, end_it, key**)** - returns the iterator to the first instance.

- Use a lambda comparator for decreasing values.
