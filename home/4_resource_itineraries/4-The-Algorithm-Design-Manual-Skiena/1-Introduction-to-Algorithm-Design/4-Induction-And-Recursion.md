---
tags:
  - dsa-model
  - recursion
---
# 4. Induction And Recursion
Created Wed May 1, 2024 at 5:41 PM

To Skiena, on first look, both induction as a proof technique, and recursion as a programming technique seemed ridiculous.

 *I’ve heard it said that a computer scientist is a mathematician who only knows how to prove things by induction. This is partially true because computer scientists are lousy at proving things, but primarily because so many of the algorithms we study are either recursive or incremental.* 🤣


Be suspicious of inductive proofs. Check this:
1. Next-step candidate is not unique. Due to duplicates/etc possibly.
2. Cavalier extension claims - adding one extra item to a problem might cause the optimal solution to change. Boldly ignoring such difficulties can lead to very convincing inductive proofs of incorrect algorithms.

Extended induction (assuming all previous instances are good, given parameter point i) is a lightweight thing (mathematically, compared to usual induction), but is sometime necessary in proofs.

*Mathematical induction is usually the right way to verify the correctness of a recursive or incremental insertion algorithm.*