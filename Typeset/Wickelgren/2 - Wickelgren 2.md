# Lecture 2: User's Guide to $\Af^1$ Homotopy Theory

Particularly, arithmetically enriching enumerative results. The first part of this talk focuses on setting up the correct category for this theory.


## Adding Colimits
Recall from last time that we wanted to form a space analogous to a sphere, given by $\PP^n/ \PP^{n-1}$, which we get from a **colimit**
$$
\begin{CD}
  \PP^{n-1} @>>> \PP^n \\
  @VVV \selfmap @VVV \\
  \pt @>>> \PP^n/ \PP^{n-1}
\end{CD}
$$

which is the same as requiring that for maps from the total space into the quotient, maps coming from the quotiented space and maps coming from the point agree when the compositions are taken.

**Example:** Another example of a colimit is the union, which is given by
$$
\begin{CD}
  U\intersect V @>>> U \\
  @VVV \selfmap @VVV \\
  V @>>> U \union V
\end{CD}
$$

These correspond to crushing and gluing operations, which we can do with topological spaces and would like to do with schemes as well. We'd also like smooth schemes to behave like smooth manifolds, in the sense that we can take an open ball around each point. This is part of what $\Af^1$ homotopy theory buys us.

We want colimits, so we add them: let $\Sm$ to be the category of smooth schemes over $k$. There is a Yoneda embedding
$$
\Sm \mapsvia{Y} \mathrm{Func}(\Sm^\text{op}, \mathrm{Sset}) = \text{PreSh}(\Sm) \\
X \mapsto \hom(\wait, X)
$$

where one might normally require the target to be sets, but since we'd like homotopy colimits and to be able to do things analogous to fibrant/cofibrant replacements, we aim for simplicial sets instead which can essentially be regarded as topological spaces. We can also identify the target with presheaves on the category of smooth schemes.

We're building a category for a homotopy theory, which means we need either
- A simplicial model category, or
- An $\infty\dash$category

Both have notions of fibrations, cofibrations, an associated homotopy category, weak equivalences, etc, and $\text{PreSh}(\Sm)$ has this structure.

## Preserving Old Colimits: Picking a Topology
This construction is essentially "freely adding colimits". Since $\Sm$ had colimits (e.g. the union/intersection of open sets), we want $Y$ to preserve these. We fix this be forcing certain maps to be equivalences using **Bousfield localization**.

This is carried out by looking at open covers
$$
U = \coprod_{\alpha} U_\alpha \to X
$$

and making a simplicial object out of this map and forcing a weak equivalence
$$
\text{cos}^0_x \coprod_\alpha U_\alpha \mapsvia{\homotopic} X
$$

> Note: this may be the Cech nerve, not entirely sure. Pretty sure I got the notation wrong though.

This gives us a localization functor
$$
\mathrm{PreSh}(\Sm) \mapsvia{L_\tau} \mathrm{Sh}_k
$$

for $\tau$ a Grothendieck topology which declares certain classes of maps to be covers. We have some choices of topology here, roughly in order of increasing number of open sets:
- Zariski (on schemes)
- Nisnevich
- Etale

**Definition:**  A map $f\in \hom(X,Y) \in \Sm$ (not necessarily smooth) is **etale** at a point $x\in X$ if the induced map on tangent/cotangent spaces is an isomorphism:
$$
T_x X \mapsvia{f^*} T_{f(x)}Y
$$

**Definition:** A map $f: \coprod_\alpha U_\alpha \to X$ is an **etale cover** if it is etale and surjective

**Definition:** A map $f: \coprod_\alpha U_\alpha \to X$ is a **Nisnevich cover** if it is an etale cover and $x\in X \implies \exists u\in U \suchthat f^*: k(x) \mapsvia{\cong}k(u)$.

This topology has a few nice properties:
- Smooth schemes have etale maps into $\Af^n$, inclusions/closed immersions $Z \injects X$ induce maps $\Af^d \injects \Af^n$
- Satisfies descent for K-theory
- The cohomological dimension equals the Krull dimension
- Cohomology can be computed Cech complexes
- More listed in Voevodsky's original paper

## Contracting the Affine Line

The last step is forcing $\Af^1$ to be contractible, i.e. $\Af^1 \cross X \homotopic X$, which will come from another localization $L_\Af$. This composition will land us in the homotopy theory we want:
$$
\Sm \mapsvia{Y} \text{PreSh}_k \mapsvia{L_\tau} \text{Sh}_k \mapsvia{L_{\Af}} \text{Spc}_k
$$

where $\tau$ is the choice of the Nisnevich topology, and so we'll call $\text{Spc}_k$ our $\Af^1$ homotopy theory.

# Making Spheres

Given two pointed spaces $X, Y$, we have
$$
X \wedge Y = \frac{X \cross Y}{(X\cross \pt) \union (\pt \cross Y)}
$$

In topology, we have $S^m \wedge S^n = S^{m+n}$. In $\Af^1$ homotopy theory, we have functors to simplicial sets, and so we can take constant functors, and in particular any element space living in simplicial sets is in our new homotopy theory as well. So we have $S^1$, we can also take $\GG_m = \Af^1 - \theset{0}$, and so we have spheres
$$
S^{p+q,q} = (S^1)^{\wedge p} \wedge (\GG_m)^{\wedge q} .
$$

Some of these end up being familiar spaces. For example, we can look at the colimit
$$
\begin{CD}
  \GG_m @>>> \Af^1 \homotopic \pt \\
  @VVV \selfmap @VVV \\
  \pt \homotopic \Af^1 @>>> \PP^1
\end{CD}
$$

which follows from the fact that $\PP^1 = \Af^1 \union \theset{\infty}$ (yielding the top-right copy of $\Af^1$), and we can take a neighborhood around the point at $\infty$ to obtain the bottom-left copy -- these intersect in $\GG_m$.

So $\PP^1$ is the colimit of maps from $\GG_m$ to a point, so we can conclude that $\PP^1 \homotopic \Sigma \GG_m = S^1 \wedge \GG_m$.

We can also show $\Af^n - \theset{0} \homotopic (S^1)^{\wedge n-1}\wedge (\GG_m)^{\wedge n}$. This will rely on a general fact about the colimit of $X\cross Y$ with its projections is a suspension, given by
$$
\begin{CD}
  X\cross Y @>>> X \\
  @VVV \selfmap @VVV \\
  Y @>>> \therefore \Sigma X\wedge Y
\end{CD}
$$

and so we can proceed by induction on the following diagram:
$$
\begin{CD}
  (\Af^{n-1} - \theset{0} )\cross(\Af^1 -\theset{0}) @>>> (\Af^{n-1} -\theset{0}) \cross \Af^1 \\
  @VVV \selfmap @VVV \\
  \Af^n \cross (\Af^1 -\theset{0}) @>>> \Af^n - \theset{0}
\end{CD}
$$

We also have $\PP^{n} / \PP^{n-1} \homotopic (S^1)^{\wedge n}\wedge (\GG_m)^{\wedge n}$. This can be show because $\PP^{n} / \PP^{n-1} \homotopic \PP^n / \PP^n-\theset{0}$ because $\Af^1$ is trivial and we can homotop the embedded $\PP^{n-1}$ down to the origin, giving a line bundle over $\PP^{n-1}$. We can then cut out the copy of $\PP^{n-1}$ at infinity, yielding $\Af^n / \Af^{n} - \theset{0} \homotopic \pt / \Af^{n} - \theset{0} = \Sigma (\Af^{n} - \theset{0})$, where the last equality comes from looking at a similar colimit diagram as earlier.

# Thom Spaces
These can be made out of vector bundles, which will prove to be useful in viewing smooth schemes like manifolds. Let $V \to X$ be an algebraic vector bundle. Then the Thom space

$$
\text{Th}(V) = \frac{V} {V-X} \homotopic \frac{\PP(V \oplus \mathcal O)}{\PP V}
$$
where $X$ here corresponds to the zero section, $\mathcal O$ is the trivial line bundle, and $\PP V$ is the projectivization of $V$ where the coordinate is zero.

> Note: If this was a virtual vector bundle, we could make a Thom spectrum.

The next theorem gives us neighborhoods around points
