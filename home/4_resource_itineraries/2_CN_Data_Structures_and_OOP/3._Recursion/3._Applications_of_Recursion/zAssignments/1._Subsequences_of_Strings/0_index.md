# 1. Subsequences of Strings
Created Friday 03 January 2020

**Jargon:**

* subarray or substring: All possible(basically of any length from **0** to size) **contiguos elements** of the given array or string.
* subsequences: A subsequence is a sequence that can be derived from the given sequence by deleting some or no elements without changing the order of the remaining elements, i.e if 'a' comes before 'f' in the original string, then it shall do this in all subsequences containing a and f. Each element has it's own identity(even if there are duplicates).

**(Note: Repetition is not allowed in both, wysiwyg)**

How many for a string of length n:

* Subarrays or substrings: 
	1. We will add all contiguous subarrays of size 0 to n.
	2. size 0: 1, size 1: n, size 2: n-1, size 3: n-2 ... size r: n-r+1 ... size n: 1 
	3. Add all of these, 1+(n)+(n-1)+(n-2)+(n-3)+ ... + 1 = 1 + n(n+1)/2 = n(n+1)/2 + 1 
	4. i.e count = n(n+1)/2 + 1(empty string).


e.g subarrays or substrings for for abc: "", a, b, c, ab, bc, abc. 6+1


* Subsequences (the power set).
	1. We add all possible strings which have the same relative ordering of the elements.

2.P and C: For every letter, we have a choice (take/leave). All are independent, product principle. And every set of choice is different from the other.

3. So 2^n ^(including the empty string i.e take none). 

e.g subsequences for abc: "", a, b, c, ab, ac, bc, abc. 2^3^=8

Q) Print/Collect all subsequences for the given array.
A) 	[All Subsequences](1._Subsequences_of_Strings/all_subsequences.cpp)
Input: String and output array address(of sufficient size).
Output: void? But we will need to give length of the string array, as there's no delimiter for the given array. Better if we return the size. So int should be the return type.
	
Base case: if(input.empty()) 
output[0] = "";
return 1;
why? Because this the first element that will be printed.
**Doubt(will "" come only once): **This will be executed only once. As we have only one recursion call, so only one anchor is possible.

* It is important that the base case be very simple, as the single case is **really **the case of the variable belonging to the activation record.
* **Believe in yourself, that is the best you can do. For anything fun and useful, you are very good. Just Chill. Alhamdulillah.**

	
We assume that our recursion will fill the output array with all subsequneces of substr(1).
Here, we will prepend the elements with the current Activation record's character, and add these to the ouput array.
We will use count as a variable to make a for loop copy "these" after the latest vacant position, which is nothing but "count"
output[count+i] = s[0]+output[i]; // we can append a character to a string it's okay. **This is a very clever trick. It's ubiquitous.**
return 2*count; // Just return the current output array size, 2 times of what was there before the loop.

* Uses: This problem can be used to solve keypad problems, it is the basis of most problems where we will store our inputs and make changes. We will use this idea.


**Why? In 'storage', if we do calc first, we'll have to pass the number of copies as we go, which is very painful. Better we do **CBA **and return1 for the empty array. This will ensure that we are right. And we don't have to explicitly deal with the number of values. **
Remember that we need to return the number of elements, and creating another formal parameter will be of significant overhead.

Q) Code all possibilities of a keypad, single press mode.
e.g 23 : dg dh di eg eh ei fg fh fi
A) Using the same logic as recursion, do this. Let us make the base case sober(key here is **returning 1 and "" when nothing is printed and with 1**). Let's code the printing of values in the calc step.
[Keypad print](1._Subsequences_of_Strings/lectureCodes.md)

