---
title: "Problem 9 CMU Putnam Training 2022 Combinatoric"
date: 2023-06-11
draft: false
---

### Problem Statement

Given a graph G with each vertex assigned with a binary state on/off.

Each move consists of choosing a vertex, then change the state of itself and all of its neighbor(s).

Prove that from the all-off starting position, it is possible to reach the all-on position.

### Idea

Let $n$ be the number of vertex in $G$.

Let $A$ be the adjacent matrix of $G$:

$$
A_{ij} = \begin{cases}
   1 &\text{if } i=j \text{ or }i\text{ and }j \text{ are adjacent in G}  \\\\
   0 &\text{otherwise }
\end{cases}
$$

Another observation is that performing 2 moves on the same vertex has net zero effect regardless of other moves.

So the problem boils down to whether there exists $v \in \mathbb{Z_2}^n$ such that:

$$Av = \overrightarrow{1} $$

We can prove by induction on $n$. The base case is trivial. Assume that it's true for $n-1$.

Let $V$ be the row span of $A$. Assume the contradiction that $\overrightarrow{1} \not \in V$.

Denote $\bar{i}$ be the vector that has 0 on row $i$ and 1 on the others.

Using the induction hypothesis on first minor matrix $M_{i,i}$ of A we get:

$$\bar{i} \in V$$

If $n$ is even then $\overrightarrow{1} = \sum_{i} \bar{i} \in V$. So we only continue with the assumption that $n$ is odd.

Any proper subset $S$ of $\lbrace \bar{i} \rbrace$ is linear independent. Let $k = \sum_{i \in S} \bar{i}$ then either $k_{i \in S} = 1$ or $k_{i \not \in S} = 1$.

But $\overrightarrow{1} \not \in V$ so $\lvert V \rvert = 2^{n-1}$ or the row vector of $A$ forms a minimal dependent set.

$$\sum_{i} A_i = \overrightarrow{0} $$

But this is a contradiction as the number of 1 entry in $A$ is always odd if $n$ is odd ($A$ is symmetric and reflexive).

### Aftermath

Later I found out there's [a generalized result with much more elegant proof](https://math.stackexchange.com/questions/1748169/the-diagonal-of-a-symmetric-matrix-a-in-m-n-mathbbz-2):

For any symmetric matrix $A$, the diagonal vector is always in the row span of $A$.

The combinatoric proof of the problem uses the corrolary of the 10th problem: 

Any graph $G$ can be partitioned into 2 possibly empty subgraphs, such that the degree of each vertex in the induce graph of one is odd while the other is even.


