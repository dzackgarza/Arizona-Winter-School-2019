# The Euler Class

Start with the version from Algebraic Topology. Let $X$ be be an $\RR\dash$manifold of dimension $d$ and $V\surjects X$ be a rank $r$ vector bundle with fibers $V_x$ for each $x\in X$. Recall the definition of the Thom space of $V$, 

$$
\text{Th}(V) \cong \PP(V\oplus \mathcal O)  / \PP(V) \homotopic \frac{V}{V-X} \\
\text{Th}(V_x) \cong \PP(V\oplus \mathcal O)  / \PP(V_x) \homotopic S^r
$$

where $\mathcal O$ is a trivial bundle and $X$ denotes the zero section.

**Definition**: $V$ is **oriented**  by a Thom class $u\in H^r(\text{Th}(V); \ZZ)$ if each restriction $H^r(\text{Th}(V_x); \ZZ)$ yields a generator.

**Example**: This occurs when all transitions functions have positive determinant. Let $\mathcal U$ be an open cover of $X$, then $V$ is described by clutching (transition) functions
$$
\theset{\restrictionof{\varphi}{U \intersect W} \suchthat U,W\in\mathcal U} \text{ where } \det \restrictionof{\varphi}{U\intersect W} > 0
$$

if and only if $\det V = L^{\tensor 2}$ for some line bundle $L \surjects X$. Note that we can do this because if the determinant is greater than zero, we can take a square root, and if we take a positive square root the cocycle condition is still satisfied.

**Definition**: A space $X$ is oriented iff its tangent space $TX$ is oriented.

Assume $X$ is a compact manifold and $d=r$, then by Poincare duality we obtain an isomorphism $H^r(X; \ZZ) \cong \ZZ$, and so $e(V)\in \ZZ$ is an integer.

We can compute the Euler class in the following way: choose a section $\sigma$ with only isolated zeros, then 
$$
e(V) = \sum_{~~x\in X\\ \sigma(x) \neq 0} \deg_x(\sigma)
$$
where we sum the local degrees, and $\sigma$ is locally identified with a function $\sigma: \RR^d \to \RR^r$ by choosing local coordinates and a local trivialization compatible with the standard orientations of the spheres in the domain and codomain.

Note that if we composed the trivialization with an element of $\GL(n, \RR)$