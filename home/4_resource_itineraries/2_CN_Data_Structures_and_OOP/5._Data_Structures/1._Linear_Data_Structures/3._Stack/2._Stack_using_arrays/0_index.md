# 2. Stack using arrays
Created Wednesday 22 January 2020

We want to create a stack using a static array, whose capacity will be set by the user.

We are controlling the ADT by using a class. Where only the interface functions are public, everything else is private.

Working:
Our head is the lastIndex, as insertion and removal is O(1).
We store this top(i.e lastIndex).
[stackUsingArray.cpp](2._Stack_using_arrays/stackUsingArray.cpp)
[stackMain.cpp](2._Stack_using_arrays/stackMain.cpp)