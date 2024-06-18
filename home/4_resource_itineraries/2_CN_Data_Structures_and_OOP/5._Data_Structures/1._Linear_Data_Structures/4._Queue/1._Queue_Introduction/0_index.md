# 1. Queue Introduction
Created Wednesday 22 January 2020


* Queues are a fundamental ADT.
* It follows FIFO.
* A queue two ends, entry and exit.
* The interface is:
	1. enqueue(data) - inserts the data at the entry. Returns nothing.
	2. front() - returns the element near exit. It is a void function.
	3. dequeue() - deletes and returns(in our version) the element at exit.
	4. isEmpty() returns true for empty queue, else false.
	5. size() returns the size.


In case of arrays, the problem of space wastage can be solved by the following methods:

1. Shift all elements to the left. Very very time consuming.
2. Use a circular system.


We use only 2 as 1 is very inefficient.

## Real world use of queues - theory
Jobs processed in FIFO order minimize the maximum time spent waiting. 

Note that the average waiting time will be the same regardless of whether FIFO or LIFO is used.

Queue is essential in graphs, since it's the controlling data structure in BFS.