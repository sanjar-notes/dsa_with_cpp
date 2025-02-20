# 1. Take input and print recursive
Created Saturday 25 January 2020

We want to achieve two things:
1. Print function - `void printTree(TreeNode<T>* root)`
	* Tree has a very easy and intuitive structure, i.e print the root and call print on all the subtrees.
	* We don't require **base cases** in generic trees, checking for NULL is an **edge case**. Both are different. Base case nake a recursion stop, while edge cases break the program or cause an error/exception.
	* We don't require a base case coz we never hit a coming back point.
	* The caller works as base case. 
	* We never call from a NULL, coz we are using vectors, so we never use a garbage or empty list.
2. Input function
	```cpp
	TreeNode<int>* takeInput()
	{
	// ask root data
	// no. of children
	// call takeInput three, 3 subtrees done.
	}
	```
* We create a node, only when we ask the value for it. This we don't have to keep a track of the variables for the children and all.
* No need of base case as input will be taken if no.of children > 0. Else it will hit brace. i.e we won't go any further.
* The function creates atleast one node.
* takeInput() is easy to make, but using it is difficult.


We'll be using recursion in 95% of the tree problems. 
[TreeNode_Input_and_Print.h](1._Take_input_and_print_recursive/TreeNode_Input_and_Print.h)
[treeMain.cpp](1._Take_input_and_print_recursive/treeMain.cpp)