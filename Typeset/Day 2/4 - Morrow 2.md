Last time: some general tools that are required to perform constructions like Hochschild homology in greater generality when one can't write down explicit complexes. We had a cyclic object, which leads to $S^1$ acting on something like a complex, and how you can pass from this action to homology, cohomology, and a Tate construction. When we fed Hochschild homology into this, the output was what we saw in earlier lectures: cyclic homology, negative cyclic homology, and periodic cyclic homology.

Why do we want to perform this construction in greater generality, and what information can we expect to extract from it?

Let $A$ be a $k\dash$algebra, and $D(k)$ be a complex of $k\dash$modules. So far we've been looking at these and tensoring things together over $k$, and in this world we built Hochschild homology: $HH(A/k) \in (D(k), \tensor_k)$. 

We also have $(D(k), \tensor_k) ``\subseteq" (D(\ZZ), \tensor_\ZZ)$ , where this "inclusion" appears because any complex of $k\dash$modules is also a complex of abelian groups. It is also the case that the $k\dash$algebra $A$ is also a $\ZZ\dash$algebra, i.e. a ring, by forgetting the $k\dash$linear structure. So in this world, we can take $HH(A/\ZZ)$, which is in some sense richer in the sense that it can recover $HH(A/k)$. In particular, we have
$$
HH(A/k) = HH(A/\ZZ) \underset{HH(k/\ZZ)}\tensor k,
$$ 

where we can form this tensor product because $k$ itself is a $\ZZ\dash$algebra.

In order to make sense of the object on the RHS, it is perhaps easiest to view everything as a simplicial ring, which can be tensored together by tensoring what happens term-wise. This will be an on-the-nose equality when some extra flatness conditions are applied; otherwise it will be some equivalence.

To check this equality, the objects on each side have the following forms
$$
A^{n\tensor_k} \leftrightarrow A^{n\tensor_\ZZ} \underset{m^{\tensor_\ZZ}}{\tensor} k
$$

where tensoring with $k$ is just by the multiplication map. The claim is that these two are the same.

The $\from$ map is given by just replacing $\tensor_\ZZ$ with $\tensor_k$ everywhere. For the $\to$ map, if we map some symbol $A_0 \times \cdots \times A_n$ to the RHS, the fact that $\wait \underset{m^{\tensor_\ZZ}}{\tensor} k$ is modding out by the kernel of the multiplication map exactly imposes $k\dash$bilinearity between the tensor symbols. This yields a $k\dash$bilinear map, which produces an actual map on the tensor product over $k$.

The question then becomes: how far can we carry out this process? Is there an even richer setting in which we can carry out these constructions, something of the form $(\wait, \tensor)?$ The structures we would need are:

- The structure must be symmetric monoidal 
  - This essentially says that there is some operation that behaves like tensoring and satisfies the properties we know and love. 
- Limits and colimits should exist
  - So we can form cyclic/periodic-cyclic homology and so on, which as we saw earlier involved taking limits over diagrams involving $BS^1$.
- $\cdots$, some other technical assumptions
- A differential-graded category
  - Need some homotopically rich framework, since in the original derived categories we produced complexes, and we were interested in quasi-isomorphisms and equivalences between these complexes, so not just any category will do.

Can such a thing exist? The answer is no! In some sense, $D(\ZZ)$ is the best we can do -- in the world of d.g. categories, $D(\ZZ)$ is characterized as an initial object. If any other such category $C$ is produced, then tensoring a map $C \to D(\ZZ)$ yields a restriction/inclusion in the other direction.

So we need to relax some of the conditions, i.e. by replacing d.g. categories with a simplicial or $\infty\dash$category, which have less strong linearity conditions on the hom-sets. Then there is something better, and the best we can do is the category of spectra $D(\Sp)$, which we're supposed to think of as some kind of derived category over the sphere spectrum. This has a similar initial property as $D(\ZZ)$.

This was an idea of Goodwillie and Voudhousen(?) in the 80s/90s that one should try to transport the construction of HH beyond the algebraic case and into the world of spectra and ring spectra, where we expect that repeating the construction would yield better information. 

What is better information? Here are a few pathologies.

- Consider $\FF_p$, then 
$$
HP_0(\FF_p) = \FF_p  \underset{\FF_p}\tensor \cdots \underset{\FF_p }\tensor \FF_p = \FF_p \\
HP_0(\FF_p/\ZZ) = \Zp \oplus \text{ junk}
$$

where in the second line, tensoring copies of $\FF_p$ together naively over $\ZZ$ would again collapse, but instead taking **derived tensor product** yields something more interesting. The "junk" appearing is in fact quite bad -- period cyclic homology was built out of piling up copies of cyclic homology shifted by different degrees. You get $(\ZpZ)^n$ at different stages, which build up to $\Zp$, but at each finite stage there is already some junk, and an inverse limit of junk is also junk. In fact, the limiting junk is bad -- at each stage, you may differ from $(\ZpZ)^n$ by something controllable, but the limiting junk is not killed by a power of $p$ -- and thus come in the form of junky $\Zp\dash$modules.

However, when we repeat our constructions in the world of spectra, this junk term goes away.

# $THH = HH(\wait, \Sp)$ of $\FF_p\dash$algebras

Although the objects we're dealing with are unfamiliar, the following theorem lets you manipulate these objects using algebraic techniques.

Theorem (Bokstedt): $THH_\text{odd}(\FF_p) = 0$ and $THH_\text{even}(\FF_p) = \FF_p[u]$ where $u\in THH_2(FF_p)$

The first part comes from computing the homotopy groups of the spectrum (and the result is something we also saw for HH), while the second part is due to the fact that $THH_2$ is a one-dimensional $\FF_p\dash$vector space, so we can just pick a generator and then multiplication is given in a polynomial fashion.

Corollary: for any $\FF_p\dash$ algebra $A$, we get a fiber sequence (or distinguished triangle)

$$
THH(A)[z] \mapsvia{x\mapsto xu} THH(A) \to HH(A/\FF_p)
$$

The first term is $THH(A)$ shifted by a bit, while what's left on the RHS is the usual $HH$ we saw in earlier lectures. If we're convinced that the same sort of algebraic manipulations as earlier continues to work in the world of spectra, we get
$$
HH(A/\FF_p) = THH(A) \underset{} \tensor \FF_p
$$