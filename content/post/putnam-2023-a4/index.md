---
title: "Putnam 2023 A4"
date: 2023-12-05T18:51:33-05:00
draft: false
---

### Problem statement

Prove that any $\overrightarrow{v} \in \mathbb{R}^3$ can be approximated to arbitrary precision by an integral linear combination of unit vectors from the origin to the vertices of a regular icosahedron.



### Idea

{{<figure align="center" width="350" src="icosahedron.png" caption="icosahedron with denotation">}}

1. $S$ = Integral linear combination of $\\{O'A, O'B, O'C, O'D, O'E\\}$ is dense on $\mathbb{R}^2$

+ $\\{ \\{n\alpha\\} = n\alpha - \lfloor n\alpha \rfloor \\}, n\in\mathbb{N}$ is dense on $\[0,1\)$

+ $\\{ m\alpha + n\beta \\}, m,n \in \mathbb{N},\dfrac{a}{b}\in \mathbb{R}\setminus\mathbb{Q}$ is dense on $\mathbb{R}$

+ $\overrightarrow{BE}  = \overrightarrow{O'E} - \overrightarrow{O'B} \in S$, $\overrightarrow{CD} \in S$, $\\|\dfrac{BE}{CD} \\| \in \mathbb{R}\setminus\mathbb{Q}$ 

+ $2\overrightarrow{O'G} = \overrightarrow{O'B} + \overrightarrow{O'E} \in S$, $2\overrightarrow{O'H} \in S$, $\\|\dfrac{O'G}{O'H} \\| \in \mathbb{R}\setminus\mathbb{Q}$ 
{{<figure align="center" width="350" src="pentagon.png" caption="pentagon with denotation">}}

2. $T$ = Integral linear combination of $\\{OA,OB,OC,OD,OE,OF\\}$ is dense on $\mathbb{R}^3$

+ $\overrightarrow{OF} \in T$, $5\overrightarrow{OO'} = \overrightarrow{OA} + \overrightarrow{OB} + \overrightarrow{OC} + \overrightarrow{OD} + \overrightarrow{OE} \in T$, $\\|\dfrac{OO'}{OF} \\| \in \mathbb{R}\setminus\mathbb{Q}$ 

+ So you can approximate the last 2 coordinates by using the "pentagon" unit vectors, then combine it with the first axis to make the integral linear system dense on $\mathbb{R}^3$.

### Aftermath

2023 is my "graduation" Putnam. I only returned to competitive math last year thanks to Dr. Dan 's great patience (The thrill is still there like the first time.) I don't prepare seriously enough for this year (due to the regional ICPC being pushed into fall, this deserves a blog post itself), so my performance is somewhat close to my expectation. 

(More things will go into this post once the result comes out)
