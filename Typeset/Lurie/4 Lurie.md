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
  \det \qty{ 1 - \phi q^{-s} \suchthat H_c^i(\bar X)  }\inv
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

Definition (Associated L Function)
:   $$
    L(\mcf, s) = \prod_{x\in X} \det \qty{1 - \abs{\kappa(x)}^{s} \phi_x \suchthat \mcf_{\bar x}  }\inv
    .$$

This definition holds provided that $\re(s)$ is sufficiently large, which guarantees that that this infinite product converges.
You can define it for almost all values of $s$ by analytically continuing.
In the case of the zeta function, this turns out to be a rational function in $q^{-s}$, and the same thing is true for this $L\dash$function since this is equivalent by the Grothendieck-Lefschetz trace formula to the following:

Definition (L Function, Alternative)
:   $$

  \det \qty{ 1 - \phi_{q} q^{-s} \suchthat H_c^i(\bar X, \mcf)  }\inv
  ,$$
  where the Frobenius now comes from $\FF_q$ and this determinant means an alternating product as before.

This is a relative version of the zeta function: if you specialize to $\mcf$ the constant sheaf $\QQ_\ell$ everywhere, it recovers the zeta function of the variety $X$.


We now want to talk about not a single $\ell\dash$adic sheaf, but rather a complex of such sheaves.
Let $D^b(X)$ be the bounded derived category of $\QQ_\ell$ sheaves on $X$.
Let $\mcf \in D^b(X)$ denote a typical element of this category.
Roughly speaking, these can be thought of as chain complexes of $\ell\dash$adic sheaves, although that's note quite right.

The objects of this category have the property that you can associate to them for each integer $i$ a $\mch^i(\mcf)$, the $i$th cohomology of $\mcf$ in the world of sheaves.
This will be an $\ell\dash$adic sheaf on $X$.
We want to consider the bounded derived category, so these $\mch^i$ vanish for almost all $i$.

Given such an object, you can associate an $L$ function in a stupid way

Definition (L Function of a Complex)
:   $$
    L(\mcf, s) = \prod_i L( \mch^i(\mcf), s )^{(-1)^i}
    $$

Depending on which definition of $L$ functions we take on $\ell\dash$adic sheaves, we get two definitions of what it means to take an $L$ function of a complex:

Definition
:   $$
    L(\mcf, s) = \prod_{x\in X} \prod_{i\in \ZZ} \det \qty{ 1 - \abs{\kappa(x)  }^{-s}\phi_x \suchthat \mch^i(\mcf)_{\bar x}  }^{(-1)^{i+1}}
    $$
    where we now take the stalks $\mch^i(\mcf)_{\bar x}$.


Definition
:   $$
    L(\mcf, s) = \det \qty{ 1 - \phi q^{-s} \suchthat H^*(\bar X; \mcf) }\inv
    $$
    where we are now considering *hypercohomology*.

The equivalence of these two definitions again follows from the Grothendieck-Lefschetz trace formula.

We would now like to cook up an $L$ function that is relevant to the situation in previous lectures.
