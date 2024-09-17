---
tags:
  - dsa-model
---
# 4. Working with Big Oh
Created Sat May 4, 2024 at 6:43 PM

## Operations
### Addition
Sum of function equals the dominant one.

f + g → Θ(max(f, g))

The intuition is as follows. At least half the bulk of f (n) + g(n) must come from the larger value. The dominant function will, by definition, provide the larger value as n → ∞. Thus, dropping the smaller function from consideration reduces the value by at most a factor of 1/2, which is just a multiplicative constant.


### Multiplication
No shortcut, the output will have both functions.

- O(f) · O(g) → O(f · g) 
- Ω(f) · Ω(g) → Ω(f · g) 
- Θ(f) · Θ(g) → Θ(f · g)

## Properties of asymptotic notations
- Transitivity: f(n) = Θ(g(n)) and g(n) = Θ(h(n)) ⇒ f(n) = Θ(h(n)). Valid for O and Ω as well.
- Reflexivity: f(n) = Θ(f(n)). Valid for O and Ω.
- Symmetry: f(n) = Θ(g(n)) if and only if g(n) = Θ(f(n)).
	- Transpose symmetry: f(n) = O(g(n)) if and only if g(n) = Ω(f(n)).

