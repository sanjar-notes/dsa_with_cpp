# 1. Containers
Created Sun May 12, 2024 at 7:34 PM


## String
TBD
```c++
```

## Pair
USP: easiest instance of tuple
```c++
pair<int, int> p = {1, 3};
cout << p.first << p.second;
p.first = 23;

pair<int, int> f() { return {1, 2}; }
```

## Vector
USP: dynamic array, the de-facto for practical programming.
```c++
vector<int> v;
vector<int> v (10); // size 10, filled garbage
vector<int> v (10, 0); // size 10, filled with 0s
vector<int> v1 (v2); // create and copy values

v[2]; // read, write access
v.front(); // access first element
v.back(); // access last element

v.size(); // current filled length of vector
v.empty(); // is empty?

v.push_back(10); // insert at back, O(1) on average
v.pop_back(10); // remove last element, O(1) on average
// front operations are absent
v.insert(it, 5); // insert at given index O(n)
	// varidaic - not allowed
	v.insert(it, 2, 10); // insert 10, 10 at given index
	v.insert(it, startIt, endIt); // insert values from startIt, endIt
v.erase(iterator); // remove first instance from array, O(n)
	v.erase(startIt, endIt); // remove first instance from array, O(n)
v.clear(); // delete everything

// iterator
vector<int>::iterator it = v.begin(); // index 0, rightward
vector<int>::iterator it = v.end(); // index n, rightward

// find
find(stk.begin(), stk.end(), 30); // function not method

// looping
for(auto it = v.begin(); it != v.end(); it++) { cout << *it; }
for(auto a: v) { cout << a; }

// utils
v.sort();
v.reverse();
v.swap(v2); // symbol-data swap
v.resize(100); // make size equal to 100, discard elements if needed

// HOFs - need decltype, back_inserter
// // map - transform()
decltype(v) output (v.size());
tranform(v.begin(), v.end(), output.begin(), [](){ return 1; }); // new array
	tranform(v.begin(), v.end(), v.begin(), [](){ return 1; }); // in-place

// // Filter - copy_if()
decltype(v) output;
copy_if(v.begin(), v.end(), back_inserter(output), [](){ return 1; }); // new array
	 // in-place - resize, distance
	auto it = copy_if(v.begin(), v.end(), v.begin(), [](){ return 1; });
	v.resize(distance(v.begin(), it));

// // Reduce - accumulate()
auto result = accumulate(v.begin(), v.end(), 0, [](auto accum, auto item){ return accum * item; });


// deep-clone
// Only way is to create a new vector and use constructor notation
vector<int> v2(v1.begin(), v1.end()); // even array elements are created from scratch
// by default, all ops - copy, swap, insert do shallow copy

// USELESS at, back, rbegin, rend
```

## List (linked list)
USP: ADT
```c++
list<int> v; // doubly linked list
list<int> v (10); // size 10, filled garbage
list<int> v (10, 0); // size 10, filled with 0s
list<int> v1 (v2); // create and copy values

// Random access not allowed
ll.front(); // last element access, write
ll.back(); // last element access, write
ll.insert(); // behavior same as vector

ll.size(); // current filled length of vector
ll.empty(); // is empty?

ll.push_back(10); // insert at back, O(1)
ll.push_front(10); // insert at front, O(1)

// iterator
vector<int>::iterator it = v.begin(); // index 0, rightward
vector<int>::iterator it = v.end(); // index n, rightward
it++, it--; // both possible

// looping
for(auto it = ll.begin(); it != ll.end(); it++) { cout << *it; }
for(auto a: ll) { cout << a; }

// other things same as vector, swap
```

## Deque (double sided vector)
USP: double sided vector.
```c++
deque<int> v; // vector with both front, back ops
// all other things same as vector, swap
```

## Stack (strict ADT)
USP: LIFO
```c++
stack<int> stk; // LIFO structure
// no initialization list

stk.push();// insert O(1)
stk.pop(); // remove O(1)
stk.top(); // access - read/write O(1)

stk.size();
stk.empty();

// iterator - none

// looping
while(!stk.empty()) { cout << stk.top(); stk.pop(); }

// utils - swap
```

## Queue (strict ADT)
USP: FIFO
```c++
queue<int> q; // LIFO structure,
// no initialization list

// ops same as stack
q.push();// insert O(1)
q.pop(); // remove O(1)
q.front(); // access - read/write O(1)
q.back(); // access - read/write O(1)

q.size();
q.empty();

// iterator - none

// looping
while(!q.empty()) { cout << q.front(); q.pop(); }

// utils - swap
```

## priority-queue/Heap (strict ADT)
USP: quick extrema access, quick insertion/deletion. Compared to sorted array.
```c++
// get max, min element quickly (lgn)
priority_queue<int> pq; // max heap
priority_queue<int, vector<int>, greater<int>> pq; // min heap
// no initialization list

// ops same as stack
pq.push();// insert - O(lgn)
pq.pop(); // remove - O(lgn)
pq.top(); // access - read/write - O(1)

pq.size();
pq.empty();

// iterator - none

// looping
while(!pq.empty()) { cout << pq.top(); pq.pop(); }

// utils - swap
```

## Set (balanced tree)
Remember one thing, set means - { sorted, unique }. Other 2 related structures are combinations of this.
```c++
set<int> s; // balanced tree (detail: Red-Black-Tree)
set<int> s {1, 2, 3}; // initialization list is allowed 
set<int> s (s2.begin(), s2.end()); // deep clone

s.insert(1);// insert - O(lgn)
s.erase(it); // remove - O(lgn)
	s.erase(5); // deletes the element (yes close polymorh)
	s.erase(startI, endI); // remove - O(lgn)

s.count(23);// exists? - 1 means true, 0 means false - O(lgn)
auto it = s.find(1); // get iterator to element - O(lgn), returns s.end() if not found
*it; // access - read ONLY (access requires finding) - O(1)
auto it = lower_bound(2);
auto it = upper_bound(23);


s.size();
s.empty();

// iterator
s.begin(); // moves in sorted order
s.end();

// looping
for(auto it = s.begin(); it != s.end(); it++) { cout << *it; }
for(auto a: s) { cout << a; }>)

// utils - swap
```

### Multi-set (not used frequently)
sorted. not unique.
```c++
multiset<int> s;
multiset<int> s {1, 2, 3}; // initialization list is allowed 
multiset<int> s (s2.begin(), s2.end()); // deep clone

s.insert(1);// insert - O(lgn)
s.erase(it); // remove - O(lgn), only erases one occurence (relevant if multiple are present)
	s.erase(5); // deletes all such elements (yes close polymorh) - DANGEROUS
	s.erase(startI, endI); // remove - O(lgn)

s.count(23);// exists? - frequency, 0 means no existent - O(lgn)
auto it = s.find(1); // get first occurence iterator to element - O(lgn), returns s.end() if not found
*it; // access - read ONLY (access requires finding) - O(1)
auto it = lower_bound(2); // first occurrence
auto it = upper_bound(23); // last occurrence

s.size();
s.empty();

// iterator
s.begin(); // moves in sorted order
s.end();

// looping
for(auto it = s.begin(); it != s.end(); it++) { cout << *it; }
for(auto a: s) { cout << a; }>)

// utils - swap, lower_bound, upper_bound
```

### Unordered set (actual math set)
not sorted. unique.
```c++
unordered_set<int> s;
unordered_set<int> s {1, 2, 3}; // initialization list is allowed 
unordered_set<int> s (s2.begin(), s2.end()); // deep clone

s.insert(1);// insert - O(1)
s.erase(it); // remove - O(1), only erases one occurence (relevant if multiple are present)
	s.erase(5); // deletes all such elements (yes close polymorh) - DANGEROUS
	s.erase(startI, endI); // remove - O(lgn)

s.count(23);//// exists? - 1 means true, 0 means false - O(1)
auto it = s.find(1); // get iterator to element - O(1), returns s.end() if not found
*it; // access - read ONLY (access requires finding) - O(1)
// lower_bound, upper_bound DO NOT work

s.size();
s.empty();

// iterator
s.begin(); // moves in sorted order
s.end();

// looping
for(auto it = s.begin(); it != s.end(); it++) { cout << *it; }
for(auto a: s) { cout << a; }>)

// utils - swap
```


Note: 
- `multiset` - syntax same as set. sorted. not unique.
- `unordered_set` - syntax same as set. not sorted. unique.
- `unordered_multiset` - syntax same as set. non-sorted, non-unique. USP (over vector): fast access, insert, deletion


## Map
Keyed data structure.
{ sorted, unique }. Other 2 related structures are combinations of this.
```c++
map<int, int> mp;
map<int, int> mp { {1: 10}, {2, 20}, {3, 30} }; // initialization list is allowed
map<int, int> mp (mp2.begin(), mp2.end()); // deep clone
// key can be any trivial combination, int x string x pair
// value can be anything

// ops same as stack, but named diff
mp.insert(1);// insert - O(lgn)
	mp[1] = 2; // insert/write in one go, returns NULL if that value does not exist.
	
mp.erase(it); // remove - O(lgn)
	mp.erase(5); // deletes the element (yes close polymorh)
	mp.erase(startI, endI); // remove - O(lgn)

mp.count(23);// exists? - 1 means true, 0 means false - O(lgn)
auto it = mp.find(1); // get iterator to element - O(lgn), returns mp.end() if not found
auto it = lower_bound(2); // first occurrence of key
auto it = upper_bound(23); // last occurrence of key
(*it).first; // read key
(*it).second, (*it).second = 4; // read/write value

mp.size();
mp.empty();

// iterator
mp.begin(); // moves in sorted order
mp.end();

// looping
for(auto it = s.begin(); it != s.end(); it++) { cout << *it; }
for(auto a: mp) { cout << a.first << a.second << endl; } // internally behaves like a collection of pairs

// utils - swap
```

### Multimap (not used frequently)
sorted. not unique.
```c++
multimap<int, int> mp;
multimap<int, int> mp { {1: 10}, {2, 20}, {3, 30}, {3, 40} }; // initialization list is allowed
multimap<int, int> mp (mp2.begin(), mp2.end()); // deep clone

// everything same as map, only it can store multiple keys
// only mpp[key] cannot be used here, since ambiguous access
```

### Unordered (actual raw hashmap)
not sorted. unique.
```c++
unordered_map<int, int> mp;
unordered_map<int, int> mp { {1: 10}, {2, 20}, {3, 30} }; // initialization list is allowed
unordered_map<int, int> mp (mp2.begin(), mp2.end()); // deep clone

// same as map
// lower_bound DOESNT work
// upper_bound DOESNT work
```


Note: 
- `multimap` - syntax same as set. sorted. not unique.
- `unordered_map` - syntax same as set. not sorted. unique.
- `unordered_multimap` - syntax same as set. non-sorted, non-unique. USP: keyed, fast access, insert, deletion