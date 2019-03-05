# Review
Let $Y \to \spec(\FF_q)$ be some algebro-geometric object defined over $\FF_q$ -- one can have an algebraic variety in mind, but this is geared towards an algebraic stack such as the moduli stack of $G\dash$bundles on an algebraic curve.

We can then look at the $\FF_q\dash$valued points of $Y$, $Y(\FF_q)$, and we think of stacks as categories, where we can measure the size of this category in the following way:
$$
\abs{Y(\FF_q)} = \sum_{y\in Y(\FF_q)} \frac{1}{\abs{\Aut(y)}}
$$

where the sum is over the objects in this category, with one term from each isomorphism class.

As a special case, let $Y$ be a smooth algebraic stack of dimension $d$, which means that it is locally an algebraic variety (i.e. it admits a submersive map from an algebraic variety) where this variety is smooth.

Definition: $Y$ satisfies the Grothendieck-Lefschetz trace formula (GL) if the number of $\FF_q$ points on $Y$ is given by some formula involving the trace of the Frobenius $\varphi$ on cohomology, i.e.
$$\begin{align*}
\frac{\abs{Y(\FF_q)}}{q^d} &= \tr(\varphi^{-1} \mid H^*(\bar Y))\\
& \definedas \sum_i (-1)^i\tr(\varphi^{-1} \mid H^i(\bar Y))
\end{align*}$$

where $q^d$ is the naive estimate of how many $\FF_q$ points there are in $Y$ and 
$$
\bar Y = Y \underset{\spec(\bar\FF_q)}\cross\spec(\bar \FF_q),
$$

so the bar notation just means extending scalars up to the algebraic closure of the underlying field.

This definition makes sense because we can ask about the $\ell\dash$adic cohomology of $\bar Y$, which is some$\QQ_\ell\dash$vector space with an automorphism called the Frobenius, and so we can take its inverse and trace.

The classical GL trace formula says this is true for $Y$ an algebraic variety, and we want an analog for stacks. We'll go through this for a moduli stack of $G\dash$ bundles not on a curve, but just on a point.

Example: Let $G$ be a linear algebraic group over $\FF_q$ and $Y=BG$, the classifying stack of $G$, which is characterized by the equivalence
$$
\pmatrix{\text{Maps } \\ \spec(R) \to BG} \iff \pmatrix{\text{Principal $G\dash$bundles}\\\text{on $\spec(R)$} }
$$

for any $\FF_q\dash$algebra $R$.

A more specific example: let $G = \GG_m$, the multiplicative group, and $Y =B\GG_m$ so that an $R\dash$valued point of $Y$ is just an invertible $R\dash$module. 

What is $Y(\FF_q)$? This is the category of 1-dimensional $\FF_q\dash$vector spaces -- so up to isomorphism, there's only one object in this category, but it has a group of symmetries $\Aut \FF_q = \FF_q^\times$ the group of units. We thus obtain
$$
\abs{Y(\FF_q)} = \sum_{y\in Y(\FF_q)} \frac{1}{\abs{\Aut(y)}} = \frac{1}{\abs{\FF_q^\times}} = \frac{1}{q-1}.
$$

We then need to check what the dimension $d=\dim B\GG_m$ is. We regard $B\GG_m$ as what you get by taking the point (here $\spec \FF_q$) and mod out by the (trivial?) action of $\GG_m$, i.e.
$$
B\GG_m = \pt / \GG_m
$$

where the quotient is taken in the category of stacks and not varieties. In this case, we get 
$$
\dim B\GG_m = \dim \pt - \dim \GG_m = 0 - 1 = -1.
$$

and so we obtain 

$$
\frac {\abs{Y(\FF_q)}}{q^{\dim Y}} = \frac{1/(q-1)}{q^{-1}} = \frac q {q-1}
$$

for the LHS of the GL trace formula.

For the RHS, we are looking at 
$$
\tr(\varphi^{-1} \mid H^*(\overline{B\GG_m}))
$$
where the bar is just to remind that we're in algebraic closures of the underlying fields.

Before seeing what this looks like in characteristic $p$, lets first look at $\CC$ and $\GG_m(\CC) = \CC^\times$. In this setting, we can dispense with $\ell\dash$adic cohomology and just take the usual cohomology of topological spaces. 

We can also just take the usual topological classifying space $B\GG_m(\CC)$ by just finding a contractible space on which $\CC^\times$ acts freely. We know that $\CC^\times$ will act on any $\CC\dash$vector space $V$, but fixes zero. We could instead try letting it act on $V-\theset{0}$, but this isn't contractible in -- in finite dimensions. So we can take $\CC^\infty = \varprojlim \CC^n$, where $\CC^\infty - \pt \homotopic \pt$ and is thus contractible, and thus we get $B\CC^\times \homotopic \CC^\infty / \CC^\times \cong \CP^\infty$.

The cohomology of $\CP^\infty$ is well-known, and given by the polynomial ring
$$
H^*(\CP^\infty) = \Lambda[t], \\ \abs{t} = 2.
$$

If we instead take the $\ell\dash$adic cohomology of the classifying stack instead (over any algebraically closed field where $\ell\neq 0$), you get
$$
H^*(\overline {B\GG_m}) = \QQ_\ell[t], \\ \abs{t} = 2.
$$

which is a $\QQ_\ell\dash$algebra. But here we also have a Frobenius that acts on $H^*$, where $\phi(t) = qt$ and $\phi(t^n) = q^nt$ (where $t$ was the generator in $H^*$). We then have

$$
\tr(\varphi^{-1} \mid H^*(\overline{B\GG_m})) = \sum_{n\geq 0} q^{-n} = \frac{q}{q-1}
$$

where the signs drop out because everything is in even degree, and the term comes from degree $2n$ and $\phi^{-1}: x\mapsto 2^{-n} x$.

**Conclusion**: The GL trace formula works for the stack $B\GG_m$, even though it was not an algebraic variety.

Note that the reason we take $\phi^{-1}$ here is because this formula will involve an infinite sum which has to converge. Taking just the trace of $\phi$ will not yield a convergent sum, whereas $\tr\phi^{-1}$ does because the eigenvalues of $\phi$ are like positive powers of $q$.

# $\ell\dash$adic Homotopy Groups
A different way of thinking about the above computation: we'll see that we can count the number of points on an algebraic variety not by using $\ell\dash$adic cohomology, but rather a notion of $\ell\dash$adic homotopy.

Let $\bar Y$ be some AG object over an algebraically closed field $k$ with a fixed base point $y\in\bar Y(k)$. We'll later be interested in the case where $k =\overline{\FF_q}$

We can take the etale fundamental group $\pi_1^\text{et}(\bar Y, y)$, which is a profinite group that was introduced by Grothendieck. If we assume that $\bar Y$ is connected, then $\pi_1$ is characterized by the property
$$
\pmatrix{\text{Finite etale}\\\text{covers of } \bar Y} \iff \pmatrix{\text{Finite sets with} \\ \text{a continuous action} \\ \text{of } \pi_1^\text{et}(\bar Y, y)}.
$$

Generally in characteristic $p$, this invariant ends up being too large, so we reduce by taking the maximal pro$\dash\ell$ quotient, which we denote $\pi_1^\text{et}(\bar Y, y)_\ell$. This is a profinite $\ell\dash$group, where $\ell\neq 0 \in k$.

# Artin-Mazur Refinement

Assuming 
- $\pi_1^\text{et}(\bar Y, y)_\ell = 0$, so $\bar Y$ looks simply-connected at $\ell$.
  - Equivalently, $H^1_\text{et}(\bar Y, \ZZ/\ell\ZZ)$
- $\dim(H^1_\text{et}(\bar Y, \ZZ/\ell\ZZ)) < \infty$ as a vector space over $\ZZ/\ell\ZZ$.
  - This always happens for $\bar Y$ an algebraic variety.


To $\bar Y$ they associate a topological space $Z$ , the **$\ell\dash$adic homotopy type of $Y$** such that
- $Z$ is simply-connected and each $\pi_n(Z)$ is a finitely generated $\ZZ_\ell\dash$module
  - So it behaves as if it's $\ell\dash$adically complete.
- $H^*_\text{Sing}(Z, \ZZ/\ell\ZZ) \cong H_\text{et}^*(\bar Y, \ZZ/\ell\ZZ)$
  - This is an abstract isomorphism. Stating this carefully would involve saying there is some datum that induces this isomorphism.


This allows us to realize the etale cohomology of some AG object $Y$ as the literal cohomology of some actual topological space $Z$ that is related to $Y$. So we can produce many more invariants of an algebraic variety $\bar Y$.

This also allows us to define homotopy groups of $\bar Y$, given by 
$$
\pi_n(\bar Y) = \pi_n(Z)
$$

where we can ignore base points because we are in the simply-connected case. This is a finitely generated $\ZZ_\ell\dash$module, and for now we will only be interested in its rationalization 
$$
\pi_n(\bar Y)_{\QQ_\ell}\definedas \pi_n(\bar Y)\left[\frac 1 \ell\right]
$$

which is now a finite-dimensional $\QQ_\ell\dash$vector space.

How are the $\ell\dash$adic homology groups related to these $\ell\dash$adic homotopy groups? In Topology, we have the Hurewciz maps taking homotopy groups into homology groups, which we can think of as giving a bilinear pairing between the homotopy groups and the cohomology groups (via natural duality of homology/cohomology).

We have the same thing here: there is a canonical map
$$
b: \pi_n(\bar Y)_{\QQ_\ell} \tensor H^n(\bar Y) \to \QQ_\ell \\
(f: S^n \to Z, \eta: H_n(\bar Y) \to \QQ_\ell) \mapsto f^*\eta\\ ~ \\
\text{where } f^*\eta \in H^n(S^n; \QQ_\ell) \cong \QQ_\ell
$$


which amounts to just pulling back elements in cohomology along the maps given by homotopy groups.

> Note: I may have gotten the type of $\eta$ wrong here.

Nothing interesting happens in degree zero, so let's take the reduced homology instead and define $I = \tilde {H^*}(\bar Y) \leq H^*(\bar Y)$ which is an ideal. We can then descend the above pairing into a new pairing
$$
\bar b: \pi_n(\bar Y)_{\QQ_\ell} \tensor \frac I I^2 \to \QQ_\ell
$$

where $b$ will vanish on any cohomology class that can be decomposed as a product of two cohomology classes of lower degree. This comes from observing that 
$$
\eta = \eta_1 \eta_2 \implies f(\eta) = f(\eta_1)f(\eta_2) \in H^*(S^n; \QQ_\ell)
$$

where the two images land in degree lower than $n$ in the cohomology ring of the sphere and thus vanish.

If $H^*(\bar Y)$ is a polynomial ring on generators of only even degree, then $\bar b$ is a perfect pairing and thus
$$
\pi_*(\bar Y) = \left(\frac I I^2\right)^\dual,
$$

so we can read the homotopy groups right off of the cohomology. Going the other way almost works, since we have a filtration
$$
\cdots I^3 \subseteq I^2 \subseteq I \subseteq H^*(\bar Y)
$$

and $H^*$ is a polynomial ring, this is an exhaustive filtration, and we can recover the homotopy from the associated graded.

Note that for an algebraic variety of dimension $n$, cohomology can only be supported on degrees up to $2n$, so it will never look like a polynomial algebra -- but this is something that may work for stacks (e.g. $\bar Y = B\GG_m)$.

What does the GL trace formula say in this case?

In this situation, the Frobenius will act on both the cohomology and homotopy groups, and $\bar b$ will be equivariant with respect to this action. For the infinite sum in the formula to make sense, we fix an embedding $\QQ_\ell \into \CC$ with the usual topology.

Supposing we only have even dimensional generators, $I/I^2$ is a finite-dimensional $\QQ_\ell$ vector space. So we look at the generalized eigenvalues of $\varphi$ on this once we extend scalars to $\CC$, say $\theset{\lambda_i}_{i=1}^n$ on $\pi_*(\bar Y)$ and thus the same eigenvalues on $\pi_*(\bar Y)^\dual = (I/I^2)^{\dual\dual} = I/I^2$.
