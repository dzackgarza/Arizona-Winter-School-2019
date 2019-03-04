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

We thus have
$$
\PP W \in X \iff \sigma_f(W) = 0,
$$
i.e. the line corresponding to $W$ is in our surface exactly when this section is zero. We now want to count the zeros of $\sigma_f$, which is exactly what the Euler class does.

To be precise, the Euler class counts the zeros of a section of a properly oriented vector bundle with a given weight. Let $V\to M$ be a rank $r$ $\RR\dash$ vector bundle over a dimension $r$ real manifold where we assume that $V$ is oriented. 

> We choose $\RR$ here because $\CC$ is slightly too nice and gives us a preferred orientation (which we'll want to track later.)

For any section $\sigma$ with only isolated zero, we'll assign a weight to each zero which comes from the topological degree function
$$
\deg: [S^{r-1}, S^{r-1}] \to \ZZ,
$$

where we use the brackets to denote homotopy classes of maps.

Definition: Let $p\in M$ where $\sigma(p) = 0$, and define $\deg_p(\sigma)$ in the following way:

Choose local coordinates near $p$. Since the zeros are isolated, we can choose a ball $B_\varepsilon(p)$ such that $x\in B_\varepsilon(p) - \theset{p} \implies \sigma(x) \neq 0$. Choose a local trivialization of the total space $V$. This allows us to view $\sigma: \RR^r \to \RR^r$ as a real function.

We can choose coordinates such that $p = 0$ in the domain, so $\sigma(0) = 0$, and moreover the image $\sigma(B_\varepsilon(p)) = \RR - \theset{0}$. We can then form a function 
$$
\bar\sigma: \del B_\varepsilon(p) = S^{r-1} \to S^{r-1} = \del \sigma(B_\varepsilon(p)) \\
x \mapsto \frac{\sigma(x)} {\norm{\sigma(x)}},
$$

and so we can take $\deg_p(\sigma) \definedas \deg \bar \sigma$.

There is indeterminacy here up to elements of $\Gl(r, \RR)$ which could possibly effect the sign, however, but this can be fixed using the assumption that $V$ is oriented and choosing local trivializations for which the orientations are compatible. This gives us a well-defined local degree of a section at a zero.














