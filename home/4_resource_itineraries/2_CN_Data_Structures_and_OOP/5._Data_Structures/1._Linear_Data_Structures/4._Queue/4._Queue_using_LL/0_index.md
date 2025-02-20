# 4. Queue using LL
Created Thursday 23 January 2020

[queueMain.cpp](4._Queue_using_LL/queueMain.cpp)
[queueUsingLL.h](4._Queue_using_LL/queueUsingLL.h)

As per the interface:
1. We need to keep size
2. For o(1) insertion, we always insert at the tail So a tail is required. Tail points to the last node in the queue.
3. For o(1) deletion, we remove from head. So we need a head. Head points to the first node in the queue.
4. front is also o(1) as we just need to print the head's data, if it exists.

* There's no need for being circular here. All operations are o(1), except print which is O(N) for both arrays and index.
* Hence it is established that basic stack and queues equally efficient in both their implementations, arrays and LL.