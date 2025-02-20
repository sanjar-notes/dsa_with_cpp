# 2. Printing subsequence
Created Saturday 04 January 2020

* Printing is different from storing. Space requirement is 2^n^.
* Realise that the subsequence'f' of f(k, abc)  = f(k, bc) + f(ka, bc). Yes, this is true, the first string is what is "fixed" and will be printed.
* **What about short strings, that can be handled in the main() call, by calling f("", input). One node will keep generating only smaller ones.**
* **Learnt: **In recursion, the function call from main is very important.
* The **first one** helps in generating deleting values subsequences, while the **2nd one** helps in progressing old ones with all possible new ones. **Saying this is important. It may not be directly technically useful, but provides the motivation.**
* i.e we are either including or excluding the head character.
* We **do** carry our output with us.
* print when input is an empty string. Use substr(liberally).
* Space complexity: Same as the height of the tree. Here it is the same as the node where we get the output as the string size.
* As this is a binary tree, hence we have 2**n leaf nodes. Storing had only one leaf node, as it was a skewed tree. Printing is not a skewed tree.

[All subsequences](2._Printing_subsequence/all_subsequences.cpp)

Print Keypad:
Step

1. try some example, 23 9 possiblilites.
2. As this is like a subsequence, except for the fact that we have toPut.size() number of problems, and not a simple inclusion/exclusion.
3. We will prefer %10 rather than storing up a divider(10^r). This decides toPut, which will surely be prepended to the output.
4. 234, as an example can be written as f(234,"")= f(23, toPut(i)+""). The recurrence relation. **Maybe** we can escape using memoization. But that is just storing, **busted**.
5. Base case: When we get num==0(num and not a digit okay, they are different), just print the output.

[Keypad Problem](2._Printing_subsequence/print_keypad.cpp)

