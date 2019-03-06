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

if and only if $det V = L^{\tensor 2}$ for some line bundle $L \surjects X$