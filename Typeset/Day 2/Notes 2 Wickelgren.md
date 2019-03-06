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

Example: Replace $\spec k$ with $\spec(k(z))$, this yields $\PP^n_{k(z)} / \PP^{n-1}_{k(z)} \homotopic \PP^n / \PP^{n-1} \wedge (\spec (k(z)\coprod \pt)$
> Note: video says "disjoint basepoint" here and uses different notation, may not be correct.

Compare to manifolds: if $z\in U$ a small ball, then $\Sigma \del U \homotopic U / U - z$. So if we wanted to look at maps between boundaries, we could suspend and take degrees.

# The Grothendieck-Witt Group and Milnor K-Theory
Recall that the target of the degree map was $GW(k)$; we'll also talk a bit about Milnor K-theory $K^M_*(k)$.

From yesterday, we defined $GW(k)$ as the isomorphism classes of symmetric nondegenerate bilinear forms over $k$, which had a generators
$$
\generators{a}, \quad a\in k^\times\\
\generators{a}: k^2 \to k\\
(x,y) \mapsto axy
$$

and relations
$$\begin{align*}
\generators{ab^2} &= \generators{a} \quad&(b\neq 0)\\
\generators{a}\tensor\generators{b} &= \generators{ab} &\\
\generators{a} + \generators b &= \generators{a+b} + \generators{ab(a+b)} \quad&(a+b\neq 0)
\end{align*}$$

which follows because we're in $k^\times/(k^\times)^2$. Note that the last relation is very important.

These relations imply a special relation concerning a **hyperbolic form,** which is given by 
$$
h\definedas \generators {1} + \generators {-1} = \generators a + \generators{-a}
$$ 
for any $a$.

We'll look at invariants on bilinear forms -- for many common fields, there are algorithms to determine equality of sums of generators, and thus in $GW$ there are many tools to work with. Some of these tools are invariants arising from the Milnor conjecture, which involves this group and is a huge achievement in $\AA^1$ homotopy theory.

We have a rank homomorphism:
$$
\text{rank}: GW(k) \to \ZZ \\ 
(B: V^2 \to k) \mapsto \dim V
$$

and the **fundamental ideal** is defined as $I \definedas \ker \text{rank}$. This yields a filtration
$$
GW(k) \supseteq I \supseteq I^2 \supseteq \cdots
$$

where the associated graded are etale cohomology groups and (by the Milnor conjecture) Milnor K-theory groups.

We define **Milnor K-theory** as
$$
K_i^M \definedas \frac{\bigoplus_{i=1}^\infty  (k^\times)^{\tensor i} } {\generators{a\tensor(1-a)}}
$$

which is tensor algebra on $k^\times$, modded out by the Steinberg relation.

**Theorem: The Milnor Conjecture (Voevodsky)**
There is a map
$$
K_n^M \to I^n/I^{n+1} \\
\bigotimes_{i=1}^n a_i \mapsto \prod_{i=1}^n \left(\generators{1} - \generators{a_i}\right).
$$

We can also look at the Kummer map coming from the short exact sequence
$$
1\to \ZZ/2\ZZ \to \overline {k^\times} \to \overline{k^\times} \to 1
$$

which lets us make a map 
$$
k^\times \to H_\text{et}^1(k;~\ZZ/2\ZZ)
$$

where we can use that fact that $k^\times \cong K^M_1$ to land in Milnor K-theory,
$$
K_1^M \to H_\text{et}^1(k;~\ZZ/2\ZZ),
$$

where we can use the cup product to lift this to a map to the $n$th graded piece
$$
K_n^M \to H_\text{et}^n(k;~\ZZ/2\ZZ).
$$

Fitting all of this together, we get maps
$$
I^n/I^{n+1} \from K_n^M \to H_\text{et}^n(k;~\ZZ/2\ZZ),
$$

and the Milnor conjecture states that these are isomorphisms.

In other words, the associated graded of this filtration is the etale cohomology or Milnor K-theory, and if you have a field for which the $n$th etale cohomology in $\ZZ/2\ZZ$ coefficients doesn't vanish, then there is a nontrivial piece in the associated graded. 

This lets us view maps $I^n \to I^n/I^{n+1}$ as invariants on $GW(k)$. 
- For $n=0$, this is the rank homomorphism.  
- For $n=1$ we get the discriminant, which is the determinant of the linear map associated to the bilinear form obtained after choosing a basis.
- For $n=2$ this is the Hasse-Witt invariant (see written notes)
- For $n=3$ this is the Arason invariant

For higher $n$ these invariants don't have names, but for various fields, the lower degrees form a complete invariant -- for example, for finite fields, one needs only check $n=0,1$, while $\QQ$ requires $n=0,1,2$.

The Grothendieck-Witt group is the 0th graded piece of Milnor-Witt K-theory, $M_*^{MW}(k)$, which is also a homotopy group of spheres in $\AA^1$ homotopy theory (due to Hopkins and Morel). 

This group has generators
$$\begin{align*}
\generators{a}, &\quad a\in k^\times, &\deg a = 1\\
\eta, & & \quad\deg \eta = -1
\end{align*}$$

and relations
$$\begin{align*}
\eta \generators{a} &= \generators{a} \eta\\
\generators{a}\generators{1-a} &= 0&\\
\generators{ab} &= \generators{a} + \generators{b} + \eta \generators{a}\generators{b}\\
\eta h &= 0
\end{align*}$$

where $h$ is the same as earlier, but since it's in the wrong group, we need to define this using the isomorphism
$$\begin{align*}
G W ( k ) &\cong K _ { 0 } ^ { MW } ( k ) \\
\generators{a} &\mapsto 1 + n \generators{a}\\
h\definedas \generators{1} + \generators{-1} &\mapsto 2 + \eta\generators{-1}\definedas h.
\end{align*}$$

# Degree Theorem
This theorem says that $\eta$ corresponds to a Hopf map.

**Theorem (Morel):**
$$
[(S^1)^{\wedge n} \wedge (\GG_m)^{\wedge j},~ (S^1)^{\wedge n} \wedge (\GG_m)^{\wedge r}] \cong K^{MW}_{r-j}
$$

where the square brackets correspond to homotopy classes of maps. In particular, when $j=r=n$, we obtain
$$
[\PP^n /\PP^{n-1},~ \PP^n /\PP^{n-1}] \cong GW(k)
$$

> This is a fantastic theorem, which we will see again later when doing oriented Chow groups.

A nice consequence is that if we let $k=\RR$, the degrees behave nicely, characterized by the commutativity of this diagram:
$$
\begin{CD}
[S^{2n},~S^{2n}] @<\CC\dash\text{points}<< [\PP^n /\PP^{n-1},~ \PP^n /\PP^{n-1}] @>\RR\dash\text{points}>> [S^n,~S^n] \\
@VV\deg V \selfmap @VV\deg V \selfmap @VV\deg V \\
\ZZ @<<\text{rank}< GW(k) @>>\text{signature}> \ZZ
\end{CD}
$$

where the edge degree maps are just the topological degree of maps between spheres and the middle is the $\AA^1$ degree. The signature is the usual difference in $\pm 1$s occurring after diagonalization. Thus $GW(k)$ lets us simultaneously read off the real and complex degrees of maps between schemes over $\RR$.

So these homotopy groups are actually homotopy sheaves (not just global sections of sheaves), where we can form a sheaf by taking smash with $U^+$ and sheafifying. Thus $GW(k), K^{MW}_*(k),$ and $K^M_*(k)$ are all global sections of sheaves.

There is a procedure in Morel's book for producing an unramified sheaf $K^{MW}_*$ from the values on fields, i.e. $K^{MW}_*(E)$ for some $E \supset k$ of finite type. It proceeds as follows:

We want to know what the sections are on some scheme $Y$, so we look at its function field and check $K^MW_*$ on it to see which sections are defined over all of $Y$ and not over the generic point. This produces the additional data of boundary/residue maps that determine when sections extend globally. 

So let $V:E \to \ZZ \union \theset\infty$ be a valuation and $\mathcal O_V = \theset{e\in E \suchthat V(e) \geq 0}$ and choose a uniformizer $\pi$ such that $v(\pi)=1$. Then form the residue field $k(V) \definedas \mathcal O_V / \generators{\pi}$. Then this residue map plus the sections will allow us to define a sheaf, so let
$$\begin{align*}
\del_V^\pi: K_*^{MW}(E) &\to K_*^{MW}(k(V))[-1]\\
\generators{\pi}\generators{a_1}\cdots\generators{a_n} &\mapsto \generators{\overline a_1} \cdots\generators{\overline a_n} \\
\generators{a_1} \cdots \generators{a_n} &\mapsto 0
\end{align*}$$
where $a_i \in \mathcal{O}_V^\times$ and $\overline a_i$ is the reduction.

So then the sections on $\mathcal O$ are given by
$$
K^{MW}_*(\mathcal O_V) \definedas \ker \del_V^\pi
$$



