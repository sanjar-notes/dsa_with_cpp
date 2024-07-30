# 3. Fast multiplication
Created Mon Jul 29, 2024 at 11:59 PM

## Karatsuba's algorithm
We want to multiply two numbers, and we're using digit by digit (and have a times table). The complexity would be O(n<sup>2</sup>).
![](../../../../assets/3-Fast-multiplication-image-1-c8517a43.png)

![](../../../../assets/3-Fast-multiplication-image-2-c8517a43.png)

Complexity is O(n<sup>1.58</sup>)

Note:
- Strassens algo for nxn matrix multiplication is similar. Theoretical O(n<sup>2.81</sup>), current best O(n<sup>2.37</sup>)