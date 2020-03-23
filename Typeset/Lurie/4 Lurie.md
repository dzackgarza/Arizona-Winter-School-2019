# Lecture 4:

> Note for this lecture: will use $L\dash$ functions, but we'll primarily be evaluating them at $s=0$.

## Review

We'll start by recalling the definition of an $L\dash$function.
In this setting, $X$ will be an algebraic variety defined over a finite field $\FF_q$.

Definition (Zeta Function)
:   One can associate a function to such a variety, namely a *zeta function*
    $$
    \zeta_X(s) = \prod_{x\in X} \frac{1}{1 - \abs{K(x)}^{-s} }
    $$
    where the product is taken over all of the closed points of the variety, and the term in the denominator is the size of the residue field at each point.

This is a generating function which contains information about the number of points your that your variety has with values in various finite fields.
It contains the same information as points that that $X$ has in $\FF_q, \FF_{q^2}$, and so on, and packages this information in a useful way.
It's called the zeta function of $X$ because you can write down (more or less) the same definition replacing $X$ with $\spec \ZZ$, and in that case this yields the Riemann Zeta function.

The zeta function of a variety over a finite field is a much simpler object is a much simpler object than the classical Riemann Zeta function: it can be written as a rational function in $q^{-s}$.

Definition (Zeta Function, Alternate)
:
$$
\zeta_X(s) =  \prod_{i\geq 0} \det \qty{ 1 - \phi q^{-s} \suchthat H^i_c(\bar X)  }
$$
where $\phi$ is the Frobenius.
