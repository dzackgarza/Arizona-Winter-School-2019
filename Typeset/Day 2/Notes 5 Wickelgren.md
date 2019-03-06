# The Euler Class

Start with the version from Algebraic Topology. Let $X$ be be an $\RR\dash$manifold of dimension $d$ and $V\surjects X$ be a rank $r$ vector bundle with fibers $V_x$ for each $x\in X$. Recall the definition of the Thom space of $V$, 

$$
\text{Th}(V) \cong \PP(V\oplus \mathcal O)  / \PP(V) \homotopic \frac{V}{V-X} \\
\text{Th}(V_x) \cong \PP(V\oplus \mathcal O)  / \PP(V_x) \homotopic S^r
$$

where $\mathcal O$ is a trivial bundle and $X$ denotes the zero section.

**Definition**: A **bundle** $V$ is **oriented**  by a Thom class $u\in H^r(\text{Th}(V); \ZZ)$ if each restriction $H^r(\text{Th}(V_x); \ZZ)$ yields a generator.

**Example**: This occurs when all transitions functions have positive determinant. Let $\mathcal U$ be an open cover of $X$, then $V$ is described by clutching (transition) functions
$$
\theset{\restrictionof{\varphi}{U \intersect W} \suchthat U,W\in\mathcal U} \text{ where } \det \restrictionof{\varphi}{U\intersect W} > 0
$$

if and only if $\det V = L^{\tensor 2}$ for some line bundle $L \surjects X$. Note that we can do this because if the determinant is greater than zero, we can take a square root, and if we take a positive square root the cocycle condition is still satisfied.

**Definition**: A **space** $X$ is **oriented** iff its tangent space $TX$ is oriented.

Assume $X$ is a compact manifold and $d=r$, then by Poincare duality we obtain an isomorphism $H^r(X; \ZZ) \cong \ZZ$, and so $e(V)\in \ZZ$ is an integer.

We can compute the Euler class in the following way: choose a section $\sigma$ with only isolated zeros, then 
$$
e(V) = \sum_{~~x\in X\\ \sigma(x) \neq 0} \deg_x(\sigma)
$$
where we sum the local degrees, and $\sigma$ is locally identified with a function 
$$
\sigma: \RR^d \to \RR^r \\
\text{coordinates on } X \mapsto \text{local trivialization}
$$ 
by choosing local coordinates and a local trivialization compatible with the standard orientations of the spheres in the domain and codomain.

Note that if we composed the trivialization with an element of $\GL(U)$ with negative determinant, that would change the local degree so this definition wouldn't make sense for relative orientations -- however, if we change coordinates for $\RR^d$ and $\RR^r$ simultaneously, it will.

**Definition:** The bundle $V\surjects X$ is **relatively oriented** iff $\hom(\det TX, \det V)$ is oriented.

We know what it means for such a homomorphism to be positive, and this won't change the value of the local index.

Since $V$ has an orientation sheaf, let $\mathcal O(V)$ be a local system on $X$ with $\mathcal O(V)_x = H^r(\text{Th}(V_x); \ZZ)$. We can then use the Thom isomorphism to get a Thom class, so we have $e(V) \in H^r(X; \mathcal O(-V))$ which comes from a canonical map. So when $V\to X$ is relatively oriented, we again have $e(V) \in \ZZ$.

# $\AA^1$ Algebraic Topology

Let $X\in\Sm$ be a smooth scheme of dimension $d$ and $V\surjects X$ an algebraic bundle of rank $r$.

**Definition**: $V$ is oriented by the data $L\surjects X$ a line bundle and an isomorphism $\det V \cong L^{\tensor 2}$.

**Definition**: $V$ is **relatively oriented** if $\hom(\det TX, \det V)$ is oriented.

**Example:** Consider both $X = \PP^n$ and $X = \Gr(m,n)$ be the Grassmannian parameterizing subspaces $\PP^m \leq \PP^n$.  Then $\det TX = \mathcal O(n+1)$, the dual of the tautological tensored $n+1$ times -- for the Grassmannian, you put it in the Plucker embedding and pull back the $\mathcal O(1)$.

$\therefore X$ is orientable $\iff n$ is odd.

This follows because we can take $\mathcal O( \frac{n+1} {2})$ and choose the morphism required in the definition above.

**Example**: $\mathcal O(n) \surjects \PP^1$ is orientable if and only if it is relatively orientable if and only if $n$ is even.

**Example**: Take $\O(d)\oplus \O(e) \to \PP^2$. Since $2+1=3$ is odd, this is orientable if and only if $d+e$ is odd. 
> Note: S. McKean uses this to make an enriched Bezout's theorem for the intersection of plane curves of degree $d$ and $e$.

## Computing Euler Classes for Relatively Orientable Bundles
> Joint with Jesse Kass

In addition to the prior assumptions, let $\sigma$ be a section of $V$ with only isolated zeros and use the same definition of $e(V)$, which will land in the Grothendieck-Witt group $GW(k)$ instead of $\ZZ$.

what remains is to define the local degree. We'll proceed in the same way by finding a function, which will give us local coordinates and a local trivialization.

**Definition**: The **Nisnevich** coordinates near $x$ are given by 
$$
\varphi: U \to \AA^d
$$ 
which induces an isomorphism on the function field, so the induced extension of residue fields $k(\varphi(p)) \injects k(p)$ is an isomorphism.

- Such coordinates determine a distinguished section of $\det TX(U)$
- A local trivialization $\restrictionof{\varphi}{U} \to \O^r$ determines a distinguished section of $\det V(U)$

And so we can make the following definition:

**Definition**: Local coordinates and a local trivialization are **compatible** if for these distinguished sections $\hom(\det TX(U), V(U)) \cong L^{\tensor 2}$.

So we can get compatibility by varying the trivialization until we get a square (no problem). Nisnevich coordinates will always exist when $k(p)$ is a separable extension of $k$, or the dimension is 1 (by Galois theory).

So suppose we have local coordinates $\phi$ and a local trivialization $\pi$ that are compatible. If $\phi: U \injects \AA^d$ is an open immersion, then our section $\sigma$ is a function can be identified by pulling back $\sigma: \AA^d \to \AA^r$ and defining $\deg_p(\sigma) \definedas \deg_{\phi(p)}(\sigma)$.

Note that we don't actually need the immersion condition here, since the $\AA^1$ local degree is finitely determined, and so modifying the function by something in a high enough power of the maximal ideal doesn't change the degree. So if the $\phi$ given by Nisnevich coordinates is an etale map where the local rings aren't isomorphic, then $\sigma$ could fail to be pulled back from $\AA^d$. However, we could just add something from a really high power of the maximal ideal, and it can be shown that $\sigma$ is pulled back from $\AA^d$. These choices don't affect the outcome, so the assumption is not necessary by "finite determinacy of $\deg_p$". 

> Need to show that it is well-defined (i.e. it doesn't depend on choice of section), which it is under some conditions.

Other perspectives: 

Barge Morel has one that lands in the oriented Chow, $e(v) \in \widetilde{\text{Ch}}{}^r(X, \det (-V))$.
> Note that you can use $V$ or $-V$ here, since the action of $GW$ has trivial squares, and the definition of the twist for oriented chow groups means that changing the twist by the square of a bundle doesn't effect the oriented chow groups. 

It is defined as follows:

There is a distinguished element $\generators{1}\in \widetilde{\text{Ch}}{}^0(X)$ which is determined by a complex
$$
\bigoplus_{z\in X^{(0)}} GW(k(Z), \det T_zX) \to \bigoplus_{z\in X^{(-1)}} GW(k(Z), \det T_zX)
$$

where $X^{(0)}$ are reduced irreducible subschemes of $X$, and the RHS disappears.