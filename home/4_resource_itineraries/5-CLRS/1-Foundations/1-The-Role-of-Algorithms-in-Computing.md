# 1. The Role of Algorithms in Computing
Created Tue Aug 13, 2024 at 12:45 AM

## Abstract
- Naive solution - even if time and memory were abundant, we'd still need *some* solution to solve problems. Coming up with naive solutions isn't that naive, since we need standardized algorithms.
- Time - computers are fast, but not infinitely fast. We need fast algorithms, since we face situations that have a short opportunity. Like stock markets, medical tests, real-time operating systems.
- Memory - space may be cheap, but it isn't free.

## Practical stuff
- DNA sequencing for solving biological problems. We have 100,000 genes and have 3 billion chemical base pairs. We need to deal with scale.
- Internet - clever algorithms help the internet be fast and performant.
- Online commerce - all electronic commerce, including banking needs privacy and authentication. Cryptographic systems need to be quantified based on hardness of problems.
- Manufacturing and business - companies need to allocate scarce resources in the most beneficial way. An oil company might need to know which land to lease. A political candidate may need to know where to spend campaign money to maximize chances of winning (DP). An airline needs to assign crews to flights so total compensation is minimized (DP/Greedy).
- Map - we need to know the shortest distance from A to B (Dijsktra). We need to build a road network connecting cities, but wish to minimize total amount of road we build (MST).
- Supply chain ordering - a product has n parts in its design, some depend on others (i.e. they fit-into/cover others). A topological sort will help knowing in what order to buy the parts, so idle time is minimized.

## Algorithms as technology
Technology brings non-trivial change to society, materially and otherwise (things become feasible, law changes).

Many apps today (that are simple from an app developer perspective) are only possible due to our understanding of algorithms:
1. Routing in networks relies heavily on algorithms.
2. GUI concepts like React, depend on fast tree diffing.
3. Compilers need to parse code - which needs dynamic programming to work. Trees are a fundamental data structure used here.
4. Bundlers - many web apps need a tool called the bundler, that packs many files into a single one. Dead-code-removal (i.e. code that isn't imported anywhere) and circular dependency checking (if there's an import cycle) are important features.
5. Static analysis - linters in IDEs need to maintain a tree of tokens, so automatic refactoring and syntax can be done.
6. Autocompletion - many text boxes need autocompletion, from the IDE to phonebook to very dynamic ones like search engine completions.

With modern computing technology, you can accomplish some tasks without knowing much about algorithms, but with a good background in algorithms, you can do much, much more.

Any business that wishes to thrive needs to be efficient in their processes and resource usage (like Uber). Algorithms are key.