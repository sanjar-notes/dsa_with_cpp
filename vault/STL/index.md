# STL
Created Sun May 12, 2024 at 7:35 PM

- Containers - trees, vectors, hashmaps.
- Iterators (actually relevant only in context of a container). help in iterating over containers, including non-linear ones. This topic also refers to the general pattern and syntax of iterators, namely .begin, .end.
- Algorithms
	- Utils - sort, find, reverse, higher order functions
	- Fast state space utils - lower_bound, upper_bound, min, max
	- PnC - permutations
- Functors - these are "classes that can be reused as functions" change the way how algorithms, containers behave. Example: min priority_queue (default is max), reverse sort.
	- Completely custom functors are also used. Example: custom sort behavior.

## Note
- I use `auto` (frequently), `decltype` (in few places) to make code concise.
- higher order function idioms like map, filter, reduce have been discussed. These are usually skipped by beginners and makes for long, unstructured code in problems. HOFs solve this problem since they effectively are a vocabulary thats very similar to simple and abstract math ops.
- Data types variates - Almost all containers, algorithms accept combinations of any data type. 
	- For situation that require hashes to be computed, generally all combinations of trivial structures like `int`, `string`, `pair`, `vector` work out of the box. *Most algorithm problems online encode data as numbers so it's usually not a requirement to specify custom hash functions for classes, and I shall try to avoid doing this for unnecessary work reasons*.
	- Nesting is OK in data types.
- I use lambdas instead of explicit (custom) functors wherever the are needed. `[](){}` simple syntax. Another good thing is `auto` is guaranteed to work since it's lexically close to related code.