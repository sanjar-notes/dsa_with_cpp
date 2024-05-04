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

## Common math
1. AP: 1 + 2 + 3 + ... + n = n \* (n+1) / 2
2. GP: 1 + x + x<sup>2</sup> + x<sup>3</sup> + ... + x<sup>n-1</sup> = (x<sup>n</sup> - 1)/(x-1)
3. HP: 1 + 1/2 + 1/3 + 1/4 + ... + 1/n ~= log(n)
4. log1 + log2 + log3 + ... + log(n) ~= nlog(n)
5. 1 + 2<sup>p</sup> + 3<sup>p</sup> + ... + n<sup>p</sup> ~= n<sup>p+1</sup>/(p+1)
