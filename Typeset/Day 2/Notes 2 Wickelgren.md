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

We want colimits, so we add them: let $\Sm$ to be the smooth schemes over $k$. There is a Yoneda embedding
$$
\Sm \mapsvia{Y} \mathrm{Func}(\Sm^\text{op}, \mathrm{Sset}) \\
X \mapsto \hom(\wait, X)
$$

where one might normally require the target to be sets, but since we'd like homotopy colimits and to be able to do things analogous to fibrant/cofibrant replacements, we aim for simplicial sets instead. These can essentially be regarded as topological spaces.

> Note: This looks a lot like sending a scheme to a its presheaves.

We're building a homotopy theory, which can mean
- A simplicial model category
  - Here we have simplicial sets, notions of fibrations/cofibrations, weak equivalences, etc
- 