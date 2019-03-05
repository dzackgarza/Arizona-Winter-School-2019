# Review
Let $Y \to \spec(\FF_q)$ be some algebro-geometric object defined over $\FF_q$ -- one can have an algebraic variety in mind, but this is geared towards an algebraic stack such as the moduli stack of $G\dash$bundles on an algebraic curve.

We can then look at the $\FF_q\dash$valued points of $Y$, $Y(\FF_q)$, and we think of stacks as categories, where we can measure the size of this category in the following way:
$$
\abs{Y(\FF_q)} = \sum_{y\in Y(\FF_q)} \frac{1}{\abs{\Aut(y)}}
$$

where the sum is over the objects in this category, with one term from each isomorphism class.

As a special case, let $Y$ be a smooth algebraic stack of dimension $d$, which means that it is locally an algebraic variety (i.e. it admits a submersive map from an algebraic variety) where this variety is smooth.

Definition: $Y$ satisfies the Grothendieck-Lefschetz trace formula (GL) if the number of $\FF_q$ points on $Y$ is given by some formula involving the trace of the Frobenius $\varphi$ on cohomology, i.e.
$$\begin{align*}
\frac{\abs{Y(\FF_q)}}{q^d} &= \tr(\varphi^{-1} \mid H^*(\bar Y))\\
& \definedas \sum_i (-1)^i\tr(\varphi^{-1} \mid H^i(\bar Y))
\end{align*}$$

where $q^d$ is the naive estimate of how many $\FF_q$ points there are in $Y$ and 
$$
\bar Y = Y \underset{\spec(\bar\FF_q)}\cross\spec(\bar \FF_q),
$$

so the bar notation just means extending scalars up to the algebraic closure of the underlying field.

This definition makes sense because we can ask about the $\ell\dash$adic cohomology of $\bar Y$, which is some$\QQ_\ell\dash$vector space with an automorphism called the Frobenius, and so we can take its inverse and trace.

The classical GL trace formula says this is true for $Y$ an algebraic variety, and we want an analog for stacks. We'll go through this for a moduli stack of $G\dash$ bundles not on a curve, but just on a point.

Example: Let $G$ be a linear algebraic group over $\FF_q$ and $Y=BG$, the classifying stack of $G$, which is characterized by the equivalence
$$
\pmatrix{\text{Maps } \\ \spec(R) \to BG} \iff \pmatrix{\text{Principal $G\dash$bundles}\\\text{on $\spec(R)$} }
$$

for any $\FF_q\dash$algebra $R$.

A more specific example: let $G = \GG_m$, the multiplicative group, and $Y =B\GG_m$ so that an $R\dash$valued point of $Y$ is just an invertible $R\dash$module. 

What is $Y(\FF_q)$? This is the category of 1-dimensional $\FF_q\dash$vector spaces -- so up to isomorphism, there's only one object in this category, but it has a group of symmetries $\Aut \FF_q = \FF_q^\times$ the group of units. We thus obtain
$$
\abs{Y(\FF_q)} = \sum_{y\in Y(\FF_q)} \frac{1}{\abs{\Aut(y)}} = \frac{1}{\abs{\FF_q^\times}} = \frac{1}{q-1}.
$$

We then need to check what the dimension $d=\dim B\GG_m$ is. We regard $B\GG_m$ as what you get by taking the point (here $\spec \FF_q$) and mod out by the (trivial?) action of $\GG_m$, i.e.
$$
B\GG_m = \pt / \GG_m
$$