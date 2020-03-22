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
