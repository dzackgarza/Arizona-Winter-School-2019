# Lecture 4:

> Note for this lecture: will use $L\dash$ functions, but we'll primarily be evaluating them at $s=0$.

## Review

We'll start by recalling the definition of an $L\dash$function.
In this setting, $X$ will be an algebraic variety defined over a finite field $\FF_q$.

Definition (Zeta Function)
:   One can associate a function to such a variety, namely a *zeta function*
    $$
    \zeta_X(s) = \prod_{x\in X} \frac{1}{1 - \abs{\kappa(x)}^{-s} }
    $$
    where the product is taken over all of the closed points of the variety, and the term in the denominator is the size of the residue field at each point.

This is a generating function which contains information about the number of points your that your variety has with values in various finite fields.
It contains the same information as points that that $X$ has in $\FF_q, \FF_{q^2}$, and so on, and packages this information in a useful way.
It's called the zeta function of $X$ because you can write down (more or less) the same definition replacing $X$ with $\spec \ZZ$, and in that case this yields the Riemann Zeta function.

The zeta function of a variety over a finite field is a much simpler object is a much simpler object than the classical Riemann Zeta function: it can be written as a rational function in $q^{-s}$.

Definition (Zeta Function, Alternate)
: $$
  \zeta_X(s) =  \prod_{i\geq 0} \det \qty{ 1 - \phi q^{-s} \suchthat H^i_c(\bar X)  }^{(-1)^{? + 1}}
  \definedas
  \prod_{i\geq 0} \det \qty{ 1 - \phi q^{-s} \suchthat H_c^i(\bar X)  }\inv
  $$
where $\phi$ is the Frobenius.

The equivalence of these two definitions is a consequence of the Grothendieck-Lefschetz trace formula mentioned earlier.

We now want to talk about a generalization of this: a zeta function "with coefficients".
Let $\mcf$ be an $\ell\dash$adic sheaf on $X$.
If I have a closed point of my variety $x\in X$, I can think of it as giving me a map $\spec \kappa(x) \mapsvia{x} X$ from the spectrum of the residue field at that closed point.
I would like to refine that to a geometric point by choosing an algebraic closure of that finite field, yielding a composite that we'll denote by $x$ with a bar over it:

\begin{center}
\begin{tikzcd}
\spec \bar{\kappa(x) } \ar[r] \ar[rr, bend left, "\bar x"] & \spec \kappa(x) \ar[r, "x"] X
\end{tikzcd}
\end{center}

This is just a geometric point lying over the point $x$ of the underlying topological space.
Then if $\mcf$ is an $\ell\dash$adic sheaf, we can talk about its stalk $\mcf_{\bar x}$, which is a finite dimensional $\QQ_\ell\dash$vector space.
It is obtained by taking the sheaf $\mcf$ which lives on $X$ and first restricting it to $x$, which gives a sheaf of the spectrum of a finite field, then restricting it to the spectrum of the algebraic closure of that finite field.
At the intermediate stage, we get some information: the $\QQ_\ell$ vector space $\mcf_{\bar x}$ has a canonical automorphism, namely the Frobenius $\phi_x$ associated to the field $\kappa(x)$.

