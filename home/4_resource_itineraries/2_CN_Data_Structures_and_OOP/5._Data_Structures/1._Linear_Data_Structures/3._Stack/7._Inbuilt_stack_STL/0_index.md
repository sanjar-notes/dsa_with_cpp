# 7. Inbuilt stack STL
Created Wednesday 22 January 2020

[stack_STL.cpp](7._Inbuilt_stack_STL/stack_STL.cpp)

* Stacks has are already been implemented in C++ STL. `<stack>`
* We will learn to use it.

1. It's better that we use **.h** now. We do this so as to avoid making main() inside the .h, as this is not allowed.
2. If we write "something".h, the header is in the directory of the main file. For anywhere else, specify the complete address or use . and .. if that does the job.
3. Inbuilt headers are included using <>


For stacks header is: `<stack>` which is a template type.


* What we have implemented is more or less the same. The interface is:
	0. stack is the name of the class Stack.
	1. push() is the same , i.e void push(T element);
	2. pop() is **different**, it is a void.
	3. top() is the same. returns the element on the top.
	4. empty() is the **changed** name in STL, same as our implementation.
	5. size() is the same.

Note: There's no need for any other thing execpt that told here.


