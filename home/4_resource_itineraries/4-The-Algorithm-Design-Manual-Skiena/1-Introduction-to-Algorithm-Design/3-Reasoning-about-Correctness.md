---
tags:
  - dsa-model
---
# 3. Reasoning about Correctness
Created Wed May 1, 2024 at 5:44 PM

Demonstrates:
- Proof is the primary tool to distinguish between correct and incorrect algorithms
- Proofs are difficult to do correctly, and can be misleading if done wrong. He'll skip them in his book.
- Correct algorithms require efforts to show both (AND)
	- correctness
	- not incorrectness

## Problems and properties
Problem specification consists of two parts:
1. Set of allowed input instances
2. The required property of the algorithm's output

*It is impossible to prove the correctness of an algorithm for a fuzzily- stated problem. Put another way, ask the wrong question and you will get the wrong answer.*

Narrowing input: *An important and honorable technique in algorithm de- sign is to narrow the set of allowable instances until there is a correct and efficient algorithm. For example, we can restrict a graph problem from general graphs down to trees, or a geometric problem from two dimensions down to one.*

Traps in output spec:
1. ill defined question
2. compounding goals - there's more than one goals, instead of a single goal.

## Expressing algorithms
There are 3 languages:
1. Natural language - English. Not precise.
2. Pseudocode - made up language (a happy medium)
3. Programming language - C++/Java etc. Too precise to work with.

Do not dress up an ill-defined idea just to make it look formal. Clarity should be the goal when expressing algorithms.

The idea: *The heart of any algorithm is an idea. If your idea is not clearly revealed when you express an algorithm, then you are using too low-level a notation to describe it.* Note-to-self: this is so good to know. Without a central idea - an algorithm either a kludge or a coincidence, in any case not reusable or readable.


## Demonstrating in-correctness
Counter-examples (i.e. a valid input instance that produces the wrong output, given an algorithm) are a rational and quick way to disprove correctness of algorithms.

A good counter example has two properties:
1. Verifiable - it can be run in the claimed algorithm and produce output.
2. Simplicity - good counterexamples have unnecessary details stripped away. Reason is you must be able to hold it in your head, to be able to even consider it.


Hunting for counterexamples is a skill worth developing.

Some counter-example generation techniques:
1. Think small - don't create big messy counter-examples. Keep it small, making it easy to verify and reason about.
2. Think exhaustively - check true/false, -1/0/+1, left/right, up/down, i.e. possibility sets of actions/situations. And create a counter example from these attributes.
3. Hunt for weakness - when an algorithm presses for an assumption (like a greedy algorithm trying to maximize some criteria at every iteration), think about why and when this become wrong.
4. Go for a tie - if the problem is a set of things, try to make them all the same. Greedy algorithms usually break this way, since they lose the comparison power that helped them steer the problem. *Essentially, try the distinct/duplicate possibility*.
5. Seek extremes - many counter examples are instances built of two extreme parts, like big+small, left+right, few+many, near+far. Example: TSP answer for a graph that is actually two very condensed subgraphs connected by a single edge, would yield the answer 2 \* D.