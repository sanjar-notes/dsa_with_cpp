---
tags:
  - dsa-model
---
# 10. Advanced Analysis
Created Tue May 7, 2024 at 11:20 AM

## Esoteric Functions
- Inverse Ackermann’s function f(n) = α(n).
- f(n) = log(logn). One natural example of how it might arise is doing a binary search on a sorted array of only lg n items.
- f (n) = log n/ log(log n).
- f(n) = log<sup>2</sup>n. Example: we were doing a binary search on n integers, where each one of them was in range 1 to n<sup>2</sup>. Seeing at a very low level, we have to scan log(n) times, and considering each number takes log(n) time, so logn \* log n. Also, the “log squared” function typically arises in the design of intricate nested data structures, where each node in (say) a binary tree represents another data structure, perhaps ordered on a different key.
- f(n) = sqrt(n). Similar to a d-dimensional hypercube of length n<sup>1/d</sup> on each side has volume n.
- f(n) = n<sup>(1+ε)</sup>. Epsilon (ε) is the mathematical symbol to denote a con- stant that can be made arbitrarily small but never becomes zero. Such a expression comes into where there are two sub-expressions involved, like 2<sup>c</sup> · n<sup>(1+1/c)</sup>, where c can be chosen to be anything. But if we try to make c fixed, say a large value, then the first term will become very large. So, the only option is to let the parameter c be included in the expression, and leave the choice of c to be decided by the user of the expression.

## Limits and dominance relations
The dominance relations (classes) we discussed earlier can be proven (i.e. the comparisons can be proven using limits, as in calculus). We just divide the smaller by the claimed larger and put n -> Infinity. If it comes out to be zero, the comparison holds.

![](../../../../assets/10-Advanced-Analysis-image-1-23f8dd9b.png)

```sh
[|	"Contents"	#page=6&view=Fit
|	"Preface"	#page=14&view=Fit
+	"I Foundations"	#page=23&view=Fit
|		"1 The Role of Algorithms in Computing"	#page=26&view=Fit
|		"2 Getting Started"	#page=37&view=Fit
|		"3 Growth of Functions"	#page=64&view=Fit
|		"4 Divide-and-Conquer"	#page=86&view=Fit
|		"5 Probabilistic Analysis and Randomized Algorithms"	#page=135&view=Fit
+	"II Sorting and Order Statistics"	#page=167&view=Fit
|		"6 Heapsort"	#page=172&view=Fit
|		"7 Quicksort"	#page=191&view=Fit
|		"8 Sorting in Linear Time"	#page=212&view=Fit
|		"9 Medians and Order Statistics"	#page=234&view=Fit
+	"III Data Structures"	#page=249&view=Fit
|		"10 Elementary Data Structures"	#page=253&view=Fit
|		"11 Hash Tables"	#page=274&view=Fit
|		"12 Binary Search Trees"	#page=307&view=Fit
|		"13 Red-Black Trees"	#page=329&view=Fit
|		"14 Augmenting Data Structures"	#page=360&view=Fit
+	"IV Advanced Design and Analysis Techniques"	#page=377&view=Fit
|		"15 Dynamic Programming"	#page=380&view=Fit
|		"16 Greedy Algorithms"	#page=435&view=Fit
|		"17 Amortized Analysis"	#page=472&view=Fit
+	"V Advanced Data Structures"	#page=501&view=Fit
|		"18 B-Trees"	#page=505&view=Fit
|		"19 Fibonacci Heaps"	#page=526&view=Fit
|		"20 van Emde Boas Trees"	#page=552&view=Fit
|		"21 Data Structures for Disjoint Sets"	#page=582&view=Fit
+	"VI Graph Algorithms"	#page=607&view=Fit
|		"22 Elementary Graph Algorithms"	#page=610&view=Fit
|		"23 Minimum Spanning Trees"	#page=645&view=Fit
|		"24 Single-Source Shortest Paths"	#page=664&view=Fit
|		"25 All-Pairs Shortest Paths"	#page=705&view=Fit
|		"26 Maximum Flow"	#page=729&view=Fit
+	"VII Selected Topics"	#page=789&view=Fit
|		"27 Multithreaded Algorithms"	#page=793&view=Fit
|		"28 Matrix Operations"	#page=834&view=Fit
|		"29 Linear Programming"	#page=864&view=Fit
|		"30 Polynomials and the FFT"	#page=919&view=Fit
|		"31 Number-Theoretic Algorithms"	#page=947&view=Fit
|		"32 String Matching"	#page=1006&view=Fit
|		"33 Computational Geometry"	#page=1035&view=Fit
|		"34 NP-Completeness"	#page=1069&view=Fit
|		"35 Approximation Algorithms"	#page=1127&view=Fit
-	"VIII Appendix: Mathematical Background"	#page=1163&view=Fit
|		"A Summations"	#page=1166&view=Fit
|		"B Sets, Etc."	#page=1179&view=Fit
|		"C Counting and Probability"	#page=1204&view=Fit
|		"D Matrices"	#page=1238&view=Fit
|	"Bibliography"	#page=1252&view=Fit
|	"Index"	#page=1272&view=Fit](<-	"Preface"	#page=6&view=Fit
|		"To the Reader"	#page=6&view=Fit
|		"To the Instructor"	#page=8&view=Fit
|		"Acknowledgments"	#page=9&view=Fit
|		"Caveat"	#page=9&view=Fit
|	"Contents"	#page=10&view=Fit
-	"Part I Practical Algorithm Design"	#page=19&view=Fit
+		"Chapter 1 Introduction to Algorithm Design"	#page=20&view=Fit
|			"1.1 Robot Tour Optimization"	#page=22&view=Fit
|			"1.2 Selecting the Right Jobs"	#page=25&view=Fit
+			"1.3 Reasoning about Correctness"	#page=28&view=Fit
|				"1.3.1 Problems and Properties"	#page=28&view=Fit
|				"1.3.2 Expressing Algorithms"	#page=29&view=Fit
|				"1.3.3 Demonstrating Incorrectness"	#page=30&view=Fit
|			"1.4 Induction and Recursion"	#page=32&view=Fit
+			"1.5 Modeling the Problem"	#page=34&view=Fit
|				"1.5.1 Combinatorial Objects"	#page=34&view=Fit
|				"1.5.2 Recursive Objects"	#page=36&view=Fit
|			"1.6 Proof by Contradiction"	#page=38&view=Fit
|			"1.7 About the War Stories"	#page=39&view=Fit
|			"1.8 War Story: Psychic Modeling"	#page=39&view=Fit
|			"1.9 Estimation"	#page=42&view=Fit
|			"1.10 Exercises"	#page=44&view=Fit
+		"Chapter 2 Algorithm Analysis"	#page=48&view=Fit
+			"2.1 The RAM Model of Computation"	#page=48&view=Fit
|				"2.1.1 Best-Case, Worst-Case, and Average-Case Complexity"	#page=49&view=Fit
|			"2.2 The Big Oh Notation"	#page=51&view=Fit
+			"2.3 Growth Rates and Dominance Relations"	#page=54&view=Fit
|				"2.3.1 Dominance Relations"	#page=55&view=Fit
+			"2.4 Working with the Big Oh"	#page=56&view=Fit
|				"2.4.1 Adding Functions"	#page=57&view=Fit
|				"2.4.2 Multiplying Functions"	#page=57&view=Fit
+			"2.5 Reasoning about E\x0Eciency"	#page=58&view=Fit
|				"2.5.1 Selection Sort"	#page=58&view=Fit
|				"2.5.2 Insertion Sort"	#page=59&view=Fit
|				"2.5.3 String Pattern Matching"	#page=60&view=Fit
|				"2.5.4 Matrix Multiplication"	#page=62&view=Fit
|			"2.6 Summations"	#page=63&view=Fit
+			"2.7 Logarithms and Their Applications"	#page=65&view=Fit
|				"2.7.1 Logarithms and Binary Search"	#page=66&view=Fit
|				"2.7.2 Logarithms and Trees"	#page=66&view=Fit
|				"2.7.3 Logarithms and Bits"	#page=67&view=Fit
|				"2.7.4 Logarithms and Multiplication"	#page=67&view=Fit
|				"2.7.5 Fast Exponentiation"	#page=67&view=Fit
|				"2.7.6 Logarithms and Summations"	#page=68&view=Fit
|				"2.7.7 Logarithms and Criminal Justice"	#page=68&view=Fit
|			"2.8 Properties of Logarithms"	#page=69&view=Fit
|			"2.9 War Story: Mystery of the Pyramids"	#page=71&view=Fit
+			"2.10 Advanced Analysis (*)"	#page=74&view=Fit
|				"2.10.1 Esoteric Functions"	#page=74&view=Fit
|				"2.10.2 Limits and Dominance Relations"	#page=75&view=Fit
|			"2.11 Exercises"	#page=76&view=Fit
+		"Chapter 3 Data Structures"	#page=85&view=Fit
+			"3.1 Contiguous vs. Linked Data Structures"	#page=85&view=Fit
|				"3.1.1 Arrays"	#page=86&view=Fit
|				"3.1.2 Pointers and Linked Structures"	#page=87&view=Fit
|				"3.1.3 Comparison"	#page=90&view=Fit
|			"3.2 Containers: Stacks and Queues"	#page=91&view=Fit
|			"3.3 Dictionaries"	#page=92&view=Fit
+			"3.4 Binary Search Trees"	#page=97&view=Fit
|				"3.4.1 Implementing Binary Search Trees"	#page=97&view=Fit
|				"3.4.2 How Good are Binary Search Trees?"	#page=101&view=Fit
|				"3.4.3 Balanced Search Trees"	#page=102&view=Fit
|			"3.5 Priority Queues"	#page=103&view=Fit
|			"3.6 War Story: Stripping Triangulations"	#page=105&view=Fit
+			"3.7 Hashing"	#page=109&view=Fit
|				"3.7.1 Collision Resolution"	#page=109&view=Fit
|				"3.7.2 Duplicate Detection via Hashing"	#page=111&view=Fit
|				"3.7.3 Other Hashing Tricks"	#page=112&view=Fit
|				"3.7.4 Canonicalization"	#page=112&view=Fit
|				"3.7.5 Compaction"	#page=113&view=Fit
|			"3.8 Specialized Data Structures"	#page=114&view=Fit
|			"3.9 War Story: String 'em Up"	#page=114&view=Fit
|			"3.10 Exercises"	#page=119&view=Fit
+		"Chapter 4 Sorting"	#page=125&view=Fit
|			"4.1 Applications of Sorting"	#page=125&view=Fit
|			"4.2 Pragmatics of Sorting"	#page=129&view=Fit
+			"4.3 Heapsort: Fast Sorting via Data Structures"	#page=131&view=Fit
|				"4.3.1 Heaps"	#page=132&view=Fit
|				"4.3.2 Constructing Heaps"	#page=134&view=Fit
|				"4.3.3 Extracting the Minimum"	#page=136&view=Fit
|				"4.3.4 Faster Heap Construction (*)"	#page=138&view=Fit
|				"4.3.5 Sorting by Incremental Insertion"	#page=140&view=Fit
|			"4.4 War Story: Give me a Ticket on an Airplane"	#page=141&view=Fit
|			"4.5 Mergesort: Sorting by Divide and Conquer"	#page=143&view=Fit
+			"4.6 Quicksort: Sorting by Randomization"	#page=146&view=Fit
|				"4.6.1 Intuition: The Expected Case for Quicksort"	#page=148&view=Fit
|				"4.6.2 Randomized Algorithms"	#page=149&view=Fit
|				"4.6.3 Is Quicksort Really Quick?"	#page=151&view=Fit
+			"4.7 Distribution Sort: Sorting via Bucketing"	#page=152&view=Fit
|				"4.7.1 Lower Bounds for Sorting"	#page=153&view=Fit
|			"4.8 War Story: Skiena for the Defense"	#page=154&view=Fit
|			"4.9 Exercises"	#page=156&view=Fit
+		"Chapter 5 Divide and Conquer"	#page=163&view=Fit
+			"5.1 Binary Search and Related Algorithms"	#page=164&view=Fit
|				"5.1.1 Counting Occurrences"	#page=164&view=Fit
|				"5.1.2 One-Sided Binary Search"	#page=165&view=Fit
|				"5.1.3 Square and Other Roots"	#page=166&view=Fit
|			"5.2 War Story: Finding the Bug in the Bug"	#page=166&view=Fit
+			"5.3 Recurrence Relations"	#page=168&view=Fit
|				"5.3.1 Divide-and-Conquer Recurrences"	#page=169&view=Fit
|			"5.4 Solving Divide-and-Conquer Recurrences"	#page=170&view=Fit
|			"5.5 Fast Multiplication"	#page=171&view=Fit
|			"5.6 Largest Subrange and Closest Pair"	#page=173&view=Fit
+			"5.7 Parallel Algorithms"	#page=175&view=Fit
|				"5.7.1 Data Parallelism"	#page=175&view=Fit
|				"5.7.2 Pitfalls of Parallelism"	#page=176&view=Fit
|			"5.8 War Story: Going Nowhere Fast"	#page=177&view=Fit
+			"5.9 Convolution (*)"	#page=178&view=Fit
|				"5.9.1 Applications of Convolution"	#page=179&view=Fit
|				"5.9.2 Fast Polynomial Multiplication (**)"	#page=180&view=Fit
|			"5.10 Exercises"	#page=182&view=Fit
+		"Chapter 6 Hashing and Randomized Algorithms"	#page=186&view=Fit
+			"6.1 Probability Review"	#page=187&view=Fit
|				"6.1.1 Probability"	#page=187&view=Fit
|				"6.1.2 Compound Events and Independence"	#page=189&view=Fit
|				"6.1.3 Conditional Probability"	#page=190&view=Fit
|				"6.1.4 Probability Distributions"	#page=191&view=Fit
|				"6.1.5 Mean and Variance"	#page=191&view=Fit
|				"6.1.6 Tossing Coins"	#page=192&view=Fit
+			"6.2 Understanding Balls and Bins"	#page=194&view=Fit
|				"6.2.1 The Coupon Collector's Problem"	#page=195&view=Fit
|			"6.3 Why is Hashing a Randomized Algorithm?"	#page=196&view=Fit
|			"6.4 Bloom Filters"	#page=197&view=Fit
|			"6.5 The Birthday Paradox and Perfect Hashing"	#page=199&view=Fit
|			"6.6 Minwise Hashing"	#page=201&view=Fit
|			"6.7 Efficient String Matching"	#page=203&view=Fit
|			"6.8 Primality Testing"	#page=205&view=Fit
|			"6.9 War Story: Giving Knuth the Middle Initial"	#page=206&view=Fit
|			"6.10 Where do Random Numbers Come From?"	#page=207&view=Fit
|			"6.11 Exercises"	#page=208&view=Fit
+		"Chapter 7 Graph Traversal"	#page=211&view=Fit
+			"7.1 Flavors of Graphs"	#page=212&view=Fit
|				"7.1.1 The Friendship Graph"	#page=215&view=Fit
|			"7.2 Data Structures for Graphs"	#page=217&view=Fit
|			"7.3 War Story: I was a Victim of Moore's Law"	#page=221&view=Fit
|			"7.4 War Story: Getting the Graph"	#page=224&view=Fit
|			"7.5 Traversing a Graph"	#page=226&view=Fit
+			"7.6 Breadth-First Search"	#page=227&view=Fit
|				"7.6.1 Exploiting Traversal"	#page=230&view=Fit
|				"7.6.2 Finding Paths"	#page=231&view=Fit
+			"7.7 Applications of Breadth-First Search"	#page=231&view=Fit
|				"7.7.1 Connected Components"	#page=232&view=Fit
|				"7.7.2 Two-Coloring Graphs"	#page=233&view=Fit
|			"7.8 Depth-First Search"	#page=235&view=Fit
+			"7.9 Applications of Depth-First Search"	#page=238&view=Fit
|				"7.9.1 Finding Cycles"	#page=238&view=Fit
|				"7.9.2 Articulation Vertices"	#page=239&view=Fit
+			"7.10 Depth-First Search on Directed Graphs"	#page=244&view=Fit
|				"7.10.1 Topological Sorting"	#page=245&view=Fit
|				"7.10.2 Strongly Connected Components"	#page=246&view=Fit
|			"7.11 Exercises"	#page=249&view=Fit
+		"Chapter 8 Weighted Graph Algorithms"	#page=257&view=Fit
+			"8.1 Minimum Spanning Trees"	#page=258&view=Fit
|				"8.1.1 Prim's Algorithm"	#page=259&view=Fit
|				"8.1.2 Kruskal's Algorithm"	#page=262&view=Fit
|				"8.1.3 The Union–Find Data Structure"	#page=264&view=Fit
|				"8.1.4 Variations on Minimum Spanning Trees"	#page=267&view=Fit
|			"8.2 War Story: Nothing but Nets"	#page=268&view=Fit
+			"8.3 Shortest Paths"	#page=271&view=Fit
|				"8.3.1 Dijkstra's Algorithm"	#page=272&view=Fit
|				"8.3.2 All-Pairs Shortest Path"	#page=275&view=Fit
|				"8.3.3 Transitive Closure"	#page=277&view=Fit
|			"8.4 War Story: Dialing for Documents"	#page=278&view=Fit
+			"8.5 Network Flows and Bipartite Matching"	#page=281&view=Fit
|				"8.5.1 Bipartite Matching"	#page=281&view=Fit
|				"8.5.2 Computing Network Flows"	#page=282&view=Fit
|			"8.6 Randomized Min-Cut"	#page=286&view=Fit
|			"8.7 Design Graphs, Not Algorithms"	#page=288&view=Fit
|			"8.8 Exercises"	#page=290&view=Fit
+		"Chapter 9 Combinatorial Search"	#page=295&view=Fit
|			"9.1 Backtracking"	#page=295&view=Fit
+			"9.2 Examples of Backtracking"	#page=298&view=Fit
|				"9.2.1 Constructing All Subsets"	#page=298&view=Fit
|				"9.2.2 Constructing All Permutations"	#page=300&view=Fit
|				"9.2.3 Constructing All Paths in a Graph"	#page=301&view=Fit
|			"9.3 Search Pruning"	#page=303&view=Fit
|			"9.4 Sudoku"	#page=304&view=Fit
|			"9.5 War Story: Covering Chessboards"	#page=309&view=Fit
|			"9.6 Best-First Search"	#page=312&view=Fit
|			"9.7 The A* Heuristic"	#page=314&view=Fit
|			"9.8 Exercises"	#page=317&view=Fit
+		"Chapter 10 Dynamic Programming"	#page=321&view=Fit
+			"10.1 Caching vs. Computation"	#page=322&view=Fit
|				"10.1.1 Fibonacci Numbers by Recursion"	#page=322&view=Fit
|				"10.1.2 Fibonacci Numbers by Caching"	#page=323&view=Fit
|				"10.1.3 Fibonacci Numbers by Dynamic Programming"	#page=325&view=Fit
|				"10.1.4 Binomial Coefficients"	#page=326&view=Fit
+			"10.2 Approximate String Matching"	#page=328&view=Fit
|				"10.2.1 Edit Distance by Recursion"	#page=329&view=Fit
|				"10.2.2 Edit Distance by Dynamic Programming"	#page=331&view=Fit
|				"10.2.3 Reconstructing the Path"	#page=332&view=Fit
|				"10.2.4 Varieties of Edit Distance"	#page=335&view=Fit
|			"10.3 Longest Increasing Subsequence"	#page=338&view=Fit
|			"10.4 War Story: Text Compression for Bar Codes"	#page=340&view=Fit
|			"10.5 Unordered Partition or Subset Sum"	#page=343&view=Fit
|			"10.6 War Story: The Balance of Power"	#page=345&view=Fit
|			"10.7 The Ordered Partition Problem"	#page=347&view=Fit
|			"10.8 Parsing Context-Free Grammars"	#page=351&view=Fit
+			"10.9 Limitations of Dynamic Programming: TSP"	#page=353&view=Fit
|				"10.9.1 When is Dynamic Programming Correct?"	#page=354&view=Fit
|				"10.9.2 When is Dynamic Programming Efficient?"	#page=355&view=Fit
|			"10.10 War Story: What's Past is Prolog"	#page=356&view=Fit
|			"10.11 Exercises"	#page=359&view=Fit
+		"Chapter 11 NP-Completeness"	#page=368&view=Fit
+			"11.1 Problems and Reductions"	#page=368&view=Fit
|				"11.1.1 The Key Idea"	#page=369&view=Fit
|				"11.1.2 Decision Problems"	#page=370&view=Fit
+			"11.2 Reductions for Algorithms"	#page=371&view=Fit
|				"11.2.1 Closest Pair"	#page=371&view=Fit
|				"11.2.2 Longest Increasing Subsequence"	#page=372&view=Fit
|				"11.2.3 Least Common Multiple"	#page=372&view=Fit
|				"11.2.4 Convex Hull (*)"	#page=373&view=Fit
+			"11.3 Elementary Hardness Reductions"	#page=374&view=Fit
|				"11.3.1 Hamiltonian Cycle"	#page=375&view=Fit
|				"11.3.2 Independent Set and Vertex Cover"	#page=376&view=Fit
|				"11.3.3 Clique"	#page=379&view=Fit
+			"11.4 Satisfiability"	#page=380&view=Fit
|				"11.4.1 3-Satisfiability"	#page=380&view=Fit
+			"11.5 Creative Reductions from SAT"	#page=382&view=Fit
|				"11.5.1 Vertex Cover"	#page=382&view=Fit
|				"11.5.2 Integer Programming"	#page=384&view=Fit
|			"11.6 The Art of Proving Hardness"	#page=386&view=Fit
|			"11.7 War Story: Hard Against the Clock"	#page=388&view=Fit
|			"11.8 War Story: And Then I Failed"	#page=390&view=Fit
+			"11.9 P vs. NP"	#page=392&view=Fit
|				"11.9.1 Verification vs. Discovery"	#page=393&view=Fit
|				"11.9.2 The Classes P and NP"	#page=393&view=Fit
|				"11.9.3 Why Satisfiability is Hard"	#page=394&view=Fit
|				"11.9.4 NP-hard vs. NP-complete?"	#page=395&view=Fit
|			"11.10 Exercises"	#page=396&view=Fit
+		"Chapter 12 Dealing with Hard Problems"	#page=402&view=Fit
|			"12.1 Approximation Algorithms"	#page=402&view=Fit
+			"12.2 Approximating Vertex Cover"	#page=403&view=Fit
|				"12.2.1 A Randomized Vertex Cover Heuristic"	#page=405&view=Fit
+			"12.3 Euclidean TSP"	#page=406&view=Fit
|				"12.3.1 The Christofides Heuristic"	#page=407&view=Fit
+			"12.4 When Average is Good Enough"	#page=409&view=Fit
|				"12.4.1 Maximum k-SAT"	#page=409&view=Fit
|				"12.4.2 Maximum Acyclic Subgraph"	#page=410&view=Fit
|			"12.5 Set Cover"	#page=410&view=Fit
+			"12.6 Heuristic Search Methods"	#page=412&view=Fit
|				"12.6.1 Random Sampling"	#page=413&view=Fit
|				"12.6.2 Local Search"	#page=415&view=Fit
|				"12.6.3 Simulated Annealing"	#page=419&view=Fit
|				"12.6.4 Applications of Simulated Annealing"	#page=423&view=Fit
|			"12.7 War Story: Only it is Not a Radio"	#page=424&view=Fit
|			"12.8 War Story: Annealing Arrays"	#page=427&view=Fit
|			"12.9 Genetic Algorithms and Other Heuristics"	#page=430&view=Fit
+			"12.10 Quantum Computing"	#page=431&view=Fit
|				"12.10.1 Properties of \"Quantum\" Computers"	#page=432&view=Fit
|				"12.10.2 Grover's Algorithm for Database Search"	#page=433&view=Fit
|				"12.10.3 The Faster \"Fourier Transform\""	#page=435&view=Fit
|				"12.10.4 Shor's Algorithm for Integer Factorization"	#page=435&view=Fit
|				"12.10.5 Prospects for Quantum Computing"	#page=437&view=Fit
|			"12.11 Exercises"	#page=439&view=Fit
+		"Chapter 13 How to Design Algorithms"	#page=442&view=Fit
|			"13.1 Preparing for Tech Company Interviews"	#page=446&view=Fit
-	"Part II The Hitchhiker's Guide to Algorithms"	#page=448&view=Fit
|		"Chapter 14 A Catalog of Algorithmic Problems"	#page=449&view=Fit
+		"Chapter 15 Data Structures"	#page=451&view=Fit
|			"15.1 Dictionaries"	#page=452&view=Fit
|			"15.2 Priority Queues"	#page=457&view=Fit
|			"15.3 Suffix Trees and Arrays"	#page=460&view=Fit
|			"15.4 Graph Data Structures"	#page=464&view=Fit
|			"15.5 Set Data Structures"	#page=468&view=Fit
|			"15.6 Kd-Trees"	#page=472&view=Fit
+		"Chapter 16 Numerical Problems"	#page=476&view=Fit
|			"16.1 Solving Linear Equations"	#page=478&view=Fit
|			"16.2 Bandwidth Reduction"	#page=481&view=Fit
|			"16.3 Matrix Multiplication"	#page=483&view=Fit
|			"16.4 Determinants and Permanents"	#page=486&view=Fit
|			"16.5 Constrained/Unconstrained Optimization"	#page=489&view=Fit
|			"16.6 Linear Programming"	#page=493&view=Fit
|			"16.7 Random Number Generation"	#page=497&view=Fit
|			"16.8 Factoring and Primality Testing"	#page=501&view=Fit
|			"16.9 Arbitrary-Precision Arithmetic"	#page=504&view=Fit
|			"16.10 Knapsack Problem"	#page=508&view=Fit
|			"16.11 Discrete Fourier Transform"	#page=512&view=Fit
+		"Chapter 17 Combinatorial Problems"	#page=515&view=Fit
|			"17.1 Sorting"	#page=516&view=Fit
|			"17.2 Searching"	#page=520&view=Fit
|			"17.3 Median and Selection"	#page=524&view=Fit
|			"17.4 Generating Permutations"	#page=527&view=Fit
|			"17.5 Generating Subsets"	#page=531&view=Fit
|			"17.6 Generating Partitions"	#page=534&view=Fit
|			"17.7 Generating Graphs"	#page=538&view=Fit
|			"17.8 Calendrical Calculations"	#page=542&view=Fit
|			"17.9 Job Scheduling"	#page=544&view=Fit
|			"17.10 Satisfiability"	#page=547&view=Fit
+		"Chapter 18 Graph Problems: Polynomial Time"	#page=550&view=Fit
|			"18.1 Connected Components"	#page=551&view=Fit
|			"18.2 Topological Sorting"	#page=555&view=Fit
|			"18.3 Minimum Spanning Tree"	#page=558&view=Fit
|			"18.4 Shortest Path"	#page=563&view=Fit
|			"18.5 Transitive Closure and Reduction"	#page=568&view=Fit
|			"18.6 Matching"	#page=571&view=Fit
|			"18.7 Eulerian Cycle/Chinese Postman"	#page=574&view=Fit
|			"18.8 Edge and Vertex Connectivity"	#page=577&view=Fit
|			"18.9 Network Flow"	#page=580&view=Fit
|			"18.10 Drawing Graphs Nicely"	#page=583&view=Fit
|			"18.11 Drawing Trees"	#page=587&view=Fit
|			"18.12 Planarity Detection and Embedding"	#page=590&view=Fit
+		"Chapter 19 Graph Problems: NP-Hard"	#page=593&view=Fit
|			"19.1 Clique"	#page=594&view=Fit
|			"19.2 Independent Set"	#page=597&view=Fit
|			"19.3 Vertex Cover"	#page=599&view=Fit
|			"19.4 Traveling Salesman Problem"	#page=602&view=Fit
|			"19.5 Hamiltonian Cycle"	#page=606&view=Fit
|			"19.6 Graph Partition"	#page=609&view=Fit
|			"19.7 Vertex Coloring"	#page=612&view=Fit
|			"19.8 Edge Coloring"	#page=616&view=Fit
|			"19.9 Graph Isomorphism"	#page=618&view=Fit
|			"19.10 Steiner Tree"	#page=622&view=Fit
|			"19.11 Feedback Edge/Vertex Set"	#page=626&view=Fit
+		"Chapter 20 Computational Geometry"	#page=629&view=Fit
|			"20.1 Robust Geometric Primitives"	#page=630&view=Fit
|			"20.2 Convex Hull"	#page=634&view=Fit
|			"20.3 Triangulation"	#page=638&view=Fit
|			"20.4 Voronoi Diagrams"	#page=642&view=Fit
|			"20.5 Nearest-Neighbor Search"	#page=645&view=Fit
|			"20.6 Range Search"	#page=649&view=Fit
|			"20.7 Point Location"	#page=652&view=Fit
|			"20.8 Intersection Detection"	#page=656&view=Fit
|			"20.9 Bin Packing"	#page=660&view=Fit
|			"20.10 Medial-Axis Transform"	#page=663&view=Fit
|			"20.11 Polygon Partitioning"	#page=666&view=Fit
|			"20.12 Simplifying Polygons"	#page=669&view=Fit
|			"20.13 Shape Similarity"	#page=672&view=Fit
|			"20.14 Motion Planning"	#page=675&view=Fit
|			"20.15 Maintaining Line Arrangements"	#page=679&view=Fit
|			"20.16 Minkowski Sum"	#page=682&view=Fit
+		"Chapter 21 Set and String Problems"	#page=685&view=Fit
|			"21.1 Set Cover"	#page=686&view=Fit
|			"21.2 Set Packing"	#page=690&view=Fit
|			"21.3 String Matching"	#page=693&view=Fit
|			"21.4 Approximate String Matching"	#page=696&view=Fit
|			"21.5 Text Compression"	#page=701&view=Fit
|			"21.6 Cryptography"	#page=705&view=Fit
|			"21.7 Finite State Machine Minimization"	#page=710&view=Fit
|			"21.8 Longest Common Substring/Subsequence"	#page=714&view=Fit
|			"21.9 Shortest Common Superstring"	#page=717&view=Fit
+		"Chapter 22 Algorithmic Resources"	#page=720&view=Fit
+			"22.1 Algorithm Libraries"	#page=720&view=Fit
|				"22.1.1 LEDA"	#page=720&view=Fit
|				"22.1.2 CGAL"	#page=721&view=Fit
|				"22.1.3 Boost Graph Library"	#page=721&view=Fit
|				"22.1.4 Netlib"	#page=721&view=Fit
|				"22.1.5 Collected Algorithms of the ACM"	#page=722&view=Fit
|				"22.1.6 GitHub and SourceForge"	#page=722&view=Fit
|				"22.1.7 The Stanford GraphBase"	#page=722&view=Fit
|				"22.1.8 Combinatorica"	#page=723&view=Fit
|				"22.1.9 Programs from Books"	#page=723&view=Fit
|			"22.2 Data Sources"	#page=724&view=Fit
|			"22.3 Online Bibliographic Resources"	#page=725&view=Fit
|			"22.4 Professional Consulting Services"	#page=725&view=Fit
|	"Chapter 23 Bibliography"	#page=726&view=Fit
|	"Index"	#page=776&view=Fit>)
```
