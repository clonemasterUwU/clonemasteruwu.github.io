---
title: "Putnam & Beyond Problem 46"
date: 2023-03-03
draft: false
---

### Problem Statement

Let $x_1,x_2,...,x_m$ be real numbers such that the set

$$ A = \lbrace \sum_{i=1}^m cos(n\pi x_i) | n \in \mathbb{N}  \rbrace $$

is finite. Prove that all the $x_i$ are rational numbers.

### Idea

(borrow from the proof that $\lbrace n\alpha \rbrace = n\alpha - \lfloor n\alpha \rfloor$ is dense on $\[0,1\]$)

Let $k$ be an integer. Consider the tuple 

$$ (\lbrace \dfrac{t x_1}{2} \rbrace,\lbrace \dfrac{t x_2}{2} \rbrace,...,\lbrace \dfrac{t x_m}{2} \rbrace)$$

Each fractional part $\lbrace \dfrac{t x_i}{2} \rbrace$ belongs to exactly one interval of the set 

$$ K = \lbrace \lbrack 0, \dfrac{1}{k}\rparen, \lbrack \dfrac{1}{k}, \dfrac{2}{k}\rparen, ... , \lbrack \dfrac{k-1}{k}, 1\rparen \rbrace $$

By pigeonhole principle, dividing infinite tuples of the above to an finite set
of $K \times K \times...\times K$ ($m$ times) means there exists 2 integers $p < q$ such that p and q falls into the same hypercube, that is their distance in each dimesion is less than $\frac{1}{k}$:

$$ \\| \\{ \dfrac{qx_i}{2}\\} -\\{ \dfrac{px_i}{2}\\}\\| < \dfrac{1}{k}$$
$$ \Leftrightarrow 0 \leq \lbrace (q-p)\dfrac{x_i}{2} \rbrace < \dfrac{1}{k}\text{ or } \dfrac{k-1}{k} \leq \lbrace (q-p)\dfrac{x_i}{2} \rbrace < 1$$

This implies, by choosing arbitarily large $k$, there exists an integer $t \geq 1$ such that $t \pi x_i$ gets arbitarily close to some $2 m \pi | m \in \mathbb{Z}$ points for every $i$. This means $cos(t\pi x_i)$ gets arbitarily close to 1 for every $i$ as well.

As the set A is finite, then the value $n$ (which is achieved when $cos(t\pi x_i) = 1$ for every i) must be in A.

Then the conclusion that all $x_i$ are rational numbers comes naturally.

### Aftermath

This proof differs from one from the book that utilize the Chebyshev polynomial's recurrence. In general,this method can be extended for any continous, periodic function as well.