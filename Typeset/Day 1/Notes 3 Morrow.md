# Topological Hochschild Homology  in Arithmetic Geometry

Goals:
- Describe Hochschild and cyclic homology using a classical approach
- Describe the "Topological" counterparts
- Relate these to Algebraic and Arithmetic Geometry

# Classical Theory

This only depends on basic homological algebra, but becomes a bit more interesting when objects with a "perfectoid" flavor are input.

Fix a commutative ring $k$, then for any $k\dash$ algebra $A$ we can form the Hochschild complex
$$
HH(A/k) \definedas A \xleftarrow{\del_1} A^{\tensor_k 2} \xleftarrow{\del_2} A^{\tensor_k 3}\to \cdots \\
~ \\
\del_1(a_0 \tensor a_1) = a_0a_1 - a_1a_0 \\
\del_2(a_0\tensor a_1\tensor a_2) = a_0a_1 \tensor a_2 -a_1a_2\tensor a_3 + a_2a_0\tensor a_1 \\
\vdots
$$

Then by definition, the Hochschild homology groups $HH_n(A/k)$ are obtained by taking the homology of this complex.

Example: 
- $HH_0(A/k) = A/<ab-ba> = A/[A,A] = A$ when $A$ is commutative.
- $HH_1(A/k) = A\tensor_k A / <ab\tensor c - a\tensor bc + ac\tensor b> = \Omega_1$
  - Note that the ideal appearing here is the Leibniz rule from differential forms
