# 2. Big Oh notation
Created Sat May 4, 2024 at 5:54 PM


> [!NOTE] Take-Home Lesson
> The Big Oh notation and worst-case analysis are tools that greatly simplify our ability to compare the efficiency of algorithms.

## Why Big-Oh
The worst, best or average case, are mathematical functions over the input size.
However, it's difficult to work precisely with these functions, because they tend to:
1. Have too many bumps. Explain by example - a binary search works a bit faster is the size of the array is n=2<sup>k</sup>-1 (where k is an integer), because array partitions work out nicely. This detail is not very important, but it does hint that the mathematical function may be too complicated, with little bumps up and down.
2. Difficult to specify precisely - coming up with a complicated worst case like
	T(n) = 12754n<sup>2</sup> + 4353n + 834lg<sub>2</sub>n + 13546
	would almost do away gains we had with simplicity of the RAM model, and we'd actually be doing the same work as if the program was machine dependent (since we would consider so much detail). But we can observe that algorithm grows "quadratically with n". Other parts are cumbersome and not helpful.

This means that it's much easier to talk in terms of upper and lower bounds of total steps taken (i.e. of a mathematical function).

![](../../../../assets/2-Big-Oh-notation-image-1-23f8dd9b.png)
## 3 notations
There are 3 variations of the notation:
- Oh (maid big): f(n) = O(g(n)) means c · g(n) is an upper bound on f(n). Thus, there exists some constant c such that f (n) ≤ c · g(n) for every large enough n (that is, for all n ≥ n<sub>0</sub>, for some constant n<sub>0</sub>).
- Sigma (maid small): f(n) = Ω(g(n)) means c·g(n) is a lower bound on f(n). Thus, there exists some constant c such that f(n) ≥ c · g(n) for all n ≥ n<sub>0</sub>.
- Theta (maid middle line, i.e. between): f(n) = Θ(g(n)) means c<sub>1</sub> · g(n) is an upper bound on f(n) and c<sub>2</sub> · g(n) is a lower bound on f(n), for all n ≥ n<sub>0</sub>. Thus, there exist constants c<sub>1</sub> and c<sub>2</sub> such that f(n) ≤ c<sub>1</sub> ·g(n) and f(n) ≥ c<sub>2</sub> ·g(n) for all n ≥ n<sub>0</sub>. This means that g(n) provides a nice, tight bound on f(n).

Note:
- We are not concerned with small values of n. We are only concerned with large values, the smallest of them being n<sub>0</sub>.
- Even though bounds can be anything after a given value, we should try to have tight bounds.

![](../../../../assets/2-Big-Oh-notation-image-2-23f8dd9b.png)