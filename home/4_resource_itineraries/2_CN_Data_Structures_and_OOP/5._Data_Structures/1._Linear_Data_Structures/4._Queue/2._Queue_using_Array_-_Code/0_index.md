# 2. Queue using Array - Code
Created Thursday 23 January 2020

[queueMain.cpp](2._Queue_using_Array_-_Code/queueMain.cpp)
[queueUsingArray.h](2._Queue_using_Array_-_Code/queueUsingArray.h)

1. enqueue(T data) function:
   ```cpp
   if (size == 0) // for the start
   {
       size = 1;
       firstIndex = 0;
       nextIndex = 1;
       data[firstIndex] = idata;
       return;
   }

   else if (size == capacity)
   {
       message();
       return;
   }
   else
   {
       // we need to insert element at nextIndex, move it to the next circularly
       data[nextIndex] = idata;
       nextIndex = (nextIndex + 1) % capacity; // no change at head
       size++;
   }
   ```
2. Dequeue function:
   ```cpp
   if (size == 0)
   {
       message();
       return generic_value;
   }
   else if (size == 1) // for debugging purposes, covered in the else case too
   {
       T ans = data[firstIndex];
       firstIndex = -1;
       nextndex = 0;
       size = 0;
       return T;
   }
   else
   {
       T ans = data[firstIndex];
       firstIndex = (firstIndex + 1) % capacity;
       size--;
       return ans;
   }
   ```
3. int getSize():
   ```cpp
   {
       return size;
   }
   ```
4. bool isEmpty()
   ```cpp
   {
       return size == 0;
   }
   ```
5. T front():
```cpp
   {
       if(size==0)
         return generic_value;

       return data[firstIndex];
   }
```
6. void print():
```cpp
// very interesting, we have to move circularly size number of times
{
    cout << "f[";
    for (int i = firstIndex, count = 0; count < size; i = (i + 1) % capacity)
        cout << data[i] << ", ";
    if (size = 0)
        cout << "]b\n";
    else
        cout << "\b\b]b\n";
}
```
