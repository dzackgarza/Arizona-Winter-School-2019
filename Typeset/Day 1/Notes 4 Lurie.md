# Review
Let $Y \to \spec(\FF_q)$ be some algebro-geometric object defined over $\FF_q$ -- one can have an algebraic variety in mind, but this is geared towards an algebraic stack such as the moduli stack of $G\dash$bundles on an algebraic curve.

We can then look at the $\FF_q\dash$valued points of $Y$, $Y(\FF_q)$, and we think of stacks as categories, where we can measure the size of this category in the following way:
$$
\abs{Y(\FF_q)} = \sum_{y\in Y(\FF_q)} \frac{1}{\abs{\Aut(y)}}
$$

where the sum is over the objects in this category, with one term from each isomorphism class.

As a special case, let $Y$ be smooth of dimension $d$.

Definition: $Y$ satisfies the Grothendieck-Lefschetz trace formula (GL) if the number of $\FF_q$ points on $Y$ is given by some formula involving the trace of the Frobenius on cohomology