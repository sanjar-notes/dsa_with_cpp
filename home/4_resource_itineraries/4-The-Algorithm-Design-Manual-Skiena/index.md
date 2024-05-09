# 4. The Algorithm Design Manual Skiena
Created Thu May 9, 2024 at 7:30 AM

## Book TOC
```php
-	"Preface"	#page=6&view=Fit
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
|			"1.4 Induction and Recursion"	#page=32&view=Fit
+			"1.5 Modeling the Problem"	#page=34&view=Fit
|			"1.6 Proof by Contradiction"	#page=38&view=Fit
|			"1.7 About the War Stories"	#page=39&view=Fit
|			"1.8 War Story: Psychic Modeling"	#page=39&view=Fit
|			"1.9 Estimation"	#page=42&view=Fit
|			"1.10 Exercises"	#page=44&view=Fit
+		"Chapter 2 Algorithm Analysis"	#page=48&view=Fit
+			"2.1 The RAM Model of Computation"	#page=48&view=Fit
|			"2.2 The Big Oh Notation"	#page=51&view=Fit
+			"2.3 Growth Rates and Dominance Relations"	#page=54&view=Fit
+			"2.4 Working with the Big Oh"	#page=56&view=Fit
+			"2.5 Reasoning about E\x0Eciency"	#page=58&view=Fit
|			"2.6 Summations"	#page=63&view=Fit
+			"2.7 Logarithms and Their Applications"	#page=65&view=Fit
|			"2.8 Properties of Logarithms"	#page=69&view=Fit
|			"2.9 War Story: Mystery of the Pyramids"	#page=71&view=Fit
+			"2.10 Advanced Analysis (*)"	#page=74&view=Fit
|			"2.11 Exercises"	#page=76&view=Fit
+		"Chapter 3 Data Structures"	#page=85&view=Fit
+			"3.1 Contiguous vs. Linked Data Structures"	#page=85&view=Fit
|			"3.2 Containers: Stacks and Queues"	#page=91&view=Fit
|			"3.3 Dictionaries"	#page=92&view=Fit
+			"3.4 Binary Search Trees"	#page=97&view=Fit
|			"3.5 Priority Queues"	#page=103&view=Fit
|			"3.6 War Story: Stripping Triangulations"	#page=105&view=Fit
+			"3.7 Hashing"	#page=109&view=Fit
|			"3.8 Specialized Data Structures"	#page=114&view=Fit
|			"3.9 War Story: String 'em Up"	#page=114&view=Fit
|			"3.10 Exercises"	#page=119&view=Fit
+		"Chapter 4 Sorting"	#page=125&view=Fit
|			"4.1 Applications of Sorting"	#page=125&view=Fit
|			"4.2 Pragmatics of Sorting"	#page=129&view=Fit
+			"4.3 Heapsort: Fast Sorting via Data Structures"	#page=131&view=Fit
|			"4.4 War Story: Give me a Ticket on an Airplane"	#page=141&view=Fit
|			"4.5 Mergesort: Sorting by Divide and Conquer"	#page=143&view=Fit
+			"4.6 Quicksort: Sorting by Randomization"	#page=146&view=Fit
+			"4.7 Distribution Sort: Sorting via Bucketing"	#page=152&view=Fit
|			"4.8 War Story: Skiena for the Defense"	#page=154&view=Fit
|			"4.9 Exercises"	#page=156&view=Fit
+		"Chapter 5 Divide and Conquer"	#page=163&view=Fit
+			"5.1 Binary Search and Related Algorithms"	#page=164&view=Fit
|			"5.2 War Story: Finding the Bug in the Bug"	#page=166&view=Fit
+			"5.3 Recurrence Relations"	#page=168&view=Fit
|			"5.4 Solving Divide-and-Conquer Recurrences"	#page=170&view=Fit
|			"5.5 Fast Multiplication"	#page=171&view=Fit
|			"5.6 Largest Subrange and Closest Pair"	#page=173&view=Fit
+			"5.7 Parallel Algorithms"	#page=175&view=Fit
|			"5.8 War Story: Going Nowhere Fast"	#page=177&view=Fit
+			"5.9 Convolution (*)"	#page=178&view=Fit
|			"5.10 Exercises"	#page=182&view=Fit
+		"Chapter 6 Hashing and Randomized Algorithms"	#page=186&view=Fit
+			"6.1 Probability Review"	#page=187&view=Fit
+			"6.2 Understanding Balls and Bins"	#page=194&view=Fit
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
|			"7.2 Data Structures for Graphs"	#page=217&view=Fit
|			"7.3 War Story: I was a Victim of Moore's Law"	#page=221&view=Fit
|			"7.4 War Story: Getting the Graph"	#page=224&view=Fit
|			"7.5 Traversing a Graph"	#page=226&view=Fit
+			"7.6 Breadth-First Search"	#page=227&view=Fit
+			"7.7 Applications of Breadth-First Search"	#page=231&view=Fit
|			"7.8 Depth-First Search"	#page=235&view=Fit
+			"7.9 Applications of Depth-First Search"	#page=238&view=Fit
+			"7.10 Depth-First Search on Directed Graphs"	#page=244&view=Fit
|			"7.11 Exercises"	#page=249&view=Fit
+		"Chapter 8 Weighted Graph Algorithms"	#page=257&view=Fit
+			"8.1 Minimum Spanning Trees"	#page=258&view=Fit
|			"8.2 War Story: Nothing but Nets"	#page=268&view=Fit
+			"8.3 Shortest Paths"	#page=271&view=Fit
|			"8.4 War Story: Dialing for Documents"	#page=278&view=Fit
+			"8.5 Network Flows and Bipartite Matching"	#page=281&view=Fit
|			"8.6 Randomized Min-Cut"	#page=286&view=Fit
|			"8.7 Design Graphs, Not Algorithms"	#page=288&view=Fit
|			"8.8 Exercises"	#page=290&view=Fit
+		"Chapter 9 Combinatorial Search"	#page=295&view=Fit
|			"9.1 Backtracking"	#page=295&view=Fit
+			"9.2 Examples of Backtracking"	#page=298&view=Fit
|			"9.3 Search Pruning"	#page=303&view=Fit
|			"9.4 Sudoku"	#page=304&view=Fit
|			"9.5 War Story: Covering Chessboards"	#page=309&view=Fit
|			"9.6 Best-First Search"	#page=312&view=Fit
|			"9.7 The A* Heuristic"	#page=314&view=Fit
|			"9.8 Exercises"	#page=317&view=Fit
+		"Chapter 10 Dynamic Programming"	#page=321&view=Fit
+			"10.1 Caching vs. Computation"	#page=322&view=Fit
+			"10.2 Approximate String Matching"	#page=328&view=Fit
|			"10.3 Longest Increasing Subsequence"	#page=338&view=Fit
|			"10.4 War Story: Text Compression for Bar Codes"	#page=340&view=Fit
|			"10.5 Unordered Partition or Subset Sum"	#page=343&view=Fit
|			"10.6 War Story: The Balance of Power"	#page=345&view=Fit
|			"10.7 The Ordered Partition Problem"	#page=347&view=Fit
|			"10.8 Parsing Context-Free Grammars"	#page=351&view=Fit
+			"10.9 Limitations of Dynamic Programming: TSP"	#page=353&view=Fit
|			"10.10 War Story: What's Past is Prolog"	#page=356&view=Fit
|			"10.11 Exercises"	#page=359&view=Fit
+		"Chapter 11 NP-Completeness"	#page=368&view=Fit
+			"11.1 Problems and Reductions"	#page=368&view=Fit
+			"11.2 Reductions for Algorithms"	#page=371&view=Fit
+			"11.3 Elementary Hardness Reductions"	#page=374&view=Fit
+			"11.4 Satisfiability"	#page=380&view=Fit
+			"11.5 Creative Reductions from SAT"	#page=382&view=Fit
|			"11.6 The Art of Proving Hardness"	#page=386&view=Fit
|			"11.7 War Story: Hard Against the Clock"	#page=388&view=Fit
|			"11.8 War Story: And Then I Failed"	#page=390&view=Fit
+			"11.9 P vs. NP"	#page=392&view=Fit
|			"11.10 Exercises"	#page=396&view=Fit
+		"Chapter 12 Dealing with Hard Problems"	#page=402&view=Fit
|			"12.1 Approximation Algorithms"	#page=402&view=Fit
+			"12.2 Approximating Vertex Cover"	#page=403&view=Fit
+			"12.3 Euclidean TSP"	#page=406&view=Fit
+			"12.4 When Average is Good Enough"	#page=409&view=Fit
|			"12.5 Set Cover"	#page=410&view=Fit
+			"12.6 Heuristic Search Methods"	#page=412&view=Fit
|			"12.7 War Story: Only it is Not a Radio"	#page=424&view=Fit
|			"12.8 War Story: Annealing Arrays"	#page=427&view=Fit
|			"12.9 Genetic Algorithms and Other Heuristics"	#page=430&view=Fit
+			"12.10 Quantum Computing"	#page=431&view=Fit
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
|			"22.2 Data Sources"	#page=724&view=Fit
|			"22.3 Online Bibliographic Resources"	#page=725&view=Fit
|			"22.4 Professional Consulting Services"	#page=725&view=Fit
|	"Chapter 23 Bibliography"	#page=726&view=Fit
|	"Index"	#page=776&view=Fit
```
