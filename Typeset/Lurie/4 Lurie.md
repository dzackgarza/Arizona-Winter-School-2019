# Lecture 4:

> Note for this lecture: will use $L\dash$ functions, but we'll primarily be evaluating them at $s=0$.

## Review

We'll start by recalling the definition of an $L\dash$function.
In this setting, $X$ will be an algebraic variety defined over a finite field $\FF_q$.
One can associate a function to such a variety, namely a *zeta function*
$$
\zeta_X(s) = \prod_{x\in x} \frac{1}{1 - \abs{K(x)}^{-s} }
$$
where the product is taken over all of the closed points, and the term in the denominator is the size of the residue field.
