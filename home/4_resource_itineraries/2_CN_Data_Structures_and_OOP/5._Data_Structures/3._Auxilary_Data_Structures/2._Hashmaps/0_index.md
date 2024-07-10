# 2. Hashmaps
Created Tuesday 18 February 2020

Aka hash table.

[Codes](./2._Hashmaps/Codes)
[Exercises.md](./2._Hashmaps/Quizzes&Exercises/Exercises.md)
[CodingExercises.md](./2._Hashmaps/Quizzes&Exercises/CodingExercises.md)
[Assignments.md](./2._Hashmaps/zAssignments/Assignments.md)

## Dictionary ADT
The dictionary data type permits access to data items by content. You stick an item into a dictionary so you can find it when you need it. The primary operations dictionaries support are:
- **Search**(D,k) – Given a search key k, return a pointer to the element in dictionary D whose key value is k, if one exists.
- **Insert**(D,x) – Given a data item x, add it to the dictionary D.
- **Delete**(D,x) – Given a pointer x to a given data item in the dictionary D, remove it from D.

Certain dictionary data structures also efficiently support other useful operations:
- **Max**(D) or **Min**(D) – Retrieve the item with the largest (or smallest) key from D. This enables the dictionary to serve as a priority queue, as will be discussed in Section 3.5 (page 87).
- **Predecessor**(D,x) or **Successor**(D,x) – Retrieve the item from D whose key is immediately before (or after) item x in sorted order. These enable us to iterate through the elements of the data structure in sorted order.

Note:
- In Skiena's book, dictionary is the ADT, hashing or sorting are implementation details. He considers many implementations including arrays/linked-lists, singly/doubly linked-lists, sorted/unsorted versions.