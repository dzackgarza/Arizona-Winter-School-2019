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

**Theorem (Bokstedt):** 
$THH_\text{odd}(\FF_p) = 0$ and $THH_\text{even}(\FF_p) = \FF_p[u]$ where $u\in THH_2(FF_p)$

The first part comes from computing the homotopy groups of the spectrum (and the result is something we also saw for HH), while the second part is due to the fact that $THH_2$ is a one-dimensional $\FF_p\dash$vector space, so we can just pick a generator and then multiplication is given in a polynomial fashion.

Corollary: for any $\FF_p\dash$ algebra $A$, we get a fiber sequence (or distinguished triangle)

$$
THH(A)[2] \mapsvia{x\mapsto xu} THH(A) \to HH(A/\FF_p)
$$

The first term is $THH(A)$ shifted by a bit, while what's left on the RHS is the usual $HH$ we saw in earlier lectures. If we're convinced that the same sort of algebraic manipulations as earlier continues to work in the world of spectra, we get
$$
HH(A/\FF_p) = THH(A) \underset{THH(\FF_p)} \tensor \FF_p
$$

which witnesses the fact that $THH(A)$ is strictly richer than $HH(A/\FF_p)$; we can recover the former from the latter.

But reading off the previous theorem, in order to kill all of $THH(\FF_p)$, apart from the initial $\FF_p$ in degree zero, we just have to kill $u$, and so by abuse of notation,
$$
THH(A) \underset{THH(\FF_p)} \tensor \FF_p = THH(A) / \generators{u}
$$

(where this abuse is, to some extent, allowed in this game.)

This allows us to study $HH(A/\FF_p)$, which we addressed in earlier lectures, in terms of $THH(A)$ and this class $u$.

If go take homotopy groups, we get a long exact sequence, so we can see what this buys us in the world of abelian groups:
$$
THH_0(A) \cong HH_0(A/\FF_p) = A \\
THH_1(A) \cong HH_1(A/\FF_p) = \Omega_{A/\FF_p}^1 \\
$$

we explicitly get the long exact sequence
$$
\cdots THH_1(A) \to THH_3(A) \to HH_3(A/\FF_p)
\to THH_0(A) \to THH_2(A) \to HH_2(A/\FF_p) \to 0
$$

where we can identify $THH_0, THH_1$ as before and in some sense, the $THH$ are built up out of multiple copies of $HH$. For example, $THH_2$ gets a contribution from $HH_2$ and $THH_0 = HH_0$. Similarly, $THH_3$ has a contribution from $HH_3$ and $THH_1 = HH_1$. So continuing upwards, each $THH$ encodes some data about all of the lower $HH$ and building them together.

The case in which one can most clearly see the way this builds up is when $A$ is a smooth $k\dash$algebra, where we computed how $HH$ of these looked in the first talk. We have an analogous result:

**Theorem (Hesselholt's Hochschild-Kostent-Rosenburg):**
If $A$ is a smooth $\FF_p\dash$algebra then 
$$
THH_*(A) \cong \Omega^*_{A/\FF_p} \underset{\FF_p[u]}\tensor \FF_p[u]
$$

where the LHS is a graded algebra of $THH$ groups and the RHS contains the differential forms seen in previous HKR theorems, along with a contribution arising from functoriality and the fact that $\FF_p \to A$ yielding a map $THH(\FF_p)\to  THH(A)$, and looks like a polynomial algebra.

More precisely, we have 
$$
THH_n(A) = \bigoplus_{i=1}^{\left \lfloor{n\over 2}\right \rfloor } \Omega_{A/\FF_p}^{n-2i}.
$$

Proof: Using the long exact sequence we have
$$
\cdots \to THH_{n-2}(A) \to THH_n(A) \to HH_n(A/\FF_p) \to \cdots
$$

We also have the classical HKR isomorphism $HH_n(A/\FF_p) \cong \Omega^n_{A/\FF_p}$. But since $\Omega$ is appearing in $THH_1$, the multiplicative structure produces for us a map $\Omega^n_{A/\FF_p} \to THH_n(A)$ by multiplying together $n$ times the map $\Omega^1 \to THH_1$.

But then $THH_n \surjects HH_n$, which means that the LES breaks into SESs by using the surjectivity at the $n$ and $n+1$ levels and adding zeros at the sides of level $n$. The result will then follow by induction, since we already have the result in degrees 0 and 1. As we run up the sequence, we'll find that as long as $THH_{n-2}$ is described by the sum above, then in order to pass to $THH_n$, we just need to add a copy of $\Omega_n$.

This may initially look bizarre -- it was very attractive in $HH$ that each group was just given by a bunch of differential forms in the expected degree, while here we have them shifted in different degrees. This actually works out perfectly. We'll look at topological periodic cyclic homology in a moment, which is built by taking the limit of multiple copies of cyclic homology piled on top of one another, and what will happen is that all of these different differential forms will exactly align to sit on top of one another and produce (in the limit) crystalline cohomology. If you view this as represented by the deRham-Witt complex, then you have a canonical $p\dash$adic filtration on this complex and all of the pieces look like copies of the deRham complex of your original algebra. So we need all of these copies of the deRham complex at the starting point in order for things to build up correctly and yield something interesting.

# The Periodic Theory $TP(\FF_p)$

Recall that this was obtained as $TP(\FF_p) = THH(\FF_p)^{tS^1}$, where we can think of this as equal to $HP(\FF_p/\Sp)$ where $tS^1$ denotes taking the Tate construction. In the algebraic setup, we defined $HP$ in terms of an explicit double complex which produces a spectral sequence. This sequence converges from the homology of the columns ($HH$) to $HP$. There is similarly a spectral sequence associated to this Tate construction, which can be reindexed to look exactly the same (to the horror of many topologists):

$$
\begin{CD}
  \ddots @. \vdots @. \vdots @. \vdots @. \vdots @. ~\rotate{\ddots} \\
  @. @VVV @VVV @VVV @VVV @.\\
  \cdots @. \color{blue}\FF_p[u]^2 @<<< \cdot @<<< \FF_p[u] @<<< \cdot @. \cdots \\
  @. @VVV @VVV @VVV @VVV @.\\
  \cdots @. \cdot @<<< \color{blue}\FF_p[u] @<<< \cdot @<<< \FF_p @. \cdots \\
  @. @VVV @VVV @VVV @. @.\\
  \cdots @. \FF_p[u] @<<< \cdot @<<< \color{blue}\FF_p @. \cdot @. \cdots \\
  @. @VVV @VVV @. @. @.\\
  \cdots @. \cdot @<<< \FF_p @. \cdot @. \cdot @. \cdots \\
  @. @VVV @. @. @. @.\\
  \cdots @. \FF_p @. \cdot @. \cdot @. \cdot @. \cdots \\
  @. @. @. @. @. @. \\
  \rotate{\ddots} @. \vdots @. \vdots @. \vdots @. \vdots @. \ddots
\end{CD}
$$

Here we just put $THH(\FF_p)$ in each of the columns, where we use the Bokstedt theorem that shows that these vanish in odd degree. We also know that there's a copy of $\FF_p[u]$ in each even degree, and we just use the powers to keep track of the multiplicative structure.

This converges to $TP(\FF_p)$, where we repeat the classical theory and "sum" along the diagonals, although we need to solve some extension problems. In particular, the blue terms yield $TP_0(\FF_p)$. This is because there are no nontrivial differentials -- since it's only supported in even bidegree, every differential either comes from something zero or targets a zero.

So $TP_0$ again contains most of the information, which is a completed filtered ring with associated graded pieces given by $\FF_p[u]. So the question is how we can add up copies of $\FF_p$ in various degrees and end up with a ring. There are two possibilities:
- We failed, and we just get $\FF_p[[u]]$, or
- We get $\Zp$.

Fortunately, life is good, and the latter case happens! We thus get a theorem, $TP_0(\FF_p) = \Zp$. Checking this isn't terribly difficult.

In particular, we have a class $u\in \FF_p[u]$, which is going to give us some element in the first step of the filtration of $TP_0$. Either it is getting sent to an element of $TP_0$ which is killed by $p$, according to the first case, or it's getting sent to some multiple of $p$ (note that $TP_0$ is in fact a ring, so it could get sent to $p$). So we only need to look at where $u$ goes in this very low degree part of the spectral sequence.
As it turns out, $THH$ is surprisingly close to classical $HH$ in very low degrees, and so in the degrees that control this extension problem, you can work with and resolve this at the level of classical $HH$. This gives you exactly the amount of information needed to determine which way $u$ acts.

But in fact, the spectral sequence is period, and so what happens along this diagonal happens along every diagonal, and we thus obtain the theorem $TP_*(\FF_p) = \Zp[\sigma^{\pm 1}]$ where $\sigma$ is any generator of the free $\Zp\dash$module $TP_2(\FF_p)$. So it's a nice, 2-periodic cohomology theory.

Now similarly, as from Bokstedt's theorem we got a consequence for arbitrary $\FF_p\dash$algebras, we will similarly find some consequence for $TP(A)$ for $A$ and arbitrary $\FF_p\dash$algebra just by knowing what happens in $TP(\FF_p)$. We now look at the consequences for such an $A$.




