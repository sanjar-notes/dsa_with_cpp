# 3. Queue using Dynamic Array - Code
Created Thursday 23 January 2020

[queueMain.cpp](3._Queue_using_Dynamic_Array_-_Code/queueMain.cpp)
[queueUsingDynamicArray.h](3._Queue_using_Dynamic_Array_-_Code/queueUsingDynamicArray.h)


* Circularity is important here too, as doubling is onlt if size\>=capacity.



* The only change required is in the enqueue function, that too in the case when size\==capacity. Note that a rearrangement is required if this has to be carried out. To ensure that circularity is maintained.



1. enqueue(T idata) function:

if(size==0) // for the start
{
size = 1;
firstIndex = 0;
nextIndex = 1;
data[firstIndex] = idata;
return;
}
	
else if(size==capacity)
{
//	assuming capacity is always > 0
T* newData = new T[capacity*2];
		
// rearrange the circular queue as a normal queue, we need a value going from 0 to capacity-1 and also need to travel all the elements.
for(int i=firstIndex, count = 0; count < capacity; i =(i+1)%capacity, count++)
newData[count] = data[i];
newData[capacity] = idata;
//delete the old array
delete[] data;
data = newData;
// set the attributes as that of a linear queue
size++;
firstIndex = 0;
lastIndex = size;	// effectively capacity + 1
capacity*=2;
}
else
{
we need to insert element at nextIndex, move it to the next circularly
data[nextIndex] = idata;
nextIndex = (nextIndex+1)%capacity;	// no change at head
}

*****


* Every other function is the same.


