# User's Guide to $\AA^1$ Homotopy Theory
Particularly, arithmetically enriching enumerative results.

Recall from last time that we wanted to form a space analogous to a sphere, given by $\PP^n/ \PP^{n-1}$, which we get from a colimit
$$
\begin{CD}
  \PP^{n-1} @>>> \PP^n \\
  @VVV \selfmap @VVV \\
  \pt @>>> \PP^n/ \PP^{n-1}
\end{CD}
$$

which is the same as requiring that for maps from the total space into the quotient, maps coming from the quotiented space and maps coming from the point agree when the compositions are taken.

Another example of a colimit is the union, which is given by
$$
\begin{CD}
  U\intersect V @>>> U \\
  @VVV \selfmap @VVV \\
  V @>>> U \union V
\end{CD}
$$

These correspond to crushing and gluing operations, which we can do with topological spaces and would like to do with schemes as well. We'd also like smooth schemes to behave like smooth manifolds, in the sense that we can take an open ball around each point. This is part of what $\AA^1$ homotopy theory buys us.

We want colimits, so we add them: let $\Sm$ to be the category of smooth schemes over $k$. There is a Yoneda embedding
$$
\Sm \mapsvia{Y} \mathrm{Func}(\Sm^\text{op}, \mathrm{Sset}) = \text{PreSh}(\Sm) \\
X \mapsto \hom(\wait, X)
$$

where one might normally require the target to be sets, but since we'd like homotopy colimits and to be able to do things analogous to fibrant/cofibrant replacements, we aim for simplicial sets instead which can essentially be regarded as topological spaces. We can also identify the target with presheaves on the category of smooth schemes.

We're building a homotopy theory, which can mean
- A simplicial model category, or
- An $\infty\dash$category

Both have notions of fibrations, cofibrations, an associated homotopy category, weak equivalences, etc, and $\text{PreSh}(\Sm)$ has this structure. 

This construction is essentially "freely adding colimits", but since $\Sm$ had colimits (e.g. the union/intersection of open sets), we want $Y$ to preserve these. We fix this be forcing certain maps to be equivalences using **Bousfield localization**.

This is carried out by looking at open covers
$$
U = \coprod_{\alpha} U_\alpha \to X
$$

and making a simplicial object out of this map and forcing a weak equivalence
$$
\text{cos}^0_x \coprod_\alpha U_\alpha \mapsvia{\homotopic} X
$$

> Note: this may be the Cech nerve, not entirely sure.

This gives us a localization functor
$$
\mathrm{PreSh}(\Sm) \mapsvia{L_\tau} \mathrm{Sh}_k
$$

for $\tau$ a Grothendieck topology which declares certain classes of maps to be covers. We have some choices of topology here, roughly in order of increasing number of open sets:
- Zariski (on schemes)
- Nisnevich
- Etale

Definition:  A map $f\in hom(X,Y) \in \Sm$ (not necessarily smooth) is **etale** at a point $x\in X$ if the induced map on tangent/cotangent spaces is an isomorphism:
$$
T_x X \mapsvia{f^*} T_{f(x)}Y
$$

Definition: A map $f: \coprod_\alpha U_\alpha \to X$ is an **etale cover** if it is etale and surjective

Definition: A map $f: \coprod_\alpha U_\alpha \to X$ is a **Nisnevich cover** if it is an etale cover and $x\in X \implies \exists u\in U \suchthat f^*: k(x) \mapsvia{\cong}k(u)$.

This topology has a few nice properties:
- Smooth schemes have etale maps into $\AA^n$, inclusions/closed immersions $Z \injects X$ induce maps $\AA^d \injects \AA^n$
- Satisfies descent for K-theory
- The cohomological dimension equals the Krull dimension 
- Cohomology can be computed Cech complexes
- More listed in Voevodsky's original paper

The next step is forcing $\AA^1$ to be contractible, i.e. $\AA^1 \cross X \homotopic X$, which will come from another localization $L_\AA$. This composition will land us in the homotopy theory we want:
$$
\Sm \mapsvia{Y} \text{PreSh}_k \mapsvia{L_\tau} \text{Sh}_k \mapsvia{L_{\AA}} \text{Spc}_k
$$

where $\tau$ is the choice of the Nisnevich topology, and so we'll call $\text{Spc}_k$ our $\AA^1$ homotopy theory.

# Making Spheres

Given two pointed spaces $X, Y$, we have
$$
X \wedge Y = \frac{X \cross Y}{(X\cross \pt) \union (\pt \cross Y)}
$$

In topology, we have $S^m \wedge S^n = S^{m+n}$. In $\AA^1$ homotopy theory, we have functors to simplicial sets, and so we can take constant functors, and in particular any element space living in simplicial sets is in our new homotopy theory as well. So we have $S^1$, we can also take $\GG_m = \AA^1 - \theset{0}$, and so we have spheres
$$
S^{p+q,q} = (S^1)^{\wedge p} \wedge (\GG_m)^{\wedge q} .
$$ 

Some of these end up being familiar spaces. For example, we can look at the colimit
$$
\begin{CD}
  \GG_m @>>> \AA^1 \homotopic \pt \\
  @VVV \selfmap @VVV \\
  \pt \homotopic \AA^1 @>>> \PP^1
\end{CD}
$$

which follows from the fact that $\PP^1 = \AA^1 \union \theset{\infty}$ (yielding the top-right copy of $\AA^1$), and we can take a neighborhood around the point at $\infty$ to obtain the bottom-left copy -- these intersect in $\GG_m$.

So $\PP^1$ is the colimit of maps from $\GG_m$ to a point, so we can conclude that $\PP^1 \homotopic \Sigma \GG_m = S^1 \wedge \GG_m$.

We can also show $\AA^n - \theset{0} \homotopic (S^1)^{\wedge n-1}\wedge (\GG_m)^{\wedge n}$. This will rely on a general fact about the colimit of $X\cross Y$ with its projections is a suspension, given by
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
  (\AA^{n-1} - \theset{0} )\cross(\AA^1 -\theset{0}) @>>> (\AA^{n-1} -\theset{0}) \cross \AA^1 \\
  @VVV \selfmap @VVV \\
  \AA^n \cross (\AA^1 -\theset{0}) @>>> \AA^n - \theset{0} 
\end{CD}
$$

We also have $\PP^{n} / \PP^{n-1} \homotopic (S^1)^{\wedge n}\wedge (\GG_m)^{\wedge n}$. This can be show because $\PP^{n} / \PP^{n-1} \homotopic \PP^n / \PP^n-\theset{0}$ because $\AA^1$ is trivial and we can homotop the embedded $\PP^{n-1}$ down to the origin, giving a line bundle over $\PP^{n-1}$. We can then cut out the copy of $\PP^{n-1}$ at infinity, yielding $\AA^n / \AA^{n} - \theset{0} \homotopic \pt / \AA^{n} - \theset{0} = \Sigma (\AA^{n} - \theset{0})$, where the last equality comes from looking at a similar colimit diagram as earlier.

# Thom Spaces
These can be made out of vector bundles, which will prove to be useful in viewing smooth schemes like manifolds. Let $V \to X$ be an algebraic vector bundle. Then the Thom space 

$$
\text{Th}(V) = \frac{V} {V-X} \homotopic \frac{\PP(V \oplus \mathcal O)}{\PP V}
$$
where $X$ here corresponds to the zero section, $\mathcal O$ is the trivial line bundle, and $\PP V$ is the projectivization of $V$ where the coordinate is zero.

> Note: If this was a virtual vector bundle, we could make a Thom spectrum.

The next theorem gives us neighborhoods around points

**The Purity Theorem**:
Let $Z \injects X$ be a closed immersion in $\Sm$. Consider $\frac X {X-Z}$, in topology we could take a tubular neighborhood around $Z$ and view this as a neighborhood mod its boundary. This is equivalent to $\text{Th}(N_Z X)$, the Thom space of the normal bundle of $Z$ in $X$. $qed$

Example: Let $Z =\spec(k)$ and $X \in \Sm$, then let $U$ be a Zariski open neighborhood of $z$. Then $U/U-Z \homotopic \PP^n / \PP^{n-1}$ since the Thom space is just a vector space here. So this produces a sphere around $z$.

Example: Replace $\spec k$