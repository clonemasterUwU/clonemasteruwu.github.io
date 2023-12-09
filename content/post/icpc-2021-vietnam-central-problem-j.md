---
title: "ICPC 2021 Vietnam Central Problem J"
date: 2022-03-27
draft: false
---

### Problem Statement

Given `n` integers `a[1..n]`. 

Calculate sum of t-th powers, $\sum_{i=1}^{n}a_i^{t}$, modulo 998244353 for t in `[1..k]`

**Constraint:** `n ~ 1e5, k ~ 1e5`

### Hint

According to [Wikipedia](https://en.wikipedia.org/wiki/Newton%27s_identities), we have the generating function for sum of power:

$$\sum_{k=1}^{\infty} (-1)^{k-1}p_k \dfrac{t^k}{k} = \ln (1+e_1 t + e_2 t^2 + e_3 t^3 + ...)$$

where $p_k$ is the t-th power sum:

$$ p_k = \sum_{i=1}^n x_i^k $$

and $e_k$ is the elementary symmetric polynomial (the sum of all distinct products of k distinct variables):

$$ e_0 = 1 $$
$$ e_1 = x_1 + x_2 + ... + x_n $$
$$ e_2 = \sum_{1\leq i < j \leq n} x_i x_j $$
$$ ... $$
$$ e_n = x_1 x_2 ... x_n $$
$$ e_k = 0, \forall k > n $$

Notice that the polynomial inside the log is similar to the characteristic polynomial of $x_i$:
$$\prod_{i=1}^n (x-x_i) = 1 x^n - e_1 x^{n-1} + e_2 x ^ {n-2} - ... + (-1)^{n-1} e_{n-1} x + (-1)^n e_n$$

And we can obtain the characteristic polynomial with FFT (NTT) and small-to-large merging in $O(n \log ^ 2 n)$.

Now we take the derivative of the generating function w.r.t. t:

$$ \sum_{k=1}^{\infty} (-1)^{k-1} p_k t^{k-1} = \dfrac{e_1 + 2e_2 t + 3e_3 t^2 + ...}{1 + e_1 t + e_2 t^2 + e_3 t^3 + ...}$$

The only missing part left is [how to divide two polynomials in poly-log ($n \log ^ 2 n$) time](https://web.archive.org/web/20170830041003/http://www.diag.uniroma1.it/sankowski/lecture4.pdf).

### Impl

DIY