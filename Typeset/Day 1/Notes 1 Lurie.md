Motivation: think about classifying quadratic forms, we'd like to know when two are equal -- i.e., when one can be obtained from the other by a linear change of variables.

Examples:
1. $x^2+y^2$
2. $x^2-y^2$
3. $-x^2-y^2$

Note that these are all equivalent over $\CC$, under the map $x \mapsto ix$ which sends $x^2\to-x^2$. But these are not equivalent over $\RR$, since (1) is positive-definite, (2) is indefinite, and (3) is negative definite.

We can similary have forms equivalent over $\RR$ but not over $\ZZ$, e.g. by considering $x^2 + 3y^2$. This is equivalent to (1) over $\RR$, since we have $\sqrt 3$, but not over $\ZZ$ -- this can be seen by reducing mod 3.

So we have two methods
- Look over $\RR$, diagonalize, take signature
- Reduce mod $p$ for various $p$.

Are these all you need?

Definition: $q,q'$ are in the same genus if $\forall n, q \equiv q' \mod n$.

Remark: there are only finitely many forms in each genus, and there is a formula to count them: the Smith-Minkowski-Segal formula. 

Definition: For a commutative ring $R$, we define the orthogonal group over $R$ to be $O_q(R) = \theset{M \in \GL(n, R) \suchthat $