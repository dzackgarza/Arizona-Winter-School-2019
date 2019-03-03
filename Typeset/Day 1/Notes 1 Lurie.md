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

Definition: For a commutative ring $R$, we define the orthogonal group over $R$ to be $O_q(R) = \theset{M \in \GL(n, R) \suchthat q\circ M = q}$; i.e. the square matrices that preserve the quadratic form $q$.

Note that $O_q(\RR)$ is the usual orthogonal group, which is a compact Lie group.

Definition: Suppose $q$ has genus $g$, then we define the mass of $q$ as 
$$
\mathrm{Mass}(q) = \sum_{q' \suchthat \mathrm{genus} (q') = g} \frac{1}{O_{q'}(\ZZ)}
$$

which counts the number of forms of the same genus as $q$.

Definition: $q$ is unimodular if $q$ is nondegenerate if for all $n$, it it nondegenerate mod $n$.

For two forms in the same genus, $q,q'$, then $q$ is unimodular iff $q'$ is, but the converse is actually true as well -- for a fixed number of variables, any two unimodular forms are in the same genus.

Supposing $q$ is unimodular, we can write the mass formula
$$
\mathrm{Mass}(q) = \sum_{q' \text{unimodular}} \frac{1}{O_{q'}(\ZZ)}
= \zeta(\frac n 2)\frac{\zeta(2)\zeta(4)\cdots\zeta(n-2)}{\mathrm{vol}~S^1 \mathrm{vol} ~S^2 \cdots \mathrm{vol}~S^{n-1}}
$$

where the denominators are the volumes of spheres, and the numerator contains certain values of the Riemann-zeta function.

If, for examplen $n=8$, we obtain
$$
\frac 1 {2^{14}3^55^2 7}
$$

This is actually the order of the Weil group of the exceptional Lie group $E_8$, i.e. $\abs{W(E_8)}$. This appears as the symmetries of a certain quadratic over $\ZZ$ -- namely the form associated to the root lattice of $E_8$. So we have one form that gives exactly the RHS of the mass formula, which tells us that there can only be one term on the LHS, and thus there is a unique unimodular form in 8 variables.

You can get other information from this formula -- for example, if the RHS is large, note that the LHS contains summands all of which are less than 1, so there have to be many (many!) terms.