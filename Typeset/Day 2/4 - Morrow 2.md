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

The $\from$ map is given by just replacing $\tensor_\ZZ$ with $\tensor_k$ everywhere. For the $\to$ map, the fact that $\wait \underset{m^{\tensor_\ZZ}}{\tensor} k$ is modding out by the kernel of the multiplication map exactly imposes $k\dash$linearity. This yields a $k\dash$bilinear map, which produces an actual