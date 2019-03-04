# $\AA^1$ Enumerative Geometry

Enumerative geometry, counts algebro-geometric objects, and in order to actually obtain an invariant number at the end of the day one uses an algebraically closed field $k$ or $\CC$. This is essentially because the conditions imposed are polynomial, and polynomials of degree $n$ over a closed field always have $n$ roots.

The goal here is to record information about the fields of definition. However, since we may no longer have invariant numbers as solutions to polynomial equations, we replace this with a notion of *weights* to get an "invariance of bilinear form" principle instead. Over characteristic not 2, we can use quadratic forms, which ties to Lurie's first talk.

# Example: Lines on a Smooth Cubic Surface
> Joint work with Jesse Kass

A **cubic surface** $X$ consists of the $\CC$ solutions to a polynomial in three variables, i.e. 
$$
X = \theset{(x,y,z) \in \CC^3 \suchthat f(x,y,z) = 0},
$$

where $f$ is degree 3. In general, we want to compactify, so we view $X \injects \CP^3$ as
$$
\CP^3 = \theset{\vector x = [w,x,y,z]\neq \vector 0 \suchthat \forall \lambda \in \CC^\times,~\vector x = \lambda \vector x}
$$

and so 
$$
X = \theset{[w,x,y,z] \in \CP^3 \suchthat f(w,x,y,z) = 0}
$$
where $f$ is homogeneous.

The surface $X$ is **smooth** if the underlying points form a manifold, or equivalently if the partials don't simultaneously vanish.

**Theorem (Salmon Cayley 1849):**
If $X$ is a smooth cubic surface, then $X$ contains exactly 27 lines.

Example: The Fermat cubic $f(w,x,y,z) = w^3 + x^3 + y^3 + z^3$.

We can find one line, given by 
$$
L = \theset{[s,-s,t,-t] \suchthat s,t \in \CP^1},
$$

and in fact this works for any $\lambda, \omega$ such that $\lambda^3 = \omega^3 = -1$, yielding
$$
L' = \theset{[s,\lambda s,t,\omega t] \suchthat s,t \in \CP^1}.
$$

We can also permute $s,t$ around to get more lines, and by counting this yields 27 distinct possibilities. (3 choices for $\lambda$, 3 choices for $\omega$, and $\frac 1 2 {4\choose 2}$ ways to pair them with the $s,t$ in the original $L$.

> There is a proof in the notes that these are the only lines, which is relatively elementary.

# Modern Proof
We'll use characteristic classes, which we'll later replace by an $\AA^1$ homotopy theory variant.

Let $\Gr(1,3)$ be the Grassmannian parameterizing 1-dimensional subspaces of $\CP^3$, where the $\CC$ points of this space parameterize 2-dimensional subspaces $W \subseteq \CC^4$. This is a moduli space of the lines we're looking for.

Let $$S \to \Gr(1,3)$$ be the tautological bundle where the fiber is simply given by $S_W = W$. We can also form the bundle $$(\sym^3 S)^\dual \to \Gr(1,3)$$ where the fiber over the point corresponding to $W$ is all of the cubic polynomials on $W$, i.e. $$(\sym^3 S)^\dual_W = (\sym^3 W)^\dual.$$

Explicitly, we have the following two bundles to work with:
$$
W \to S \to \Gr(1,3) \\
(\sym^3 W)^\dual \to (\sym^3 S)^\dual \to \Gr(1,3)
$$

Our chosen $f$ determines an element of $(\sym^3 \CC^4)^\dual$, which is thus a section $\sigma_f$ of the second bundle above, where
$$
\sigma_f(W) = \restrictionof{f}{W}.
$$










