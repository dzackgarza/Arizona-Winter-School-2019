---
title: 'A1 Enumerative Geometry'
author: 'Kirsten Wickelgren'
date: 'March 9, 2019'
output:
    custom_document: {path: Wickelgren.tex, pandoc_args: ['-r', markdown+tex_math_dollars+simple_tables+table_captions+yaml_metadata_block+smart, '-t', latex, '--template=/home/zack/Notes/Latex/pandoc_template.tex']}
---  
  
  
Arizona Winter School 2019
Speaker: Kirsten Wickelgren
Topic: <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Enumerative Geometry
  
- [Lecture 1](#lecture-1 )
- [Lecture 2](#lecture-2 )
- [Lecture 3](#lecture-3 )
- [Lecture 4](#lecture-4 )
  
# Lecture 1
  
  
# <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Enumerative Geometry
  
  
Enumerative geometry counts algebro-geometric objects, and in order to actually obtain an invariant number at the end of the day one uses an algebraically closed field <img src="https://latex.codecogs.com/gif.latex?k"/> or <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/>. This is essentially because the conditions imposed are polynomial, and polynomials of degree <img src="https://latex.codecogs.com/gif.latex?n"/> over a closed field always have <img src="https://latex.codecogs.com/gif.latex?n"/> roots.
  
The goal here is to record information about the fields of definition. However, since we may no longer have invariant numbers as solutions to polynomial equations, we replace this with a notion of *weights* to get an "invariance of bilinear form" principle instead. Over characteristic not 2, we can use quadratic forms, which ties to Lurie's first talk.
  
# Example: Lines on a Smooth Cubic Surface
  
> Joint work with Jesse Kass
  
A **cubic surface** <img src="https://latex.codecogs.com/gif.latex?X"/> consists of the <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/> solutions to a polynomial in three variables, i.e. 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?X%20=%20&#x5C;theset{(x,y,z)%20&#x5C;in%20&#x5C;CC^3%20&#x5C;suchthat%20f(x,y,z)%20=%200},"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?f"/> is degree 3. In general, we want to compactify, so we view <img src="https://latex.codecogs.com/gif.latex?X%20&#x5C;injects%20&#x5C;CP^3"/> as
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;CP^3%20=%20&#x5C;theset{&#x5C;vector%20x%20=%20[w,x,y,z]&#x5C;neq%20&#x5C;vector%200%20&#x5C;suchthat%20&#x5C;forall%20&#x5C;lambda%20&#x5C;in%20&#x5C;CC^&#x5C;times,~&#x5C;vector%20x%20=%20&#x5C;lambda%20&#x5C;vector%20x}"/></p>  
  
  
and so 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?X%20=%20&#x5C;theset{[w,x,y,z]%20&#x5C;in%20&#x5C;CP^3%20&#x5C;suchthat%20f(w,x,y,z)%20=%200}"/></p>  
  
where <img src="https://latex.codecogs.com/gif.latex?f"/> is homogeneous.
  
The surface <img src="https://latex.codecogs.com/gif.latex?X"/> is **smooth** if the underlying points form a manifold, or equivalently if the partials don't simultaneously vanish.
  
**Theorem (Salmon Cayley 1849):**
If <img src="https://latex.codecogs.com/gif.latex?X"/> is a smooth cubic surface, then <img src="https://latex.codecogs.com/gif.latex?X"/> contains exactly 27 lines.
  
Example: The Fermat cubic <img src="https://latex.codecogs.com/gif.latex?f(w,x,y,z)%20=%20w^3%20+%20x^3%20+%20y^3%20+%20z^3"/>.
  
We can find one line, given by 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?L%20=%20&#x5C;theset{[s,-s,t,-t]%20&#x5C;suchthat%20s,t%20&#x5C;in%20&#x5C;CP^1},"/></p>  
  
  
and in fact this works for any <img src="https://latex.codecogs.com/gif.latex?&#x5C;lambda,%20&#x5C;omega"/> such that <img src="https://latex.codecogs.com/gif.latex?&#x5C;lambda^3%20=%20&#x5C;omega^3%20=%20-1"/>, yielding
<p align="center"><img src="https://latex.codecogs.com/gif.latex?L&#x27;%20=%20&#x5C;theset{[s,&#x5C;lambda%20s,t,&#x5C;omega%20t]%20&#x5C;suchthat%20s,t%20&#x5C;in%20&#x5C;CP^1}."/></p>  
  
  
We can also permute <img src="https://latex.codecogs.com/gif.latex?s,t"/> around to get more lines, and by counting this yields 27 distinct possibilities. (3 choices for <img src="https://latex.codecogs.com/gif.latex?&#x5C;lambda"/>, 3 choices for <img src="https://latex.codecogs.com/gif.latex?&#x5C;omega"/>, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;frac%201%202%20{4&#x5C;choose%202}"/> ways to pair them with the <img src="https://latex.codecogs.com/gif.latex?s,t"/> in the original <img src="https://latex.codecogs.com/gif.latex?L"/>.
  
> There is a proof in the notes that these are the only lines, which is relatively elementary.
  
# Modern Proof
  
We'll use characteristic classes, which we'll later replace by an <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory variant.
  
Let <img src="https://latex.codecogs.com/gif.latex?&#x5C;Gr(1,3)"/> be the Grassmannian parameterizing 1-dimensional subspaces of <img src="https://latex.codecogs.com/gif.latex?&#x5C;CP^3"/>, where the <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/> points of this space parameterize 2-dimensional subspaces <img src="https://latex.codecogs.com/gif.latex?W%20&#x5C;subseteq%20&#x5C;CC^4"/>. This is a moduli space of the lines we're looking for.
  
Let <p align="center"><img src="https://latex.codecogs.com/gif.latex?S%20&#x5C;to%20&#x5C;Gr(1,3)"/></p>  
 be the tautological bundle where the fiber is simply given by <img src="https://latex.codecogs.com/gif.latex?S_W%20=%20W"/>. We can also form the bundle <p align="center"><img src="https://latex.codecogs.com/gif.latex?(&#x5C;sym^3%20S)^&#x5C;dual%20&#x5C;to%20&#x5C;Gr(1,3)"/></p>  
 where the fiber over the point corresponding to <img src="https://latex.codecogs.com/gif.latex?W"/> is all of the cubic polynomials on <img src="https://latex.codecogs.com/gif.latex?W"/>, i.e. <p align="center"><img src="https://latex.codecogs.com/gif.latex?(&#x5C;sym^3%20S)^&#x5C;dual_W%20=%20(&#x5C;sym^3%20W)^&#x5C;dual."/></p>  
  
  
Explicitly, we have the following two bundles to work with:
<p align="center"><img src="https://latex.codecogs.com/gif.latex?W%20&#x5C;to%20S%20&#x5C;to%20&#x5C;Gr(1,3)%20&#x5C;&#x5C;(&#x5C;sym^3%20W)^&#x5C;dual%20&#x5C;to%20(&#x5C;sym^3%20S)^&#x5C;dual%20&#x5C;to%20&#x5C;Gr(1,3)"/></p>  
  
  
Our chosen <img src="https://latex.codecogs.com/gif.latex?f"/> determines an element of <img src="https://latex.codecogs.com/gif.latex?(&#x5C;sym^3%20&#x5C;CC^4)^&#x5C;dual"/>, which is thus a section <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_f"/> of the second bundle above, where
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_f(W)%20=%20&#x5C;restrictionof{f}{W}."/></p>  
  
  
We thus have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;PP%20W%20&#x5C;in%20X%20&#x5C;iff%20&#x5C;sigma_f(W)%20=%200,"/></p>  
  
i.e. the line corresponding to <img src="https://latex.codecogs.com/gif.latex?W"/> is in our surface exactly when this section is zero. We now want to count the zeros of <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_f"/>, which is exactly what the Euler class does.
  
To be precise, the Euler class counts the zeros of a section of a properly oriented vector bundle with a given weight. Let <img src="https://latex.codecogs.com/gif.latex?V&#x5C;to%20M"/> be a rank <img src="https://latex.codecogs.com/gif.latex?r"/> <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR&#x5C;dash"/> vector bundle over a dimension <img src="https://latex.codecogs.com/gif.latex?r"/> real manifold where we assume that <img src="https://latex.codecogs.com/gif.latex?V"/> is oriented. 
  
> We choose <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR"/> here because <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/> is slightly too nice and gives us a preferred orientation (which we'll want to track later.)
  
For any section <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> with only isolated zero, we'll assign a weight to each zero which comes from the topological degree function
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;deg:%20[S^{r-1},%20S^{r-1}]%20&#x5C;to%20&#x5C;ZZ,"/></p>  
  
  
where we use the brackets to denote homotopy classes of maps.
  
Definition: Let <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20M"/> where <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma(p)%20=%200"/>, and define <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_p(&#x5C;sigma)"/> in the following way:
  
Choose local coordinates near <img src="https://latex.codecogs.com/gif.latex?p"/>. Since the zeros are isolated, we can choose a ball <img src="https://latex.codecogs.com/gif.latex?B_&#x5C;varepsilon(p)"/> such that <img src="https://latex.codecogs.com/gif.latex?x&#x5C;in%20B_&#x5C;varepsilon(p)%20-%20&#x5C;theset{p}%20&#x5C;implies%20&#x5C;sigma(x)%20&#x5C;neq%200"/>. Choose a local trivialization of the total space <img src="https://latex.codecogs.com/gif.latex?V"/>. This allows us to view <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma:%20&#x5C;RR^r%20&#x5C;to%20&#x5C;RR^r"/> as a real function.
  
We can choose coordinates such that <img src="https://latex.codecogs.com/gif.latex?p%20=%200"/> in the domain, so <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma(0)%20=%200"/>, and moreover the image <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma(B_&#x5C;varepsilon(p))%20=%20&#x5C;RR%20-%20&#x5C;theset{0}"/>. We can then form a function 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;bar&#x5C;sigma:%20&#x5C;del%20B_&#x5C;varepsilon(p)%20=%20S^{r-1}%20&#x5C;to%20S^{r-1}%20=%20&#x5C;del%20&#x5C;sigma(B_&#x5C;varepsilon(p))%20&#x5C;&#x5C;x%20&#x5C;mapsto%20&#x5C;frac{&#x5C;sigma(x)}%20{&#x5C;norm{&#x5C;sigma(x)}},"/></p>  
  
  
and so we can take <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_p(&#x5C;sigma)%20&#x5C;definedas%20&#x5C;deg%20&#x5C;bar%20&#x5C;sigma"/>.
  
There is indeterminacy here up to elements of <img src="https://latex.codecogs.com/gif.latex?&#x5C;GL(r,%20&#x5C;RR)"/> which could possibly effect the sign, however, but this can be fixed using the assumption that <img src="https://latex.codecogs.com/gif.latex?V"/> is oriented and choosing local trivializations for which the orientations are compatible. This gives us a well-defined local degree of a section at a zero.
  
The Euler class, which only depends on the bundle and not the section, is given by 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?e(V)%20=%20&#x5C;sum_{p&#x5C;suchthat%20&#x5C;sigma(p)%20=%200}%20&#x5C;deg_p(&#x5C;sigma)."/></p>  
  
  
It can be shown that because <img src="https://latex.codecogs.com/gif.latex?X"/> is smooth, the zeros are all simple and so in the complex case, the degrees are all 1. We thus obtain
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;abs{&#x5C;theset{&#x5C;text{lines%20on%20}%20X}}%20=%20e((&#x5C;sym^3%20S)^&#x5C;dual),"/></p>  
  
  
where the RHS is independent of <img src="https://latex.codecogs.com/gif.latex?X"/> and can be computed using the splitting principle and the cohomology of <img src="https://latex.codecogs.com/gif.latex?&#x5C;Gr"/>.
  
# What about <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR"/>?
  
  
Schlafli, 19th century: <img src="https://latex.codecogs.com/gif.latex?X"/> can have <img src="https://latex.codecogs.com/gif.latex?3,7,15"/> or <img src="https://latex.codecogs.com/gif.latex?27"/> lines. So it's not constant, and thus there's not an invariant number here, but Segre (1942) distinguished between hyperbolic and elliptic lines.
  
Recall the characterization of elements in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Aut%20L"/> for <img src="https://latex.codecogs.com/gif.latex?L=&#x5C;RP^1"/> (real lines) as elliptic/hyperbolic: we have <img src="https://latex.codecogs.com/gif.latex?&#x5C;Aut%20L%20&#x5C;cong%20&#x5C;mathrm{PGL}(2,%20&#x5C;RR)"/>, so pick some <img src="https://latex.codecogs.com/gif.latex?I"/> corresponding to a matrix
<p align="center"><img src="https://latex.codecogs.com/gif.latex?[I]%20=%20&#x5C;begin{pmatrix}a%20&amp;%20b%20&#x5C;&#x5C;%20c%20&amp;%20d&#x5C;end{pmatrix},&#x5C;quad%20%20z&#x5C;mapsto%20&#x5C;frac{az+b}{cz+d}"/></p>  
  
  
where the second formulation above shows that there are two fixed points, since solving for <img src="https://latex.codecogs.com/gif.latex?z&#x5C;mapsto%20z"/> yields a quadratic equation. So we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Fix}(I)%20=%20&#x5C;theset{z%20&#x5C;in%20&#x5C;CC%20&#x5C;suchthat%20cz^2%20+%20(d-z)z%20+%20b%20=%200},"/></p>  
  
and we characterize <img src="https://latex.codecogs.com/gif.latex?I"/> by the following cases:
- <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Fix}(I)"/> contains two real points: hyperbolic
- A complex conjugate pair: elliptic
  
So we'll associate an involution to <img src="https://latex.codecogs.com/gif.latex?L"/>, and port over these notions of hyperbolic/elliptic. As we'll see later, for each point on <img src="https://latex.codecogs.com/gif.latex?L"/>, there will be a unique other point that has the tangent space, and this involution will swap them.
  
Let <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20L"/>, and consider <img src="https://latex.codecogs.com/gif.latex?T_pX%20&#x5C;intersect%20X"/> . Since <img src="https://latex.codecogs.com/gif.latex?L"/> is in both of the varieties we're intersecting here, and we can apply Bezout's theorem, we know that its complement will some degree 2 variety <img src="https://latex.codecogs.com/gif.latex?Q"/> (since the total degree is 3).
  
So we can write <img src="https://latex.codecogs.com/gif.latex?T_pX%20&#x5C;intersect%20X%20=%20L%20&#x5C;union%20Q"/>. We know that <img src="https://latex.codecogs.com/gif.latex?L%20&#x5C;intersect%20Q"/> will be the intersection of a degree 1 and a degree 2 curve, which will have 2 points of intersection. At one of these points, say <img src="https://latex.codecogs.com/gif.latex?p"/>, <img src="https://latex.codecogs.com/gif.latex?Q"/> and <img src="https://latex.codecogs.com/gif.latex?L"/> will intersect transversally, and so the tangent vectors <img src="https://latex.codecogs.com/gif.latex?T_pQ"/> and <img src="https://latex.codecogs.com/gif.latex?T_pL"/> give a 2-dimensional frame, which yields a plane <img src="https://latex.codecogs.com/gif.latex?P%20&#x5C;subseteq%20T_pX"/>. Since <img src="https://latex.codecogs.com/gif.latex?X"/> is smooth, we get equality and <img src="https://latex.codecogs.com/gif.latex?P%20=%20T_pX"/>.
  
This also holds for the second point of intersection, <img src="https://latex.codecogs.com/gif.latex?p&#x27;"/>, and so we take the involution <img src="https://latex.codecogs.com/gif.latex?I(p)%20=%20p&#x27;"/> and vice-versa. We then say <img src="https://latex.codecogs.com/gif.latex?L"/> is elliptic/hyperbolic exactly when <img src="https://latex.codecogs.com/gif.latex?I"/> is.
  
A natural way to see that there should be a distinction between two types of lines is to use spin structures. Consider a physical cubic surface sitting inside <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR^3"/>, and push the tangent plane alone a line. There are two things that can happen -- one is a twisting by a nontrivial element of <img src="https://latex.codecogs.com/gif.latex?&#x5C;pi_1%20SO_3(&#x5C;RR)"/>, the other is no twisting at all.
  
Example: Look at the Fermat cubic surface <img src="https://latex.codecogs.com/gif.latex?x^3+y^3+z^3=-1"/>
  
![](../assets/2019-03-03-22-11-15.png )
  
Interpretation of this image: <img src="https://latex.codecogs.com/gif.latex?X%20&#x5C;subset%20&#x5C;RR^3"/> is a surface, which has 3 lines that are contained in a plane. We this view <img src="https://latex.codecogs.com/gif.latex?X"/> from above this plane, marking a plus/minus to denote the relative height of the surface within each bounded region. Plus denotes part of the surface that bubbles up over the plane, having positive height/<img src="https://latex.codecogs.com/gif.latex?z"/> coordinates, etc.
  
> This took me a while to visualize -- what worked for me was thinking about "egg crate" padding:
  
![](../assets/2019-03-03-22-27-49.png )
  
After thinking about what physically happens as you push a plane around, it becomes clear that these three lines are all hyperbolic. Note that this question is the same as asking if a path in the frame bundle lifts.
  
Although the number of lines isn't a constant, we can take a "signature" sort of formula to obtain an invariant. In this case, the number hyperbolic lines minus the number of elliptic lines *is* constant. In this case, the constant is 3.
  
General mantra for <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory: if you have a result that works over <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/> and <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR"/>, it may be a result in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> theory that has realizations recovering the original results.
  
# <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Homotopy Theory
  
This will allow us to do with schemes much of what we can do in <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{Top}"/>. Smooth schemes behave like manifolds, where there are balls around points. The convention here will be that we're working over smooth schemes, denoted <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Sm}_k"/> where <img src="https://latex.codecogs.com/gif.latex?k"/> is a field.
  
> Remark: in my notation I use <img src="https://latex.codecogs.com/gif.latex?&#x5C;RP^n,%20&#x5C;CP^n"/>, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n(k)"/> to denote various projective spaces. I'll adopt Kirsten's convention here and just denote <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n(k)"/> as <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n"/>.
  
We'll get spheres from <img src="https://latex.codecogs.com/gif.latex?S_&#x5C;Af^n%20&#x5C;definedas%20&#x5C;PP^n&#x2F;&#x5C;PP^{n-1}"/>.. One nice result due to Morel is that there is a degree map
<p align="center"><img src="https://latex.codecogs.com/gif.latex?[S_&#x5C;Af^n,%20S_&#x5C;Af^n]%20&#x5C;to%20GW(k),"/></p>  
  
  
where the target is not the integers in this case, but rather a group of bilinear forms that are quadratic in characteristic not equal to 2. It is the Grothendieck-Witt group, whose elements are formal difference of bilinear forms. 
  
Thus the group itself is the group completion of nondegenerate symmetric isomorphism classes of bilinear forms <img src="https://latex.codecogs.com/gif.latex?V^2%20&#x5C;to%20k"/> where <img src="https://latex.codecogs.com/gif.latex?V"/> is a finite-dimensional <img src="https://latex.codecogs.com/gif.latex?k&#x5C;dash"/>vector space.
  
The group structure arises because if we have two bilinear forms <img src="https://latex.codecogs.com/gif.latex?B,%20B&#x27;"/> on vector spaces <img src="https://latex.codecogs.com/gif.latex?V,%20W"/> respectively, then we can define a new form on <img src="https://latex.codecogs.com/gif.latex?V%20&#x5C;oplus%20W"/> by working in components and declaring orthogonality between any of the factors. We then take formal differences of these, and inherit a ring structure from the tensor product of forms.
  
Bilinear forms over fields can all be diagonalized, although in characteristic 2, this only holds in a stable sense.
  
# The Grothendieck-Witt Group
  
Since we can diagonalize, the group <img src="https://latex.codecogs.com/gif.latex?GW(k)"/> has a presentation coming from the one dimensional forms. Any of these work as a generator, so we have
  
- Generators: <img src="https://latex.codecogs.com/gif.latex?&lt;a&gt;"/> where <img src="https://latex.codecogs.com/gif.latex?a&#x5C;in%20k^&#x5C;times"/>, corresponding to the form
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&lt;a&gt;%20:%20k^2%20&#x5C;to%20k&#x5C;&#x5C;(x,y)%20&#x5C;mapsto%20axy"/></p>  
  
- Relations: if we change the basis of <img src="https://latex.codecogs.com/gif.latex?k"/> using a multiplication by <img src="https://latex.codecogs.com/gif.latex?b&#x5C;in%20k^&#x5C;times"/>, we get <img src="https://latex.codecogs.com/gif.latex?&lt;ab^2&gt;=&lt;a&gt;"/>. (This means that <img src="https://latex.codecogs.com/gif.latex?a%20&#x5C;in%20k^&#x5C;times&#x2F;(k^&#x5C;times)^2"/>
  - We also get <img src="https://latex.codecogs.com/gif.latex?&lt;a&gt;%20+%20&lt;b&gt;%20=%20&lt;a+b&gt;%20+%20&lt;ab(a+b)&gt;"/>
  
There are many concrete computations of this known for global fields, local fields, finite fields, function fields, etc.
  
**Example:** Computing <img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;CC)"/>.
  
The generators are in bijection with <img src="https://latex.codecogs.com/gif.latex?k^&#x5C;times&#x2F;(k^&#x5C;times)^2"/>, but since every element of <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC"/> is a square, so there's only one element here. We thus obtain
<p align="center"><img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;CC)%20&#x5C;mapsvia{&#x5C;cong}%20&#x5C;ZZ%20&#x5C;&#x5C;&#x5C;beta%20&#x5C;mapsto%20&#x5C;dim%20V"/></p>  
  
  
which is realized by taking the rank.
  
**Example:** <img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;RR)"/>.
We still have the rank, but now we can also take the signature, so we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;RR)%20&#x5C;mapsvia{&#x5C;text{rank}%20&#x5C;times%20&#x5C;text{signature}}%20&#x5C;ZZ^2,"/></p>  
  
  
although a minor parity issue crops up here that can be fixed without damaging the isomorphism type.
  
**Example:** <img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;FF_q)"/>.
We can make a matrix out of how <img src="https://latex.codecogs.com/gif.latex?&#x5C;beta"/> acts on basis elements and take the determinant of it to obtain an invariant called the *discriminant*, and so
<p align="center"><img src="https://latex.codecogs.com/gif.latex?GW(&#x5C;FF_q)%20&#x5C;mapsvia{&#x5C;text{discriminant}%20&#x5C;times%20&#x5C;text{rank}}%20&#x5C;FF_q^&#x5C;times&#x2F;(&#x5C;FF_q^&#x5C;times)^2%20&#x5C;times%20&#x5C;ZZ"/></p>  
  
  
Note that the quotient is needed because we can change basis in <img src="https://latex.codecogs.com/gif.latex?&#x5C;FF_q"/>, which amounts to conjugating by a matrix <img src="https://latex.codecogs.com/gif.latex?A"/>, and so this discriminant is only well-defined up to squares.
  
# Euler Class
  
There is an Euler class in this setting,
<p align="center"><img src="https://latex.codecogs.com/gif.latex?e(V)%20=%20&#x5C;sum_{p&#x5C;suchthat%20&#x5C;sigma(p)%20=%200}%20&#x5C;deg_p(&#x5C;sigma)."/></p>  
  
  
Letting <img src="https://latex.codecogs.com/gif.latex?X"/> be a smooth cubic surface over <img src="https://latex.codecogs.com/gif.latex?k"/>, then a line <img src="https://latex.codecogs.com/gif.latex?L&#x5C;subset%20X"/> will be a closed point of the Grassmannian <img src="https://latex.codecogs.com/gif.latex?&#x5C;Gr(1,3)"/>, so we can think of it as points of the form
<p align="center"><img src="https://latex.codecogs.com/gif.latex?L%20=%20&#x5C;theset{[a,b,c,d]s%20+%20[a&#x27;,b&#x27;,c&#x27;,d&#x27;]t%20&#x5C;suchthat%20s,t%20&#x5C;in%20&#x5C;PP^1(k(L}"/></p>  
  
  
where the extension field <img src="https://latex.codecogs.com/gif.latex?k(L)%20=%20k(a,b,c,d,a&#x27;,b&#x27;,c&#x27;,d&#x27;)"/> is obtained by adjoining the coefficients to <img src="https://latex.codecogs.com/gif.latex?k"/>. 
  
> I think these are always separable, mentioned later in the talk.
  
We thus get
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^1(k(L))%20&#x5C;cong%20L%20&#x5C;underset{&#x5C;substack{&#x5C;text{closed}&#x5C;&#x5C;&#x5C;text{subscheme}}}&#x5C;subseteq%20X_{k(L)}%20&#x5C;subseteq%20&#x5C;PP^3(k(L))."/></p>  
  
  
Given such a line <img src="https://latex.codecogs.com/gif.latex?L&#x5C;subseteq%20X"/>, similar to the real setting, we obtain an involution <img src="https://latex.codecogs.com/gif.latex?I%20&#x5C;in%20&#x5C;Aut%20L%20&#x5C;cong%20PGL(2,%20k(L))"/> after choosing coordinates. We also find that <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Fix}(L)"/> again falls into two cases:
- <img src="https://latex.codecogs.com/gif.latex?2%20k(L)"/> points, or
- 2 conjugate points in some quadratic extension <img src="https://latex.codecogs.com/gif.latex?k(L)[&#x5C;sqrt%20D]"/> where <img src="https://latex.codecogs.com/gif.latex?D%20&#x5C;in%20k(L)^&#x5C;times%20&#x2F;%20(k(L)^&#x5C;times)^2"/>. These correspond to the oddities in the tangent plane in the real case.
  
We then define
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Type}(L)%20=%20&lt;D&gt;%20&#x5C;in%20GW(k(L)),"/></p>  
  
  
or equivalently <img src="https://latex.codecogs.com/gif.latex?D=ab-cd"/> when <img src="https://latex.codecogs.com/gif.latex?I%20=%20&#x5C;begin{pmatrix}a&amp;b&#x5C;&#x5C;c&amp;d&#x5C;end{pmatrix}"/>, in which case <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Type}(L)%20=%20&lt;-1&gt;&#x5C;deg%20I"/>.
  
# An Analogous Trace Formula
  
  
**Theorem:**
Supposing <img src="https://latex.codecogs.com/gif.latex?X"/> is a smooth cubic surface over <img src="https://latex.codecogs.com/gif.latex?k"/> of characteristic not equal to 2, we then have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sum_{L%20&#x5C;in%20X}&#x5C;mathrm{Tr}_{k(L)%20&#x2F;%20k}&#x5C;mathrm{Type}(L)%20=%20&#x5C;text{One%20fixed%20quadratic%20form}%20=%2015&lt;1&gt;%20+%2012&lt;-1&gt;"/></p>  
  
  
where the trace/transfer maps are defined as 
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Tr}_{k(L)%20&#x2F;%20k}:%20GW(k(L))%20&#x5C;to%20GW(k)%20&#x5C;&#x5C;(V^2%20&#x5C;mapsvia{&#x5C;beta}%20k(L))%20&#x5C;mapsto%20(V^2%20&#x5C;mapsvia{&#x5C;beta}%20k)%20&#x5C;circ%20&#x5C;mathrm{Trace}_&#x5C;text{Galois}"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{Trace}_&#x5C;text{Galois}"/> comes from summing the conjugates. Note that we can do this because we can view <img src="https://latex.codecogs.com/gif.latex?V"/> as a vector space over either <img src="https://latex.codecogs.com/gif.latex?k"/> or <img src="https://latex.codecogs.com/gif.latex?k(L)"/>, so we end up with a quadratic form over <img src="https://latex.codecogs.com/gif.latex?k"/>.
  
> Note: we have a well-defined map in the other direction, since the <img src="https://latex.codecogs.com/gif.latex?GW"/> is a stable homotopy group of spheres.
  
**Example:** Let <img src="https://latex.codecogs.com/gif.latex?k=&#x5C;CC"/>, then apply rank to get <img src="https://latex.codecogs.com/gif.latex?15+12=27"/> on the RHS, while since every element is a square, the Type is just 1, so we get 27 total.
  
**Example:** Let <img src="https://latex.codecogs.com/gif.latex?k=&#x5C;RR"/>, apply signature. If <img src="https://latex.codecogs.com/gif.latex?L"/> is defined over <img src="https://latex.codecogs.com/gif.latex?C"/>, so the type is 1, and we're just left with the trace of <img src="https://latex.codecogs.com/gif.latex?&#x5C;CC&#x2F;&#x5C;RR"/> -- but this contributes a <img src="https://latex.codecogs.com/gif.latex?+1"/> and <img src="https://latex.codecogs.com/gif.latex?-1"/>, so there is no contribution. What's left are the lines of <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR"/>, and since we set it up so type 1 lines are hyperbolic, we just get the trace <img src="https://latex.codecogs.com/gif.latex?15-12=3"/>.
  
**Example:** Let <img src="https://latex.codecogs.com/gif.latex?k=&#x5C;FF^q"/>. We can define lines in <img src="https://latex.codecogs.com/gif.latex?&#x5C;FF_q^n"/>, and the "begin a square" partitions <img src="https://latex.codecogs.com/gif.latex?(&#x5C;FF_q^n)^&#x5C;times"/> into two disjoint subsets, we can assign types and we let squares be the hyperbolic elements.
  
We thus get
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mltext{%20%20%20%20&#x5C;text{Elliptic%20lines%20<img src="https://latex.codecogs.com/gif.latex?L"/>%20}%20&#x5C;&#x5C;%20%20%20%20%20%20&#x5C;text{with%20<img src="https://latex.codecogs.com/gif.latex?k(L)%20=%20&amp;#x5C;FF_&amp;#x5C;text{odd}"/>}%20}%20-%20&#x5C;mltext{%20%20%20%20&#x5C;text{Hyperbolic%20lines%20<img src="https://latex.codecogs.com/gif.latex?L"/>}%20&#x5C;&#x5C;%20%20%20%20&#x5C;text{with%20<img src="https://latex.codecogs.com/gif.latex?k(L)%20=%20&amp;#x5C;FF_&amp;#x5C;text{even}"/>}}%20&#x5C;equiv%200%20&#x5C;mod%202"/></p>  
  
  
which follows from computing the discriminant of the given form.
  
  
# Lecture 2
  
  
# User's Guide to <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Homotopy Theory
  
Particularly, arithmetically enriching enumerative results. The first part of this talk focuses on setting up the correct category for this theory.
  
  
## Adding Colimits
  
Recall from last time that we wanted to form a space analogous to a sphere, given by <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n&#x2F;%20&#x5C;PP^{n-1}"/>, which we get from a **colimit**
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}%20%20&#x5C;PP^{n-1}%20@&gt;&gt;&gt;%20&#x5C;PP^n%20&#x5C;&#x5C;%20%20@VVV%20&#x5C;selfmap%20@VVV%20&#x5C;&#x5C;%20%20&#x5C;pt%20@&gt;&gt;&gt;%20&#x5C;PP^n&#x2F;%20&#x5C;PP^{n-1}&#x5C;end{CD}"/></p>  
  
  
which is the same as requiring that for maps from the total space into the quotient, maps coming from the quotiented space and maps coming from the point agree when the compositions are taken.
  
**Example:** Another example of a colimit is the union, which is given by
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}%20%20U&#x5C;intersect%20V%20@&gt;&gt;&gt;%20U%20&#x5C;&#x5C;%20%20@VVV%20&#x5C;selfmap%20@VVV%20&#x5C;&#x5C;%20%20V%20@&gt;&gt;&gt;%20U%20&#x5C;union%20V&#x5C;end{CD}"/></p>  
  
  
These correspond to crushing and gluing operations, which we can do with topological spaces and would like to do with schemes as well. We'd also like smooth schemes to behave like smooth manifolds, in the sense that we can take an open ball around each point. This is part of what <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory buys us.
  
We want colimits, so we add them: let <img src="https://latex.codecogs.com/gif.latex?&#x5C;Sm"/> to be the category of smooth schemes over <img src="https://latex.codecogs.com/gif.latex?k"/>. There is a Yoneda embedding
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;Sm%20&#x5C;mapsvia{Y}%20&#x5C;mathrm{Func}(&#x5C;Sm^&#x5C;text{op},%20&#x5C;mathrm{Sset})%20=%20&#x5C;text{PreSh}(&#x5C;Sm)%20&#x5C;&#x5C;X%20&#x5C;mapsto%20&#x5C;hom(&#x5C;wait,%20X)"/></p>  
  
  
where one might normally require the target to be sets, but since we'd like homotopy colimits and to be able to do things analogous to fibrant/cofibrant replacements, we aim for simplicial sets instead which can essentially be regarded as topological spaces. We can also identify the target with presheaves on the category of smooth schemes.
  
We're building a category for a homotopy theory, which means we need either
- A simplicial model category, or
- An <img src="https://latex.codecogs.com/gif.latex?&#x5C;infty&#x5C;dash"/>category
  
Both have notions of fibrations, cofibrations, an associated homotopy category, weak equivalences, etc, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;text{PreSh}(&#x5C;Sm)"/> has this structure. 
  
## Preserving Old Colimits: Picking a Topology
  
This construction is essentially "freely adding colimits". Since <img src="https://latex.codecogs.com/gif.latex?&#x5C;Sm"/> had colimits (e.g. the union/intersection of open sets), we want <img src="https://latex.codecogs.com/gif.latex?Y"/> to preserve these. We fix this be forcing certain maps to be equivalences using **Bousfield localization**.
  
This is carried out by looking at open covers
<p align="center"><img src="https://latex.codecogs.com/gif.latex?U%20=%20&#x5C;coprod_{&#x5C;alpha}%20U_&#x5C;alpha%20&#x5C;to%20X"/></p>  
  
  
and making a simplicial object out of this map and forcing a weak equivalence
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;text{cos}^0_x%20&#x5C;coprod_&#x5C;alpha%20U_&#x5C;alpha%20&#x5C;mapsvia{&#x5C;homotopic}%20X"/></p>  
  
  
> Note: this may be the Cech nerve, not entirely sure. Pretty sure I got the notation wrong though.
  
This gives us a localization functor
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathrm{PreSh}(&#x5C;Sm)%20&#x5C;mapsvia{L_&#x5C;tau}%20&#x5C;mathrm{Sh}_k"/></p>  
  
  
for <img src="https://latex.codecogs.com/gif.latex?&#x5C;tau"/> a Grothendieck topology which declares certain classes of maps to be covers. We have some choices of topology here, roughly in order of increasing number of open sets:
- Zariski (on schemes)
- Nisnevich
- Etale
  
**Definition:**  A map <img src="https://latex.codecogs.com/gif.latex?f&#x5C;in%20&#x5C;hom(X,Y)%20&#x5C;in%20&#x5C;Sm"/> (not necessarily smooth) is **etale** at a point <img src="https://latex.codecogs.com/gif.latex?x&#x5C;in%20X"/> if the induced map on tangent/cotangent spaces is an isomorphism:
<p align="center"><img src="https://latex.codecogs.com/gif.latex?T_x%20X%20&#x5C;mapsvia{f^*}%20T_{f(x)}Y"/></p>  
  
  
**Definition:** A map <img src="https://latex.codecogs.com/gif.latex?f:%20&#x5C;coprod_&#x5C;alpha%20U_&#x5C;alpha%20&#x5C;to%20X"/> is an **etale cover** if it is etale and surjective
  
**Definition:** A map <img src="https://latex.codecogs.com/gif.latex?f:%20&#x5C;coprod_&#x5C;alpha%20U_&#x5C;alpha%20&#x5C;to%20X"/> is a **Nisnevich cover** if it is an etale cover and <img src="https://latex.codecogs.com/gif.latex?x&#x5C;in%20X%20&#x5C;implies%20&#x5C;exists%20u&#x5C;in%20U%20&#x5C;suchthat%20f^*:%20k(x)%20&#x5C;mapsvia{&#x5C;cong}k(u)"/>.
  
This topology has a few nice properties:
- Smooth schemes have etale maps into <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^n"/>, inclusions/closed immersions <img src="https://latex.codecogs.com/gif.latex?Z%20&#x5C;injects%20X"/> induce maps <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^d%20&#x5C;injects%20&#x5C;Af^n"/>
- Satisfies descent for K-theory
- The cohomological dimension equals the Krull dimension 
- Cohomology can be computed Cech complexes
- More listed in Voevodsky's original paper
  
## Contracting the Affine Line
  
  
The last step is forcing <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> to be contractible, i.e. <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1%20&#x5C;cross%20X%20&#x5C;homotopic%20X"/>, which will come from another localization <img src="https://latex.codecogs.com/gif.latex?L_&#x5C;Af"/>. This composition will land us in the homotopy theory we want:
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;Sm%20&#x5C;mapsvia{Y}%20&#x5C;text{PreSh}_k%20&#x5C;mapsvia{L_&#x5C;tau}%20&#x5C;text{Sh}_k%20&#x5C;mapsvia{L_{&#x5C;Af}}%20&#x5C;text{Spc}_k"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?&#x5C;tau"/> is the choice of the Nisnevich topology, and so we'll call <img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Spc}_k"/> our <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory.
  
# Making Spheres
  
  
Given two pointed spaces <img src="https://latex.codecogs.com/gif.latex?X,%20Y"/>, we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?X%20&#x5C;wedge%20Y%20=%20&#x5C;frac{X%20&#x5C;cross%20Y}{(X&#x5C;cross%20&#x5C;pt)%20&#x5C;union%20(&#x5C;pt%20&#x5C;cross%20Y)}"/></p>  
  
  
In topology, we have <img src="https://latex.codecogs.com/gif.latex?S^m%20&#x5C;wedge%20S^n%20=%20S^{m+n}"/>. In <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory, we have functors to simplicial sets, and so we can take constant functors, and in particular any element space living in simplicial sets is in our new homotopy theory as well. So we have <img src="https://latex.codecogs.com/gif.latex?S^1"/>, we can also take <img src="https://latex.codecogs.com/gif.latex?&#x5C;GG_m%20=%20&#x5C;Af^1%20-%20&#x5C;theset{0}"/>, and so we have spheres
<p align="center"><img src="https://latex.codecogs.com/gif.latex?S^{p+q,q}%20=%20(S^1)^{&#x5C;wedge%20p}%20&#x5C;wedge%20(&#x5C;GG_m)^{&#x5C;wedge%20q}%20."/></p>  
  
  
Some of these end up being familiar spaces. For example, we can look at the colimit
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}%20%20&#x5C;GG_m%20@&gt;&gt;&gt;%20&#x5C;Af^1%20&#x5C;homotopic%20&#x5C;pt%20&#x5C;&#x5C;%20%20@VVV%20&#x5C;selfmap%20@VVV%20&#x5C;&#x5C;%20%20&#x5C;pt%20&#x5C;homotopic%20&#x5C;Af^1%20@&gt;&gt;&gt;%20&#x5C;PP^1&#x5C;end{CD}"/></p>  
  
  
which follows from the fact that <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^1%20=%20&#x5C;Af^1%20&#x5C;union%20&#x5C;theset{&#x5C;infty}"/> (yielding the top-right copy of <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/>), and we can take a neighborhood around the point at <img src="https://latex.codecogs.com/gif.latex?&#x5C;infty"/> to obtain the bottom-left copy -- these intersect in <img src="https://latex.codecogs.com/gif.latex?&#x5C;GG_m"/>.
  
So <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^1"/> is the colimit of maps from <img src="https://latex.codecogs.com/gif.latex?&#x5C;GG_m"/> to a point, so we can conclude that <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^1%20&#x5C;homotopic%20&#x5C;Sigma%20&#x5C;GG_m%20=%20S^1%20&#x5C;wedge%20&#x5C;GG_m"/>.
  
We can also show <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^n%20-%20&#x5C;theset{0}%20&#x5C;homotopic%20(S^1)^{&#x5C;wedge%20n-1}&#x5C;wedge%20(&#x5C;GG_m)^{&#x5C;wedge%20n}"/>. This will rely on a general fact about the colimit of <img src="https://latex.codecogs.com/gif.latex?X&#x5C;cross%20Y"/> with its projections is a suspension, given by
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}%20%20X&#x5C;cross%20Y%20@&gt;&gt;&gt;%20X%20&#x5C;&#x5C;%20%20@VVV%20&#x5C;selfmap%20@VVV%20&#x5C;&#x5C;%20%20Y%20@&gt;&gt;&gt;%20&#x5C;therefore%20&#x5C;Sigma%20X&#x5C;wedge%20Y%20&#x5C;end{CD}"/></p>  
  
  
and so we can proceed by induction on the following diagram:
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}%20%20(&#x5C;Af^{n-1}%20-%20&#x5C;theset{0}%20)&#x5C;cross(&#x5C;Af^1%20-&#x5C;theset{0})%20@&gt;&gt;&gt;%20(&#x5C;Af^{n-1}%20-&#x5C;theset{0})%20&#x5C;cross%20&#x5C;Af^1%20&#x5C;&#x5C;%20%20@VVV%20&#x5C;selfmap%20@VVV%20&#x5C;&#x5C;%20%20&#x5C;Af^n%20&#x5C;cross%20(&#x5C;Af^1%20-&#x5C;theset{0})%20@&gt;&gt;&gt;%20&#x5C;Af^n%20-%20&#x5C;theset{0}%20&#x5C;end{CD}"/></p>  
  
  
We also have <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^{n}%20&#x2F;%20&#x5C;PP^{n-1}%20&#x5C;homotopic%20(S^1)^{&#x5C;wedge%20n}&#x5C;wedge%20(&#x5C;GG_m)^{&#x5C;wedge%20n}"/>. This can be show because <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^{n}%20&#x2F;%20&#x5C;PP^{n-1}%20&#x5C;homotopic%20&#x5C;PP^n%20&#x2F;%20&#x5C;PP^n-&#x5C;theset{0}"/> because <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> is trivial and we can homotop the embedded <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^{n-1}"/> down to the origin, giving a line bundle over <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^{n-1}"/>. We can then cut out the copy of <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^{n-1}"/> at infinity, yielding <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^n%20&#x2F;%20&#x5C;Af^{n}%20-%20&#x5C;theset{0}%20&#x5C;homotopic%20&#x5C;pt%20&#x2F;%20&#x5C;Af^{n}%20-%20&#x5C;theset{0}%20=%20&#x5C;Sigma%20(&#x5C;Af^{n}%20-%20&#x5C;theset{0})"/>, where the last equality comes from looking at a similar colimit diagram as earlier.
  
# Thom Spaces
  
These can be made out of vector bundles, which will prove to be useful in viewing smooth schemes like manifolds. Let <img src="https://latex.codecogs.com/gif.latex?V%20&#x5C;to%20X"/> be an algebraic vector bundle. Then the Thom space 
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Th}(V)%20=%20&#x5C;frac{V}%20{V-X}%20&#x5C;homotopic%20&#x5C;frac{&#x5C;PP(V%20&#x5C;oplus%20&#x5C;mathcal%20O)}{&#x5C;PP%20V}"/></p>  
  
where <img src="https://latex.codecogs.com/gif.latex?X"/> here corresponds to the zero section, <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O"/> is the trivial line bundle, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP%20V"/> is the projectivization of <img src="https://latex.codecogs.com/gif.latex?V"/> where the coordinate is zero.
  
> Note: If this was a virtual vector bundle, we could make a Thom spectrum.
  
The next theorem gives us neighborhoods around points
  
**The Purity Theorem**:
Let <img src="https://latex.codecogs.com/gif.latex?Z%20&#x5C;injects%20X"/> be a closed immersion in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Sm"/>. Consider <img src="https://latex.codecogs.com/gif.latex?&#x5C;frac%20X%20{X-Z}"/>, in topology we could take a tubular neighborhood around <img src="https://latex.codecogs.com/gif.latex?Z"/> and view this as a neighborhood mod its boundary. This is equivalent to <img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Th}(N_Z%20X)"/>, the Thom space of the normal bundle of <img src="https://latex.codecogs.com/gif.latex?Z"/> in <img src="https://latex.codecogs.com/gif.latex?X"/>.
  
**Example:** Let <img src="https://latex.codecogs.com/gif.latex?Z%20=&#x5C;spec(k)"/> and <img src="https://latex.codecogs.com/gif.latex?X%20&#x5C;in%20&#x5C;Sm"/>, then let <img src="https://latex.codecogs.com/gif.latex?U"/> be a Zariski open neighborhood of <img src="https://latex.codecogs.com/gif.latex?z"/>. Then <img src="https://latex.codecogs.com/gif.latex?U&#x2F;U-Z%20&#x5C;homotopic%20&#x5C;PP^n%20&#x2F;%20&#x5C;PP^{n-1}"/> since the Thom space is just a vector space here. So this produces a sphere around <img src="https://latex.codecogs.com/gif.latex?z"/>.
  
**Example:** Replace <img src="https://latex.codecogs.com/gif.latex?&#x5C;spec%20k"/> with <img src="https://latex.codecogs.com/gif.latex?&#x5C;spec(k(z))"/>, this yields <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n_{k(z)}%20&#x2F;%20&#x5C;PP^{n-1}_{k(z)}%20&#x5C;homotopic%20&#x5C;PP^n%20&#x2F;%20&#x5C;PP^{n-1}%20&#x5C;wedge%20(&#x5C;spec%20(k(z)&#x5C;coprod%20&#x5C;pt)"/>
> Note: video says "disjoint basepoint" here and uses different notation, may not be correct.
  
Compare to manifolds: if <img src="https://latex.codecogs.com/gif.latex?z&#x5C;in%20U"/> a small ball, then <img src="https://latex.codecogs.com/gif.latex?&#x5C;Sigma%20&#x5C;del%20U%20&#x5C;homotopic%20U%20&#x2F;%20U%20-%20z"/>. So if we wanted to look at maps between boundaries, we could suspend and take degrees.
  
# The Grothendieck-Witt Group
  
Recall that the target of the degree map was <img src="https://latex.codecogs.com/gif.latex?GW(k)"/>; we'll also talk a bit about Milnor K-theory <img src="https://latex.codecogs.com/gif.latex?K^M_*(k)"/>.
  
From yesterday, we defined <img src="https://latex.codecogs.com/gif.latex?GW(k)"/> as the isomorphism classes of symmetric nondegenerate bilinear forms over <img src="https://latex.codecogs.com/gif.latex?k"/>, which had a generators
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{a},%20&#x5C;quad%20a&#x5C;in%20k^&#x5C;times&#x5C;&#x5C;&#x5C;generators{a}:%20k^2%20&#x5C;to%20k&#x5C;&#x5C;(x,y)%20&#x5C;mapsto%20axy"/></p>  
  
  
and relations
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;generators{ab^2}%20&amp;=%20&#x5C;generators{a}%20&#x5C;quad&amp;(b&#x5C;neq%200)&#x5C;&#x5C;&#x5C;generators{a}&#x5C;tensor&#x5C;generators{b}%20&amp;=%20&#x5C;generators{ab}%20&amp;&#x5C;&#x5C;&#x5C;generators{a}%20+%20&#x5C;generators%20b%20&amp;=%20&#x5C;generators{a+b}%20+%20&#x5C;generators{ab(a+b)}%20&#x5C;quad&amp;(a+b&#x5C;neq%200)&#x5C;end{align*}"/></p>  
  
  
which follows because we're in <img src="https://latex.codecogs.com/gif.latex?k^&#x5C;times&#x2F;(k^&#x5C;times)^2"/>. Note that the last relation is very important.
  
These relations imply a special relation concerning a **hyperbolic form,** which is given by 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?h&#x5C;definedas%20&#x5C;generators%20{1}%20+%20&#x5C;generators%20{-1}%20=%20&#x5C;generators%20a%20+%20&#x5C;generators{-a}"/></p>  
  
for any <img src="https://latex.codecogs.com/gif.latex?a"/>.
  
We'll look at invariants on bilinear forms -- for many common fields, there are algorithms to determine equality of sums of generators, and thus in <img src="https://latex.codecogs.com/gif.latex?GW"/> there are many tools to work with. Some of these tools are invariants arising from the Milnor conjecture, which involves this group and is a huge achievement in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory.
  
We have a **rank homomorphism:**
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;text{rank}:%20GW(k)%20&#x5C;to%20&#x5C;ZZ%20&#x5C;&#x5C;%20(B:%20V^2%20&#x5C;to%20k)%20&#x5C;mapsto%20&#x5C;dim%20V"/></p>  
  
  
and the **fundamental ideal** is defined as <img src="https://latex.codecogs.com/gif.latex?I%20&#x5C;definedas%20&#x5C;ker%20&#x5C;text{rank}"/>. This yields a filtration
<p align="center"><img src="https://latex.codecogs.com/gif.latex?GW(k)%20&#x5C;supseteq%20I%20&#x5C;supseteq%20I^2%20&#x5C;supseteq%20&#x5C;cdots"/></p>  
  
  
where the associated graded are etale cohomology groups and (by the Milnor conjecture) Milnor K-theory groups.
  
# Milnor K-Theory
  
  
We define **Milnor K-theory** as
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K_i^M%20&#x5C;definedas%20&#x5C;frac{&#x5C;bigoplus_{i=1}^&#x5C;infty%20%20(k^&#x5C;times)^{&#x5C;tensor%20i}%20}%20{&#x5C;generators{a&#x5C;tensor(1-a)}}"/></p>  
  
  
which is tensor algebra on <img src="https://latex.codecogs.com/gif.latex?k^&#x5C;times"/>, modded out by the Steinberg relation.
  
**Theorem: The Milnor Conjecture (Voevodsky)**
There is a map
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K_n^M%20&#x5C;to%20I^n&#x2F;I^{n+1}%20&#x5C;&#x5C;&#x5C;bigotimes_{i=1}^n%20a_i%20&#x5C;mapsto%20&#x5C;prod_{i=1}^n%20&#x5C;left(&#x5C;generators{1}%20-%20&#x5C;generators{a_i}&#x5C;right)."/></p>  
  
  
We can also look at the Kummer map coming from the short exact sequence
<p align="center"><img src="https://latex.codecogs.com/gif.latex?1&#x5C;to%20&#x5C;ZZ&#x2F;2&#x5C;ZZ%20&#x5C;to%20&#x5C;overline%20{k^&#x5C;times}%20&#x5C;to%20&#x5C;overline{k^&#x5C;times}%20&#x5C;to%201"/></p>  
  
  
which lets us make a map 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?k^&#x5C;times%20&#x5C;to%20H_&#x5C;text{et}^1(k;~&#x5C;ZZ&#x2F;2&#x5C;ZZ)"/></p>  
  
  
where we can use that fact that <img src="https://latex.codecogs.com/gif.latex?k^&#x5C;times%20&#x5C;cong%20K^M_1"/> to land in Milnor K-theory,
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K_1^M%20&#x5C;to%20H_&#x5C;text{et}^1(k;~&#x5C;ZZ&#x2F;2&#x5C;ZZ),"/></p>  
  
  
where we can use the cup product to lift this to a map to the <img src="https://latex.codecogs.com/gif.latex?n"/>th graded piece
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K_n^M%20&#x5C;to%20H_&#x5C;text{et}^n(k;~&#x5C;ZZ&#x2F;2&#x5C;ZZ)."/></p>  
  
  
Fitting all of this together, we get maps
<p align="center"><img src="https://latex.codecogs.com/gif.latex?sI^n&#x2F;I^{n+1}%20&#x5C;from%20K_n^M%20&#x5C;to%20H_&#x5C;text{et}^n(k;~&#x5C;ZZ&#x2F;2&#x5C;ZZ),"/></p>  
  
  
and the Milnor conjecture states that these are isomorphisms.
  
In other words, the associated graded of this filtration is the etale cohomology or Milnor K-theory, and if you have a field for which the <img src="https://latex.codecogs.com/gif.latex?n"/>th etale cohomology in <img src="https://latex.codecogs.com/gif.latex?&#x5C;ZZ&#x2F;2&#x5C;ZZ"/> coefficients doesn't vanish, then there is a nontrivial piece in the associated graded. 
  
# Grothendieck-Witt Group Invariants
  
  
This lets us view maps <img src="https://latex.codecogs.com/gif.latex?I^n%20&#x5C;to%20I^n&#x2F;I^{n+1}"/> as invariants on <img src="https://latex.codecogs.com/gif.latex?GW(k)"/>. 
- For <img src="https://latex.codecogs.com/gif.latex?n=0"/>, this is the rank homomorphism.  
- For <img src="https://latex.codecogs.com/gif.latex?n=1"/> we get the discriminant, which is the determinant of the linear map associated to the bilinear form obtained after choosing a basis.
- For <img src="https://latex.codecogs.com/gif.latex?n=2"/> this is the Hasse-Witt invariant (see written notes)
- For <img src="https://latex.codecogs.com/gif.latex?n=3"/> this is the Arason invariant
  
For higher <img src="https://latex.codecogs.com/gif.latex?n"/> these invariants don't have names, but for various fields, the lower degrees form a complete invariant -- for example, for finite fields, one needs only check <img src="https://latex.codecogs.com/gif.latex?n=0,1"/>, while <img src="https://latex.codecogs.com/gif.latex?&#x5C;QQ"/> requires <img src="https://latex.codecogs.com/gif.latex?n=0,1,2"/>.
  
The Grothendieck-Witt group is the 0th graded piece of Milnor-Witt K-theory, <img src="https://latex.codecogs.com/gif.latex?M_*^{MW}(k)"/>, which is also a homotopy group of spheres in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory (due to Hopkins and Morel). 
  
This group has generators
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;generators{a},%20&amp;&#x5C;quad%20a&#x5C;in%20k^&#x5C;times,%20&amp;&#x5C;deg%20a%20=%201&#x5C;&#x5C;&#x5C;eta,%20&amp;%20&amp;%20&#x5C;quad&#x5C;deg%20&#x5C;eta%20=%20-1&#x5C;end{align*}"/></p>  
  
  
and relations
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;eta%20&#x5C;generators{a}%20&amp;=%20&#x5C;generators{a}%20&#x5C;eta&#x5C;&#x5C;&#x5C;generators{a}&#x5C;generators{1-a}%20&amp;=%200&amp;&#x5C;&#x5C;&#x5C;generators{ab}%20&amp;=%20&#x5C;generators{a}%20+%20&#x5C;generators{b}%20+%20&#x5C;eta%20&#x5C;generators{a}&#x5C;generators{b}&#x5C;&#x5C;&#x5C;eta%20h%20&amp;=%200&#x5C;end{align*}"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?h"/> is the same as earlier, but since it's in the wrong group, we need to define this using the isomorphism
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}G%20W%20(%20k%20)%20&amp;&#x5C;cong%20K%20_%20{%200%20}%20^%20{%20MW%20}%20(%20k%20)%20&#x5C;&#x5C;&#x5C;generators{a}%20&amp;&#x5C;mapsto%201%20+%20n%20&#x5C;generators{a}&#x5C;&#x5C;h&#x5C;definedas%20&#x5C;generators{1}%20+%20&#x5C;generators{-1}%20&amp;&#x5C;mapsto%202%20+%20&#x5C;eta&#x5C;generators{-1}&#x5C;definedas%20h.&#x5C;end{align*}"/></p>  
  
  
# Degree Theorem
  
This theorem says that <img src="https://latex.codecogs.com/gif.latex?&#x5C;eta"/> corresponds to a Hopf map.
  
**Theorem (Morel):**
<p align="center"><img src="https://latex.codecogs.com/gif.latex?[(S^1)^{&#x5C;wedge%20n}%20&#x5C;wedge%20(&#x5C;GG_m)^{&#x5C;wedge%20j},~%20(S^1)^{&#x5C;wedge%20n}%20&#x5C;wedge%20(&#x5C;GG_m)^{&#x5C;wedge%20r}]%20&#x5C;cong%20K^{MW}_{r-j}"/></p>  
  
  
where the square brackets correspond to homotopy classes of maps.
  
In particular, when <img src="https://latex.codecogs.com/gif.latex?j=r=n"/>, we obtain
<p align="center"><img src="https://latex.codecogs.com/gif.latex?[&#x5C;PP^n%20&#x2F;&#x5C;PP^{n-1},~%20&#x5C;PP^n%20&#x2F;&#x5C;PP^{n-1}]%20&#x5C;cong%20GW(k)"/></p>  
  
  
> This is a fantastic theorem, which we will see again later when doing oriented Chow groups.
  
A nice consequence is that if we let <img src="https://latex.codecogs.com/gif.latex?k=&#x5C;RR"/>, the degrees behave nicely, characterized by the commutativity of this diagram:
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{CD}[S^{2n},~S^{2n}]%20@&lt;&#x5C;CC&#x5C;dash&#x5C;text{points}&lt;&lt;%20[&#x5C;PP^n%20&#x2F;&#x5C;PP^{n-1},~%20&#x5C;PP^n%20&#x2F;&#x5C;PP^{n-1}]%20@&gt;&#x5C;RR&#x5C;dash&#x5C;text{points}&gt;&gt;%20[S^n,~S^n]%20&#x5C;&#x5C;@VV&#x5C;deg%20V%20&#x5C;selfmap%20@VV&#x5C;deg%20V%20&#x5C;selfmap%20@VV&#x5C;deg%20V%20&#x5C;&#x5C;&#x5C;ZZ%20@&lt;&lt;&#x5C;text{rank}&lt;%20GW(k)%20@&gt;&gt;&#x5C;text{signature}&gt;%20&#x5C;ZZ&#x5C;end{CD}"/></p>  
  
  
where the edge degree maps are just the topological degree of maps between spheres and the middle is the <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> degree. The signature is the usual difference in <img src="https://latex.codecogs.com/gif.latex?&#x5C;pm%201"/>s occurring after diagonalization. Thus <img src="https://latex.codecogs.com/gif.latex?GW(k)"/> lets us simultaneously read off the real and complex degrees of maps between schemes over <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR"/>.
  
So these homotopy groups are actually homotopy sheaves (not just global sections of sheaves), where we can form a sheaf by taking smash with <img src="https://latex.codecogs.com/gif.latex?U^+"/> and sheafifying. Thus <img src="https://latex.codecogs.com/gif.latex?GW(k),%20K^{MW}_*(k),"/> and <img src="https://latex.codecogs.com/gif.latex?K^M_*(k)"/> are all global sections of sheaves.
  
> Not sure what <img src="https://latex.codecogs.com/gif.latex?U^+"/> is here.
  
  
# Producing a Sheaf
  
There is a procedure in Morel's book for producing an unramified sheaf <img src="https://latex.codecogs.com/gif.latex?K^{MW}_*"/> from the values on fields, i.e. <img src="https://latex.codecogs.com/gif.latex?K^{MW}_*(E)"/> for some <img src="https://latex.codecogs.com/gif.latex?E%20&#x5C;supset%20k"/> of finite type. It proceeds as follows:
  
We want to know what the sections are on some scheme <img src="https://latex.codecogs.com/gif.latex?Y"/>, so we look at its function field and check <img src="https://latex.codecogs.com/gif.latex?K^{MW}_*"/> on it to see which sections are defined over all of <img src="https://latex.codecogs.com/gif.latex?Y"/> and not over the generic point. This produces the additional data of boundary/residue maps that determine when sections extend globally. 
  
So let <img src="https://latex.codecogs.com/gif.latex?V:E%20&#x5C;to%20&#x5C;ZZ%20&#x5C;union%20&#x5C;theset&#x5C;infty"/> be a valuation and <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O_V%20=%20&#x5C;theset{e&#x5C;in%20E%20&#x5C;suchthat%20V(e)%20&#x5C;geq%200}"/> and choose a uniformizer <img src="https://latex.codecogs.com/gif.latex?&#x5C;pi"/> such that <img src="https://latex.codecogs.com/gif.latex?v(&#x5C;pi)=1"/>. Then form the residue field <img src="https://latex.codecogs.com/gif.latex?k(V)%20&#x5C;definedas%20&#x5C;mathcal%20O_V%20&#x2F;%20&#x5C;generators{&#x5C;pi}"/>. Then this residue map plus the sections will allow us to define a sheaf, so define the **residue homomorphism**
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;del_V^&#x5C;pi:%20K_*^{MW}(E)%20&amp;&#x5C;to%20K_*^{MW}(k(V))[-1]%20&#x5C;&#x5C;&#x5C;generators{&#x5C;pi}&#x5C;generators{a_1}&#x5C;cdots&#x5C;generators{a_n}%20&amp;&#x5C;mapsto%20&#x5C;generators{&#x5C;overline%20a_1}%20&#x5C;cdots&#x5C;generators{&#x5C;overline%20a_n}%20&#x5C;&#x5C;&#x5C;generators{a_1}%20&#x5C;cdots%20&#x5C;generators{a_n}%20&amp;&#x5C;mapsto%200%20&#x5C;&#x5C;&#x5C;generators{&#x5C;eta}%20&#x5C;mapsto%200&#x5C;end{align*}"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?a_i%20&#x5C;in%20&#x5C;mathcal{O}_V^&#x5C;times"/> and <img src="https://latex.codecogs.com/gif.latex?&#x5C;overline%20a_i"/> is the reduction.
  
> Note that it is true that <img src="https://latex.codecogs.com/gif.latex?&#x5C;del_V^&#x5C;pi%20&#x5C;eta%20=%20&#x5C;eta%20&#x5C;del_V^&#x5C;pi"/>, and this is part of what uniquely defines this map. However, we can't have <img src="https://latex.codecogs.com/gif.latex?&#x5C;eta%20&#x5C;mapsto%20&#x5C;eta"/>, because this does not decrease the degree by 1.
  
So then the sections on <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O"/> are given by
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K^{MW}_*(&#x5C;mathcal%20O_V)%20&#x5C;definedas%20&#x5C;ker%20&#x5C;del_V^&#x5C;pi"/></p>  
  
  
and there is a procedure for making a sheaf from this denoted <img src="https://latex.codecogs.com/gif.latex?K_*^{MW}"/>.
  
The fact this is a stable homotopy sheaf provides some transfers (seen last time), which we'll start with next time.
  
  
  
# Lecture 3
  
  
  
  
  
# Transfers
  
  
## Defining Some Transfers
  
Recall that we have the sheaves <img src="https://latex.codecogs.com/gif.latex?K^{MW}_*,%20GW"/>, and the sheaf property means that an inclusion <img src="https://latex.codecogs.com/gif.latex?K%20&#x5C;injects%20L"/> induces a map <img src="https://latex.codecogs.com/gif.latex?&#x5C;spec(L)%20&#x5C;to%20&#x5C;spec(K)"/>. We can take <img src="https://latex.codecogs.com/gif.latex?GW(spec(L)%20&#x5C;to%20&#x5C;spec(K))"/>, and this is exactly the restriction/base change given by <img src="https://latex.codecogs.com/gif.latex?&#x5C;wait%20&#x5C;tensor_k%20L"/> of bilinear forms.
  
We also saw that these were stable homotopy sheaves, so there should be transfers, and we want to use them for field extensions. Let <img src="https://latex.codecogs.com/gif.latex?K&#x5C;subset%20L"/> be a finite extension of finite-type schemes over <img src="https://latex.codecogs.com/gif.latex?k"/>. This leads to transfer maps
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;Tr_{L&#x2F;K}:%20GW(K)%20&#x5C;to%20GW(L)."/></p>  
  
  
There is also a geometric transfer (which is the prettiest!) which we'll define momentarily, given by with multiplication by one of those brackets to define a cohomological transfer. The geometric transfer will depend on a sequence of generators, while, while this choice can be removed for the cohomological transfer. If you use the twisting data you can get an absolute transfer. 
  
In the case where <img src="https://latex.codecogs.com/gif.latex?K&#x5C;subset%20L"/> is separable, there is a canonical way to explicitly untwist, and the absolute and cohomological transfers agree.  For these two, we took
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;Tr(B:%20V^2%20&#x5C;to%20L)%20=%20V^2%20&#x5C;mapsvia{B}%20L%20&#x5C;mapsvia{&#x5C;Tr_{W^k}}"/></p>  
  
where we now view <img src="https://latex.codecogs.com/gif.latex?V"/> as a <img src="https://latex.codecogs.com/gif.latex?k&#x5C;dash"/>vector space, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;Tr_{W^k}"/> is the trace from Galois theory, the sum of the Galois conjugates.
  
We'll show that we have this structure for the geometric transfer. If <img src="https://latex.codecogs.com/gif.latex?L%20=%20K[z]&#x2F;&#x5C;generators{f}"/>, so we've chosen some generator, then we get an induced map <img src="https://latex.codecogs.com/gif.latex?&#x5C;spec(L)%20&#x5C;overset{z}&#x5C;injects%20&#x5C;PP^1_K"/>. Since this is a closed immersion corresponding to <img src="https://latex.codecogs.com/gif.latex?z"/>, we can form a backwards map 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^1_K%20&#x5C;to%20{&#x5C;PP^1_K%20&#x5C;over%20&#x5C;PP^1_K-&#x5C;theset{z}}%20&#x5C;homotopic%20&#x5C;PP^1_L"/></p>  
  
by crushing everything but <img src="https://latex.codecogs.com/gif.latex?z"/>, where the last equivalence was seen in the previous lecture. But now we can take <img src="https://latex.codecogs.com/gif.latex?K^{MW}_1(&#x5C;PP^1_K%20&#x5C;to%20&#x5C;PP^1_L)"/>, which is a map
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;Tr_{L&#x2F;K}^{&#x5C;text{geom}}:%20%20GW(L)%20&#x5C;to%20GW(K)"/></p>  
  
  
So we have some transfers.
  
## Bilinear Forms on Chow Groups
  
  
The finale of this morning was going to be adding bilinear forms to Chow groups for the purposes of having a tool in enumerative geometry. So let <img src="https://latex.codecogs.com/gif.latex?X&#x5C;in&#x5C;Sm"/> and <img src="https://latex.codecogs.com/gif.latex?X^{(i)}"/> codimension <img src="https://latex.codecogs.com/gif.latex?i"/> reduced, irreducible subschemes of <img src="https://latex.codecogs.com/gif.latex?X"/>. Then 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?CH^i(X)%20=%20{&#x5C;bigoplus_{X^{(i)}}%20&#x5C;ZZ%20&#x5C;over%20&#x5C;sim}"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?&#x5C;sim"/> is rational equivalence, the equivalence relation generated by taking subvarieties of <img src="https://latex.codecogs.com/gif.latex?V&#x5C;subset%20X&#x5C;cross%20&#x5C;PP^1"/> and equating the fibers and the endpoints <img src="https://latex.codecogs.com/gif.latex?V_{&#x5C;theset{1}}%20&#x5C;sim%20V_{&#x5C;theset{0}}"/>, i.e. <img src="https://latex.codecogs.com/gif.latex?V&#x5C;intersect%20(X&#x5C;cross&#x5C;theset{1})%20&#x5C;sim%20V&#x5C;intersect%20(X&#x5C;cross&#x5C;theset{0})"/>.
  
These are useful in enumerative geometry -- there are Chern classes, pushforwards, pullbacks, a ring structure, etc. This ring structure lets us do intersection theory, providing some machinery to help with enumerative questions.
  
The <img src="https://latex.codecogs.com/gif.latex?i"/>th Chow group, in addition to being a motivic homology group, also has a nice formula due to Bloch that applies in the case of smooth schemes: <img src="https://latex.codecogs.com/gif.latex?CH^i(X)%20&#x5C;cong%20H^i(X;%20K^{M}_i)"/> where the RHS is the Nisnevich cohomology of <img src="https://latex.codecogs.com/gif.latex?X"/> with coefficients in Milnor <img src="https://latex.codecogs.com/gif.latex?K&#x5C;dash"/>theory.
  
Oriented Chow groups (AKA Chow-Witt groups) which are the original Chow groups together with a bilinear form. By Borge and Morel, motivated by the Bloch formula above, these can be defined as 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;widetilde{CH}{}^i(X)%20&#x5C;definedas%20H^i(X;%20K_i^{MW})."/></p>  
  
  
This can be computed by a complex (as in Morel's book):
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;cdots%20&#x5C;to%20&#x5C;bigoplus_{z&#x5C;in%20X^{(ii1)}}%20K^{MW}_{1}(K(z),%20~&#x5C;det_{k(z)}%20T_z%20X)%20&#x5C;to%20&#x5C;bigoplus_{z&#x5C;in%20X^{(i)}}%20GW(K(z),%20~&#x5C;det_{k(z)}%20T_z%20X)%20%20&#x5C;to%20&#x5C;bigoplus_{z&#x5C;in%20X^{(i+1)}}%20K^{MW}_{-1}(K(z),%20~&#x5C;det_{k(z)}%20T_z%20X)%20%20&#x5C;to%20&#x5C;cdots"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?k(z)"/> is the function field, and since <img src="https://latex.codecogs.com/gif.latex?z"/> has a generic point, we can take the highest wedge power of the tangent space of <img src="https://latex.codecogs.com/gif.latex?X"/> at <img src="https://latex.codecogs.com/gif.latex?z"/> to yield the determinant term, which serves as an added twist. This explains why elements of the oriented Chow are formal combinations of codimension <img src="https://latex.codecogs.com/gif.latex?i"/> subvarieties <img src="https://latex.codecogs.com/gif.latex?z&#x5C;in%20X^{(i)}"/> and a bilinear form over <img src="https://latex.codecogs.com/gif.latex?k(z)"/>, <img src="https://latex.codecogs.com/gif.latex?B&#x5C;in%20GW(k(z))"/>.
  
There's structure here -- Fasel developed ring structure and pushforwards, while in the context of enumerative geometry, Mark Levine works with these. All in all, we have pullbacks, pushforwards, a noncommutative ring structure, and we can twist these groups as well.
  
## Twisted Chow
  
  
First we'll define the twists appearing in the complex above, and then we can define how to do twisted Chow so we can do pushforwards.
  
If <img src="https://latex.codecogs.com/gif.latex?E"/> is a field of finite type over <img src="https://latex.codecogs.com/gif.latex?k"/>, then <img src="https://latex.codecogs.com/gif.latex?K^{MW}_i(E;%20&#x5C;Lambda)"/> ("twisted by <img src="https://latex.codecogs.com/gif.latex?&#x5C;Lambda"/>") where <img src="https://latex.codecogs.com/gif.latex?&#x5C;Lambda"/> is a 1-dimensional <img src="https://latex.codecogs.com/gif.latex?E&#x5C;dash"/>vector space can be defined as 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?K^{MW}_i(E)%20&#x5C;underset{&#x5C;ZZ[E^&#x5C;times]}&#x5C;tensor%20&#x5C;ZZ[&#x5C;Lambda%20-%20&#x5C;theset{0}]"/></p>  
  
  
since <img src="https://latex.codecogs.com/gif.latex?E^&#x5C;times"/> acts of the LHS due to the bracket <img src="https://latex.codecogs.com/gif.latex?E"/> in the Grothendieck-Witt group, and the RHS is possible because we can act on the nonzero elements of the vector space. 
  
We can also twist by line bundles <img src="https://latex.codecogs.com/gif.latex?L%20&#x5C;to%20X"/>, leading to a definition of **oriented Chow groups twisted by local coefficients** via <img src="https://latex.codecogs.com/gif.latex?&#x5C;widetilde{CH}{}^i(X;%20L)%20&#x5C;definedas%20H^i(X;%20K^{MW}_i(L))"/> where we just take <img src="https://latex.codecogs.com/gif.latex?K&#x5C;dash"/>Milnor-Witt and twist by <img src="https://latex.codecogs.com/gif.latex?L"/>.
  
For any proper <img src="https://latex.codecogs.com/gif.latex?f:%20X&#x5C;to%20Y"/> where <img src="https://latex.codecogs.com/gif.latex?&#x5C;dim%20Y%20-%20&#x5C;dim%20X%20=%20r"/>, then we have a pushforward map 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?f_*:%20&#x5C;widetilde{CH}{}^i(X,%20&#x5C;omega_{X&#x2F;k}&#x5C;tensor%20f^*%20&#x5C;mathcal%20L)%20&#x5C;to%20&#x5C;widetilde{CH}{}^{i-r}(Y,%20&#x5C;omega_{Y&#x2F;k}&#x5C;tensor%20&#x5C;mathcal%20L)"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?&#x5C;omega_{X&#x2F;K}"/> is the canonical line bundle of <img src="https://latex.codecogs.com/gif.latex?X"/> over <img src="https://latex.codecogs.com/gif.latex?k"/> given by <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20TX"/>, the determinant of the tangent bundle of <img src="https://latex.codecogs.com/gif.latex?X"/>, and <img src="https://latex.codecogs.com/gif.latex?f^*%20&#x5C;mathcal%20L"/> is the pullback of any line bundle from <img src="https://latex.codecogs.com/gif.latex?f"/>.
  
Note that the bilinear form here acts like an orientation (which is exciting!), hence the name.
  
# Degree by Local Degree
  
  
Recall from Algebraic Topology that if we have a smooth map <img src="https://latex.codecogs.com/gif.latex?f:S^n%20&#x5C;to%20S^n"/>, then there is a notion of degree given picking regular values <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20S^n"/>, so the preimage consists of finitely many points <img src="https://latex.codecogs.com/gif.latex?f&#x5C;inv(p)%20=%20&#x5C;theset{q_1,%20&#x5C;dots,%20q_n}"/>, and we define <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg%20f%20=%20&#x5C;sum%20&#x5C;underset{q_i}&#x5C;deg%20f"/> to be the sum of local degrees. There is a formula for computing the degree from differential topology,  given by choosing coordinates <img src="https://latex.codecogs.com/gif.latex?x_1,%20&#x5C;cdots,%20x_n"/> near <img src="https://latex.codecogs.com/gif.latex?q_i"/> and <img src="https://latex.codecogs.com/gif.latex?y_1,%20&#x5C;cdots,%20y_n"/> near <img src="https://latex.codecogs.com/gif.latex?p"/> which are compatible with orientations. Then <img src="https://latex.codecogs.com/gif.latex?f:&#x5C;RR^n&#x5C;to&#x5C;RR^n"/>, so we can form its Jacobian <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Jac}(f)%20=%20&#x5C;det%20J"/> where that matrix <img src="https://latex.codecogs.com/gif.latex?J"/> is given by <img src="https://latex.codecogs.com/gif.latex?(J)_{i,j}%20=%20&#x5C;dd{f_i}{x_j}"/>. We then have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;underset{q_i}&#x5C;deg%20f%20=%20&#x5C;begin{cases}%20%20%20%201,%20%20&amp;%20<img src="https://latex.codecogs.com/gif.latex?&amp;#x5C;operatorname{Jac}(f)%20&amp;gt;%200"/>%20&#x5C;&#x5C;%20%20%20%20-1,%20&amp;%20<img src="https://latex.codecogs.com/gif.latex?&amp;#x5C;operatorname{Jac}(f)%20&amp;lt;%200"/>.&#x5C;end{cases}"/></p>  
  
  
In <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> algebraic topology, instead of just remembering the sign (like the signature), the idea of Lannes-Morel is to remember the entirety of <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Jac}(f)"/>. Take <img src="https://latex.codecogs.com/gif.latex?f:%20&#x5C;PP^1%20&#x5C;to%20&#x5C;PP^1"/> over a field <img src="https://latex.codecogs.com/gif.latex?k"/>, then let <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20&#x5C;PP^1(k)"/> be a <img src="https://latex.codecogs.com/gif.latex?k&#x5C;dash"/>rational point so that <img src="https://latex.codecogs.com/gif.latex?f&#x5C;inv(p)%20=%20&#x5C;theset{q_1,%20&#x5C;cdots,%20q_n}"/>. We can then define
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;deg^{&#x5C;Af^1}(f)%20=%20&#x5C;sum%20&#x5C;langle%20&#x5C;underset{q_i}{&#x5C;operatorname{Jac}}%20f&#x5C;rangle%20&#x5C;in%20GW(k)"/></p>  
  
  
which doesn't depend on <img src="https://latex.codecogs.com/gif.latex?p"/>. We then make an analogous definition for higher dimensions.
  
**Proposition:** the global degree is a sum of local degrees. 
Let <img src="https://latex.codecogs.com/gif.latex?f:%20&#x5C;PP^n%20&#x5C;to%20&#x5C;PP^n"/> be finite such that <img src="https://latex.codecogs.com/gif.latex?f&#x5C;inv(&#x5C;Af^n)%20=%20&#x5C;Af^n"/> for some chosen copy of <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^n%20&#x5C;subset%20&#x5C;PP^n"/>. This yields an induced map <img src="https://latex.codecogs.com/gif.latex?&#x5C;overline%20f%20:&#x5C;PP^{n}&#x2F;&#x5C;PP^{n-1}%20&#x5C;to%20&#x5C;PP^{n}&#x2F;&#x5C;PP^{n-1}"/>. We then define the global degree by picking some <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20&#x5C;Af^n"/> and setting
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;deg^{&#x5C;Af^1}(&#x5C;overline%20f)%20=%20&#x5C;sum_{q&#x5C;in%20f&#x5C;inv(p)}&#x5C;underset{q}&#x5C;deg{&#x5C;Af^1}(f)"/></p>  
  
  
where the local degree can be define using balls (as in the first lecture), and we let <img src="https://latex.codecogs.com/gif.latex?&#x5C;underset{q}&#x5C;deg{&#x5C;Af^1}(f)"/> be the degree of the composite map
<p align="center"><img src="https://latex.codecogs.com/gif.latex?{&#x5C;PP^{n}%20&#x5C;over%20&#x5C;PP^{n-1}}%20&#x5C;homotopic%20{U%20&#x5C;over%20U-&#x5C;theset{q}}%20&#x5C;to%20{&#x5C;Af^n%20&#x5C;over%20&#x5C;Af^n%20-%20&#x5C;theset{p}}%20&#x5C;homotopic%20&#x5C;operatorname{Th}(N_p&#x5C;Af^n)%20&#x5C;homotopic%20{&#x5C;PP^{n}%20&#x5C;over%20&#x5C;PP^{n-1}}"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?U"/> is an open set chosen such that the preimage of <img src="https://latex.codecogs.com/gif.latex?p"/> only contains <img src="https://latex.codecogs.com/gif.latex?q"/>, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Th}(N_p&#x5C;Af^n)"/> is the Thom space of the normal bundle (here, the tangent bundle) and the last equality follows from the purity theorem and the fact that everything is <img src="https://latex.codecogs.com/gif.latex?k&#x5C;dash"/>rational (i.e. <img src="https://latex.codecogs.com/gif.latex?k(q)%20=%20k"/>).
  
This can also be made to work at a non-rational point, using the Hatcher-style proof, of taking a collapsing map to yield the composite
<p align="center"><img src="https://latex.codecogs.com/gif.latex?{&#x5C;PP^{n}%20&#x5C;over%20&#x5C;PP^{n-1}}%20&#x5C;to%20{&#x5C;PP^{n}%20&#x5C;over%20&#x5C;PP^{n-1}%20-&#x5C;theset{q}}&#x5C;to%20{U%20&#x5C;over%20U-&#x5C;theset{q}}%20&#x5C;to%20{&#x5C;Af^n%20&#x5C;over%20&#x5C;Af^n%20-%20&#x5C;theset{p}}%20&#x5C;homotopic%20{&#x5C;PP^{n}%20&#x5C;over%20&#x5C;PP^{n-1}}."/></p>  
  
  
This yields a notion of local degree in terms of global degree, by taking boundaries of balls, and we have the following facts:
  
- If <img src="https://latex.codecogs.com/gif.latex?f"/> is etale at <img src="https://latex.codecogs.com/gif.latex?q"/>, and <img src="https://latex.codecogs.com/gif.latex?k%20&#x5C;subseteq%20k(q)"/> is separable then 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;underset%20q%20&#x5C;deg^{&#x5C;Af^1}%20(f)%20=%20&#x5C;Tr_{k(q)&#x2F;k}%20&#x5C;langle%20&#x5C;operatorname{Jac}(q)%20&#x5C;rangle"/></p>  
  
  - Depending on what you mean by transfer, the hypothesis of separability can be dropped, but it's needed here to take the composition with the Galois theory trace.
  - We could use this to compute the degree, but we are missing something
  
  
**Question:** what happens if <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Jac}(f)%20=%200"/>? Answer: The Eisenbud-Levine-Khimshiashvili signature formula, which says that if <img src="https://latex.codecogs.com/gif.latex?f:%20&#x5C;RR^n%20&#x5C;to%20&#x5C;RR^n"/> where <img src="https://latex.codecogs.com/gif.latex?0&#x5C;mapsto%200"/> is an isolated zero, then <img src="https://latex.codecogs.com/gif.latex?&#x5C;underset%200%20&#x5C;deg(f)%20=%20&#x5C;operatorname{signature}%20(&#x5C;omega^{EKL})"/> which is a bilinear quadratic form on 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?Q%20&#x5C;definedas%20&#x5C;RR[x_1,%20&#x5C;cdots,%20x_n]_0%20&#x5C;over%20&#x5C;generators{f_1,%20&#x5C;cdots,%20f_n}"/></p>  
  
  
where the numerator is localized at zero. Since the zero was isolated in its fiber, <img src="https://latex.codecogs.com/gif.latex?Q"/> is a finite-dimensional <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR&#x5C;dash"/>vector space, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Jac}(f)%20&#x5C;in%20Q"/> (which may lie in the maximal ideal <img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{x_1,%20&#x5C;cdots,%20x_n})"/>. So we can pick any <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR&#x5C;dash"/>linear <img src="https://latex.codecogs.com/gif.latex?&#x5C;eta:%20Q%20&#x5C;to%20&#x5C;RR"/> such that <img src="https://latex.codecogs.com/gif.latex?&#x5C;eta(&#x5C;operatorname{Jac}(f))%20=%20&#x5C;dim%20Q"/>. This allows us to define
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;omega^{EKL}:%20Q^2%20&#x5C;to%20&#x5C;RR%20&#x5C;&#x5C;(a,b)%20&#x5C;mapsto%20&#x5C;eta(ab)."/></p>  
  
  
A question Eisenbud was whether or not this whole form could be used as a degree over an arbitrary field <img src="https://latex.codecogs.com/gif.latex?k"/>, not just its signature. So does it have an interpretation in algebraic topology? The answer is that it does, as a local degree in <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> homotopy theory (which wasn't around at the time).
  
**Theorem (Kass-Wickelgren)**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;underset%200%20&#x5C;deg^{&#x5C;Af^1}(f)%20=%20&#x5C;omega^{EKL}"/>, constructed in the same way.
  
This works for any rational point, and one of the projects is to remove the hypothesis that <img src="https://latex.codecogs.com/gif.latex?k(x)%20=%20k"/>.
  
**Example:**
Let <img src="https://latex.codecogs.com/gif.latex?f(x)%20=%20x^2"/>, and consider <img src="https://latex.codecogs.com/gif.latex?&#x5C;omega^{EKL}"/> for this form. Form <img src="https://latex.codecogs.com/gif.latex?Q%20=%20k[x]&#x2F;&#x5C;generators{x^2}"/>, where we don't need to localize at zero since <img src="https://latex.codecogs.com/gif.latex?0"/> is the only preimage of <img src="https://latex.codecogs.com/gif.latex?0"/>. Then <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Jac}(f)%20=%202x"/>. Note that <img src="https://latex.codecogs.com/gif.latex?Q"/> has a basis <img src="https://latex.codecogs.com/gif.latex?&#x5C;theset{1,%20x}"/>, and so we can choose
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;eta:%20k[x]&#x2F;&#x5C;generators{x^2}%20&#x5C;to%20k%20&#x5C;&#x5C;&#x5C;eta(2x)%20=%202&#x5C;&#x5C;&#x5C;eta(1)%20=%200"/></p>  
  
  
where we claim can send 1 wherever we want without altering the isomorphism class of <img src="https://latex.codecogs.com/gif.latex?&#x5C;omega^{EKL}"/>. We do this by forming the Gram matrix
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{array}{cc}%20&amp;%20&#x5C;matrix{1%20&amp;%20x}%20&#x5C;&#x5C;%20&#x5C;matrix{1%20&#x5C;&#x5C;%20x}%20&amp;%20&#x5C;begin{bmatrix}%200%20&amp;%201%20&#x5C;&#x5C;%201%20&amp;%200%20%20&#x5C;end{bmatrix}&#x5C;end{array}"/></p>  
  
  
where the 1s appear since we require <img src="https://latex.codecogs.com/gif.latex?x&#x5C;mapsto%201"/>, the bottom-right 0 because <img src="https://latex.codecogs.com/gif.latex?x^2"/> in the ring, and no matter what the top-left corner is, we can change basis by adding a multiple of <img src="https://latex.codecogs.com/gif.latex?x"/> to it.
  
Thus we can diagonalize this matrix to yield <img src="https://latex.codecogs.com/gif.latex?&#x5C;omega^{EKL}%20=%20&#x5C;generators{1}%20+%20&#x5C;generators{-1}"/>. Note that we needed to assume <img src="https://latex.codecogs.com/gif.latex?&#x5C;char%20k"/> does not divide <img src="https://latex.codecogs.com/gif.latex?&#x5C;dim%20Q"/>, otherwise we could have used a distinguished socle element instead in place of the Jacobian.
  
So now we have a way to concretely calculate degrees of maps <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^n%20&#x2F;&#x5C;PP^{n-1}&#x5C;selfmap"/>, so here's an enumerative application.
  
# <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Milnor Numbers
  
(Joint with Jesse Kass)
  
**Definition**: A point <img src="https://latex.codecogs.com/gif.latex?p"/> on a scheme <img src="https://latex.codecogs.com/gif.latex?X"/> is a **node** if after base changing to the separable closure <img src="https://latex.codecogs.com/gif.latex?k^s"/> and looking at all of the preimages, the completed local ring <img src="https://latex.codecogs.com/gif.latex?&#x5C;OO_{X,%20p}%20&#x5C;cong%20k^s[[x_1,%20&#x5C;cdots,%20x_n]]%20&#x2F;%20&#x5C;generators{&#x5C;sum%20x_i^2%20+%20o(x_i^3)}"/> (where <img src="https://latex.codecogs.com/gif.latex?o(x_i^3)"/> just denotes higher order terms).
  
Let <img src="https://latex.codecogs.com/gif.latex?X%20=%20&#x5C;theset{f=0}"/> be a hypersurface, which is a scheme determined by a single equation, then if we perturb the equation near a complicated singularity, that singularity would bifurcate into nodes. So let <img src="https://latex.codecogs.com/gif.latex?p&#x5C;in%20X"/> be a singularity; as <img src="https://latex.codecogs.com/gif.latex?X"/> is perturbed within a family <img src="https://latex.codecogs.com/gif.latex?P"/>, <img src="https://latex.codecogs.com/gif.latex?p"/> bifurcates into nodes. 
  
More specifically, for any <img src="https://latex.codecogs.com/gif.latex?a_1,%20&#x5C;cdots,%20a_n"/>, we have a family of varieties/hypersurfaces given by <img src="https://latex.codecogs.com/gif.latex?f(x_1,%20&#x5C;cdots%20x_n)%20+%20&#x5C;sum%20a_i%20x_i%20=%20t"/> parameterized by <img src="https://latex.codecogs.com/gif.latex?t"/>. One definition of the Milnor number is that in any such family, it counts the number of nodes.
  
Let <img src="https://latex.codecogs.com/gif.latex?k=&#x5C;CC"/>, then a result of Milnor says that for any sufficiently small <img src="https://latex.codecogs.com/gif.latex?a_1,%20&#x5C;cdots,%20a_n"/>, the family <img src="https://latex.codecogs.com/gif.latex?P"/> contains <img src="https://latex.codecogs.com/gif.latex?&#x5C;mu(p)"/> nodes, where <img src="https://latex.codecogs.com/gif.latex?&#x5C;mu"/> denotes taking the Milnor number.
  
To find nodes, one can look at the gradient and see where all of the coefficients of the linear terms vanish. What remains is <img src="https://latex.codecogs.com/gif.latex?o(x_i^2)"/>, so we're looking for zeros of the gradient, which requires looking at the inverse image of the gradient, so we're picking up the degree of the gradient. This gives us another definition, <img src="https://latex.codecogs.com/gif.latex?&#x5C;mu(p)%20=%20&#x5C;deg(&#x5C;grad%20f)(p)"/>.
  
However, when <img src="https://latex.codecogs.com/gif.latex?k&#x5C;neq%20&#x5C;CC"/> and generally not algebraically closed, nodes have interesting information, including arithmetic data.
  
For example, consider <img src="https://latex.codecogs.com/gif.latex?x^2+y^2"/> and <img src="https://latex.codecogs.com/gif.latex?x^2-y^2"/>. The first carves out just the origin, the latter, two diagonal lines.
  
![](../assets/2019-03-09-12-18-52.png )
  
The LHS is a non-split node, meaning the tangent is not defined over <img src="https://latex.codecogs.com/gif.latex?k"/>, while the RHS is a split node. So we can use the <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> degree in place of the topological degree, since we want to count the zeros of the gradient, and it will naturally pick up information about the node.
  
**Definition:** the **type** of a node <img src="https://latex.codecogs.com/gif.latex?p%20=%20&#x5C;theset{f=0}"/> is given by 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Type}(p)%20=%20&#x5C;underset%20p%20&#x5C;deg^{&#x5C;Af^1}%20(&#x5C;grad%20f)%20&#x5C;in%20GW(k)."/></p>  
  
  
**Example:** 
Choose a preimage of <img src="https://latex.codecogs.com/gif.latex?p"/> after base change to <img src="https://latex.codecogs.com/gif.latex?k(p)"/>, suppose the node is cut out by the <img src="https://latex.codecogs.com/gif.latex?f%20=%20&#x5C;sum%20x_i^2%20+%20o(x_i^3)"/>. Then we have the local ring <img src="https://latex.codecogs.com/gif.latex?&#x5C;widehat&#x5C;OO_{X.%20p}%20=%20k[[p]]%20&#x2F;%20&#x5C;generators{f}"/>. Then <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Type}(p)%20=%20&#x5C;Tr_{k(p)&#x2F;%20k}&#x5C;generators{2^n%20a_1%20&#x5C;cdots%20a_n}"/>, where <img src="https://latex.codecogs.com/gif.latex?k(p)"/> is always a separable extension of <img src="https://latex.codecogs.com/gif.latex?k"/>.
  
Then <img src="https://latex.codecogs.com/gif.latex?&#x5C;operatorname{Type}(x^2+ay^2)%20=%20&#x5C;generators{a}"/>. This picks up the two tangent directions in the field of definition, and when it's not rational, it picks up the trace from <img src="https://latex.codecogs.com/gif.latex?k"/> with a 2-tangent direction. So this contains geometric/arithmetic information about both the node and its tangent directions.
  
**Definition:** For <img src="https://latex.codecogs.com/gif.latex?p"/> a singularity on a hypersurface, we can define **the Milnor number** <img src="https://latex.codecogs.com/gif.latex?&#x5C;mu^{&#x5C;Af^1}(p)%20&#x5C;definedas%20&#x5C;underset%20p%20&#x5C;deg%20(&#x5C;grad%20f)"/>. 
  
**Theorem (Kass-Wickelgren):** It then follows that for a generic <img src="https://latex.codecogs.com/gif.latex?a_1,&#x5C;cdots,a_n"/>, for a singularity <img src="https://latex.codecogs.com/gif.latex?p"/>, we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sum_{x%20&#x5C;in%20&#x5C;text{a%20family%20of%20nodes}}%20&#x5C;operatorname{Type}%20(x)%20=%20&#x5C;mu^{&#x5C;Af^1}(p)%20&#x5C;in%20GW(k),"/></p>  
  
  
which is a fixed element.
  
  
**Example:** 
Let <img src="https://latex.codecogs.com/gif.latex?f(x,y)%20=%20y^2-x^3"/>, supposing <img src="https://latex.codecogs.com/gif.latex?&#x5C;char(k)%20&#x5C;neq%202,3"/> and consider computing the <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Milnor number. We compute <img src="https://latex.codecogs.com/gif.latex?&#x5C;grad(f)%20=%20(-3x^2,%202y)"/>. We can choose <img src="https://latex.codecogs.com/gif.latex?p=0"/> as a singularity, then 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mu^{&#x5C;Af^1}(0)%20=%20&#x5C;underset%200%20&#x5C;deg(&#x5C;grad%20f)%20&#x5C;&#x5C;%20=%20&#x5C;underset%200%20&#x5C;deg(x&#x5C;mapsto%20-3x^2)%20&#x5C;underset%200%20&#x5C;deg(y&#x5C;mapsto%202y),"/></p>  
  
  
since the two variables being split apart implies that we can decompose <img src="https://latex.codecogs.com/gif.latex?&#x5C;grad%20f"/> into the smash product of two maps into spheres. We know that the latter map is etale, so its degree is <img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{2}"/>. For the former, we can use the prior computation for <img src="https://latex.codecogs.com/gif.latex?x&#x5C;mapsto%20x^2"/> and just post-compose with <img src="https://latex.codecogs.com/gif.latex?x&#x5C;mapsto%203x"/>, so we obtain
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;mu^{&#x5C;Af^1}(0)%20&amp;=%20&#x5C;generators{3}(&#x5C;generators{1}%20+%20&#x5C;generators{-1})%20&#x5C;generators{2}%20&#x5C;&#x5C;&amp;=%20&#x5C;generators{-6}%20+%20&#x5C;generators{6}&#x5C;&#x5C;&amp;=%20&#x5C;generators{1}%20+%20&#x5C;generators{-1}&#x5C;&#x5C;&amp;=%20h,&#x5C;end{align*}"/></p>  
  
  
the hyperbolic form from earlier.
  
Alternatively, take a family <img src="https://latex.codecogs.com/gif.latex?y^2%20=%20x^3%20+%20ax%20%20+%20t"/>. We then have two situations, depending on whether or not <img src="https://latex.codecogs.com/gif.latex?a=0"/>:
  
![](../assets/2019-03-09-12-44-39.png )
  
The bottom represents the <img src="https://latex.codecogs.com/gif.latex?t"/> line, where the LHS shows a cusp at <img src="https://latex.codecogs.com/gif.latex?t=0"/> and otherwise some general fibers. For the RHS, there are nodes exactly when <img src="https://latex.codecogs.com/gif.latex?x^3+ax+t"/> has a double root, which happens exactly when this polynomial' discriminant is zero, which occurs at <img src="https://latex.codecogs.com/gif.latex?-27t^2-4t"/>. In particular, <img src="https://latex.codecogs.com/gif.latex?t"/> is degree 2, so there are two nodal fibers (which agrees with Milnor's theorem), and moreover if we add up the types we must get <img src="https://latex.codecogs.com/gif.latex?h"/>.
  
So for example, over <img src="https://latex.codecogs.com/gif.latex?&#x5C;FF_5"/>, we <img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{1}%20=%20&#x5C;generators{-1}"/>, so in a family, it is not possible to have one split and one non-split rational node.
  
For <img src="https://latex.codecogs.com/gif.latex?&#x5C;FF_7"/>, this is reverse, and you can't have 2 split or 2 non-split rational nodes.
  
Moral of the story: this obstructs certain kinds of arithmetic behavior within these families!
  
  
# Lecture 4
  
  
# The Euler Class
  
  
Start with the version from Algebraic Topology. Let <img src="https://latex.codecogs.com/gif.latex?X"/> be be an <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR&#x5C;dash"/>manifold of dimension <img src="https://latex.codecogs.com/gif.latex?d"/> and <img src="https://latex.codecogs.com/gif.latex?V&#x5C;surjects%20X"/> be a rank <img src="https://latex.codecogs.com/gif.latex?r"/> vector bundle with fibers <img src="https://latex.codecogs.com/gif.latex?V_x"/> for each <img src="https://latex.codecogs.com/gif.latex?x&#x5C;in%20X"/>. Recall the definition of the Thom space of <img src="https://latex.codecogs.com/gif.latex?V"/>, 
  
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Th}(V)%20&#x5C;cong%20&#x5C;PP(V&#x5C;oplus%20&#x5C;mathcal%20O)%20%20&#x2F;%20&#x5C;PP(V)%20&#x5C;homotopic%20&#x5C;frac{V}{V-X}%20&#x5C;&#x5C;"/></p>  
  
  
which can be defined on a fiber
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Th}(V_x)%20&#x5C;cong%20&#x5C;PP(V&#x5C;oplus%20&#x5C;mathcal%20O)%20%20&#x2F;%20&#x5C;PP(V_x)%20&#x5C;homotopic%20S^r"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O"/> is a trivial bundle and <img src="https://latex.codecogs.com/gif.latex?X"/> denotes the zero section.
  
**Definition**: A **bundle** <img src="https://latex.codecogs.com/gif.latex?V"/> is **oriented**  by a Thom class <img src="https://latex.codecogs.com/gif.latex?u&#x5C;in%20H^r(&#x5C;text{Th}(V);%20&#x5C;ZZ)"/> if each restriction <img src="https://latex.codecogs.com/gif.latex?H^r(&#x5C;text{Th}(V_x);%20&#x5C;ZZ)"/> yields a generator.
  
**Example**: This occurs when all transitions functions have positive determinant. Let <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20U"/> be an open cover of <img src="https://latex.codecogs.com/gif.latex?X"/>, then <img src="https://latex.codecogs.com/gif.latex?V"/> is described by clutching (transition) functions
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;theset{&#x5C;restrictionof{&#x5C;varphi}{U%20&#x5C;intersect%20W}%20&#x5C;suchthat%20U,W&#x5C;in&#x5C;mathcal%20U}%20&#x5C;text{%20where%20}%20&#x5C;det%20&#x5C;restrictionof{&#x5C;varphi}{U&#x5C;intersect%20W}%20&gt;%200"/></p>  
  
  
if and only if <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20V%20=%20L^{&#x5C;tensor%202}"/> for some line bundle <img src="https://latex.codecogs.com/gif.latex?L%20&#x5C;surjects%20X"/>. Note that we can do this because if the determinant is greater than zero, we can take a square root, and if we take a positive square root the cocycle condition is still satisfied.
  
**Definition**: A **space** <img src="https://latex.codecogs.com/gif.latex?X"/> is **oriented** iff its tangent space <img src="https://latex.codecogs.com/gif.latex?TX"/> is oriented.
  
Assume <img src="https://latex.codecogs.com/gif.latex?X"/> is a compact manifold and <img src="https://latex.codecogs.com/gif.latex?d=r"/>, then by Poincare duality we obtain an isomorphism <img src="https://latex.codecogs.com/gif.latex?H^r(X;%20&#x5C;ZZ)%20&#x5C;cong%20&#x5C;ZZ"/>, and so <img src="https://latex.codecogs.com/gif.latex?e(V)&#x5C;in%20&#x5C;ZZ"/> is an integer.
  
We can compute the Euler class in the following way: choose a section <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> with only isolated zeros, then 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?e(V)%20=%20&#x5C;sum_{~~x&#x5C;in%20X&#x5C;&#x5C;%20&#x5C;sigma(x)%20&#x5C;neq%200}%20&#x5C;deg_x(&#x5C;sigma)"/></p>  
  
where we sum the local degrees, and <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> is locally identified with a function 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma:%20&#x5C;RR^d%20&#x5C;to%20&#x5C;RR^r%20&#x5C;&#x5C;&#x5C;text{coordinates%20on%20}%20X%20&#x5C;mapsto%20&#x5C;text{local%20trivialization}"/></p>  
  
by choosing local coordinates and a local trivialization compatible with the standard orientations of the spheres in the domain and codomain.
  
Note that if we composed the trivialization with an element of <img src="https://latex.codecogs.com/gif.latex?&#x5C;GL(U)"/> with negative determinant, that would change the local degree so this definition wouldn't make sense for relative orientations -- however, if we change coordinates for <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR^d"/> and <img src="https://latex.codecogs.com/gif.latex?&#x5C;RR^r"/> simultaneously, it will.
  
**Definition:** The bundle <img src="https://latex.codecogs.com/gif.latex?V&#x5C;surjects%20X"/> is **relatively oriented** iff <img src="https://latex.codecogs.com/gif.latex?&#x5C;hom(&#x5C;det%20TX,%20&#x5C;det%20V)"/> is oriented.
  
We know what it means for such a homomorphism to be positive, and this won't change the value of the local index.
  
Since <img src="https://latex.codecogs.com/gif.latex?V"/> has an orientation sheaf, let <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O(V)"/> be a local system on <img src="https://latex.codecogs.com/gif.latex?X"/> with <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O(V)_x%20=%20H^r(&#x5C;text{Th}(V_x);%20&#x5C;ZZ)"/>. We can then use the Thom isomorphism to get a Thom class, so we have <img src="https://latex.codecogs.com/gif.latex?e(V)%20&#x5C;in%20H^r(X;%20&#x5C;mathcal%20O(-V))"/> which comes from a canonical map. So when <img src="https://latex.codecogs.com/gif.latex?V&#x5C;to%20X"/> is relatively oriented, we again have <img src="https://latex.codecogs.com/gif.latex?e(V)%20&#x5C;in%20&#x5C;ZZ"/>.
  
# <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> Algebraic Topology
  
  
Let <img src="https://latex.codecogs.com/gif.latex?X&#x5C;in&#x5C;Sm"/> be a smooth scheme of dimension <img src="https://latex.codecogs.com/gif.latex?d"/> and <img src="https://latex.codecogs.com/gif.latex?V&#x5C;surjects%20X"/> an algebraic bundle of rank <img src="https://latex.codecogs.com/gif.latex?r"/>.
  
**Definition**: <img src="https://latex.codecogs.com/gif.latex?V"/> is oriented by the data <img src="https://latex.codecogs.com/gif.latex?L&#x5C;surjects%20X"/> a line bundle and an isomorphism <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20V%20&#x5C;cong%20L^{&#x5C;tensor%202}"/>.
  
**Definition**: <img src="https://latex.codecogs.com/gif.latex?V"/> is **relatively oriented** if <img src="https://latex.codecogs.com/gif.latex?&#x5C;hom(&#x5C;det%20TX,%20&#x5C;det%20V)"/> is oriented.
  
**Example:** Consider both <img src="https://latex.codecogs.com/gif.latex?X%20=%20&#x5C;PP^n"/> and <img src="https://latex.codecogs.com/gif.latex?X%20=%20&#x5C;Gr(m,n)"/> be the Grassmannian parameterizing subspaces <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^m%20&#x5C;leq%20&#x5C;PP^n"/>.  Then <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20TX%20=%20&#x5C;mathcal%20O(n+1)"/>, the dual of the tautological tensored <img src="https://latex.codecogs.com/gif.latex?n+1"/> times -- for the Grassmannian, you put it in the Plucker embedding and pull back the <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O(1)"/>.
  
<img src="https://latex.codecogs.com/gif.latex?&#x5C;therefore%20X"/> is orientable <img src="https://latex.codecogs.com/gif.latex?&#x5C;iff%20n"/> is odd.
  
This follows because we can take <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O(%20&#x5C;frac{n+1}%20{2})"/> and choose the morphism required in the definition above.
  
**Example**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathcal%20O(n)%20&#x5C;surjects%20&#x5C;PP^1"/> is orientable if and only if it is relatively orientable if and only if <img src="https://latex.codecogs.com/gif.latex?n"/> is even.
  
**Example**: Take <img src="https://latex.codecogs.com/gif.latex?&#x5C;OO(d)&#x5C;oplus%20&#x5C;OO(e)%20&#x5C;to%20&#x5C;PP^2"/>. Since <img src="https://latex.codecogs.com/gif.latex?2+1=3"/> is odd, this is orientable if and only if <img src="https://latex.codecogs.com/gif.latex?d+e"/> is odd. 
> Note: S. McKean uses this to make an enriched Bezout's theorem for the intersection of plane curves of degree <img src="https://latex.codecogs.com/gif.latex?d"/> and <img src="https://latex.codecogs.com/gif.latex?e"/>.
  
## Computing Euler Classes for Relatively Orientable Bundles
  
> Joint with Jesse Kass
  
In addition to the prior assumptions, let <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> be a section of <img src="https://latex.codecogs.com/gif.latex?V"/> with only isolated zeros and use the same definition of <img src="https://latex.codecogs.com/gif.latex?e(V)"/>, which will land in the Grothendieck-Witt group <img src="https://latex.codecogs.com/gif.latex?GW(k)"/> instead of <img src="https://latex.codecogs.com/gif.latex?&#x5C;ZZ"/>.
  
what remains is to define the local degree. We'll proceed in the same way by finding a function, which will give us local coordinates and a local trivialization.
  
**Definition**: The **Nisnevich** coordinates near <img src="https://latex.codecogs.com/gif.latex?x"/> are given by 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;varphi:%20U%20&#x5C;to%20&#x5C;Af^d"/></p>  
  
which induces an isomorphism on the function field, so the induced extension of residue fields <img src="https://latex.codecogs.com/gif.latex?k(&#x5C;varphi(p))%20&#x5C;injects%20k(p)"/> is an isomorphism.
  
- Such coordinates determine a distinguished section of <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20TX(U)"/>
- A local trivialization <img src="https://latex.codecogs.com/gif.latex?&#x5C;restrictionof{&#x5C;varphi}{U}%20&#x5C;to%20&#x5C;OO^r"/> determines a distinguished section of <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20V(U)"/>
  
And so we can make the following definition:
  
**Definition**: Local coordinates and a local trivialization are **compatible** if for these distinguished sections, we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;hom(&#x5C;det%20TX(U),%20V(U))%20&#x5C;cong%20L^{&#x5C;tensor%202}."/></p>  
  
  
So we can get compatibility by varying the trivialization until we get a square (no problem). Nisnevich coordinates will always exist when <img src="https://latex.codecogs.com/gif.latex?k(p)"/> is a separable extension of <img src="https://latex.codecogs.com/gif.latex?k"/>, or the dimension is 1 (by Galois theory).
  
So suppose we have local coordinates <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi"/> and a local trivialization <img src="https://latex.codecogs.com/gif.latex?&#x5C;pi"/> that are compatible. If <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi:%20U%20&#x5C;injects%20&#x5C;Af^d"/> is an open immersion, then our section <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> is a function can be identified by pulling back <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma:%20&#x5C;Af^d%20&#x5C;to%20&#x5C;Af^r"/> and defining <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_p(&#x5C;sigma)%20&#x5C;definedas%20&#x5C;deg_{&#x5C;phi(p)}(&#x5C;sigma)"/>.
  
Note that we don't actually need the immersion condition here, since the <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^1"/> local degree is finitely determined, and so modifying the function by something in a high enough power of the maximal ideal doesn't change the degree. So if the <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi"/> given by Nisnevich coordinates is an etale map where the local rings aren't isomorphic, then <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> could fail to be pulled back from <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^d"/>. However, we could just add something from a really high power of the maximal ideal, and it can be shown that <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> is pulled back from <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^d"/>. These choices don't affect the outcome, so the assumption is not necessary by "finite determinacy of <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_p"/>". 
  
> Need to show that it is well-defined (i.e. it doesn't depend on choice of section), which it is under some conditions.
  
# Relations to Chow Groups
  
  
Other perspectives: 
  
Barge Morel has one that lands in the oriented Chow, <img src="https://latex.codecogs.com/gif.latex?e(v)%20&#x5C;in%20&#x5C;widetilde{&#x5C;text{Ch}}{}^r(X,%20&#x5C;det%20(-V))"/>.
> Note that you can use <img src="https://latex.codecogs.com/gif.latex?V"/> or <img src="https://latex.codecogs.com/gif.latex?-V"/> here, since the action of <img src="https://latex.codecogs.com/gif.latex?GW"/> has trivial squares, and the definition of the twist for oriented chow groups means that changing the twist by the square of a bundle doesn't effect the oriented chow groups. 
  
It is defined as follows:
  
There is a distinguished element <img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{1}&#x5C;in%20&#x5C;widetilde{&#x5C;text{Ch}}{}^0(X)"/> which is determined by a complex
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;cdots%20&#x5C;to%20&#x5C;bigoplus_{z&#x5C;in%20X^{(0)}}%20GW(k(Z),%20&#x5C;det%20T_zX)%20&#x5C;to%20&#x5C;bigoplus_{z&#x5C;in%20X^{(-1)}}%20GW(k(Z),%20&#x5C;det%20T_zX)"/></p>  
  
  
where <img src="https://latex.codecogs.com/gif.latex?X^{(0)}"/> are reduced irreducible subschemes of <img src="https://latex.codecogs.com/gif.latex?X"/>, and the RHS disappears because it's the generic point.
  
In Algebraic Topology, the definition of the Thom class involves a canonical map <img src="https://latex.codecogs.com/gif.latex?&#x5C;text{Th}(-V)&#x5C;to%20X"/>, making the class land in <img src="https://latex.codecogs.com/gif.latex?H^0(&#x5C;text{Th}(-V)"/> which under the Thom isomorphism gives something in <img src="https://latex.codecogs.com/gif.latex?H^r"/> with a twist. An analog in this setting is the following pushforward.
  
Let <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> denote the zero section of <img src="https://latex.codecogs.com/gif.latex?V&#x5C;covers%20X"/>, then there is a pushforward map
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_*:%20&#x5C;widetilde{&#x5C;text{Ch}}{}^0(X)%20&#x5C;to%20&#x5C;widetilde{&#x5C;text{Ch}}{}^r(V,%20&#x5C;det%20p^*%20V)"/></p>  
  
  
where the source with ordinarily have a twist by the canonical, but when pulled back it will disappear.
  
> Note: the difference between the canonical bundle of <img src="https://latex.codecogs.com/gif.latex?V"/> and the twist we had to do to get rid of <img src="https://latex.codecogs.com/gif.latex?X"/> is like the difference between <img src="https://latex.codecogs.com/gif.latex?TV"/> and <img src="https://latex.codecogs.com/gif.latex?TX"/>, yielding the determinant appearing on the RHS.
  
The map <img src="https://latex.codecogs.com/gif.latex?p"/> also yields an isomorphism
<p align="center"><img src="https://latex.codecogs.com/gif.latex?p^*:%20&#x5C;widetilde{&#x5C;text{Ch}}{}^r(X,%20&#x5C;det%20V)%20&#x5C;to%20&#x5C;widetilde{&#x5C;text{Ch}}{}^r(V,%20&#x5C;det%20p^*%20V)"/></p>  
  
  
and so we define
<p align="center"><img src="https://latex.codecogs.com/gif.latex?e(V)%20&#x5C;definedas%20(p^*)^{-1}&#x5C;sigma_*(&#x5C;generators{1})."/></p>  
  
  
If <img src="https://latex.codecogs.com/gif.latex?V%20&#x5C;surjects%20X"/> is relatively oriented, there is a map <img src="https://latex.codecogs.com/gif.latex?X%20&#x5C;mapsvia%20&#x5C;pi%20&#x5C;spec(k)"/> and so <img src="https://latex.codecogs.com/gif.latex?&#x5C;pi_*%20e(V)%20&#x5C;in%20GW(k)"/>.
  
Other perspectives
  
- There is a different perspective of Morel and Mark Levine, giving the Euler class as the principal obstruction to having a nonvanishing section. This is known to be equal to the one given above, up to a unit (<img src="https://latex.codecogs.com/gif.latex?&#x5C;generators{a}"/>)
- A six functor formalism
- Mike Hopkins 
- Raxit and Levine?
  
# Example Computations
  
  
**Example**: Let <img src="https://latex.codecogs.com/gif.latex?n"/> be even, and <img src="https://latex.codecogs.com/gif.latex?V%20=%20&#x5C;OO_{&#x5C;PP^1}(n)"/> which can be thought of as meromorphic functions that have a pole of order at most <img src="https://latex.codecogs.com/gif.latex?n"/> at some point, say zero. Then in local coordinates, the function 1 looks like <img src="https://latex.codecogs.com/gif.latex?x^n"/>, and so <img src="https://latex.codecogs.com/gif.latex?e(V)%20=%20&#x5C;deg_0%20x^n%20=%20{n&#x5C;over%202}%20h%20=%20{n&#x5C;over%202}(&#x5C;generators{1}%20+%20&#x5C;generators{-1})"/>. 
  
> Ordinary vector bundles in Algebraic Topology for odd-dimensional vector bundles are 2-torsion. Moreover, by a result of Levine, since this is a line bundle we know that the Euler class will be a multiple of <img src="https://latex.codecogs.com/gif.latex?h"/>. A similar argument works here?
  
**Example**: How many lines meet 4 general lines in <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^3"/>?
Follows joint work with Srinivasan, also in Schubert Calculus paper (Mathies Wendt)
  
Lines in <img src="https://latex.codecogs.com/gif.latex?&#x5C;PP^3"/> are parameterized by <img src="https://latex.codecogs.com/gif.latex?&#x5C;Gr(1,3)"/>, which is equivalent to <img src="https://latex.codecogs.com/gif.latex?W%20&#x5C;subseteq%20k^{&#x5C;oplus%204},%20&#x5C;dim%20W%20=%202"/>. Let 
- <img src="https://latex.codecogs.com/gif.latex?L_i"/> be 4 lines, no two of which intersect
- <img src="https://latex.codecogs.com/gif.latex?e_i"/> be a basis of <img src="https://latex.codecogs.com/gif.latex?k^4"/>
- <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi_i"/> be the corresponding dual basis
  
where <img src="https://latex.codecogs.com/gif.latex?L_1%20=%20&#x5C;PP(ke_3&#x5C;oplus%20ke_4)%20=%20&#x5C;theset{&#x5C;phi_1=&#x5C;phi_2%20=%200}"/>. Lets find a condition on bundles for lines that intersect <img src="https://latex.codecogs.com/gif.latex?L_1"/>.
  
Let <img src="https://latex.codecogs.com/gif.latex?L=%20&#x5C;PP(k&#x5C;tilde%20e_3%20&#x5C;oplus%20k&#x5C;tilde%20e_4)"/>, the span of some two linearly independent vectors. If we wrote these out in terms of <img src="https://latex.codecogs.com/gif.latex?e_i"/>, we'd need to find a combination where the coefficients of <img src="https://latex.codecogs.com/gif.latex?e_1,%20e_2"/> vanish, i.e. there needs to be a linear dependence in the part of their basis expansion involving these two elements. We thus get the condition
<p align="center"><img src="https://latex.codecogs.com/gif.latex?L&#x5C;intersect%20L_1%20&#x5C;iff%20(&#x5C;phi_1%20&#x5C;wedge%20&#x5C;phi_2)(&#x5C;tilde%20e_3%20&#x5C;wedge%20&#x5C;tilde%20e_4)%20=%200"/></p>  
  
  
So we look at the line bundle <img src="https://latex.codecogs.com/gif.latex?S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual%20&#x5C;covers%20&#x5C;Gr(1,3)"/>, where the fiber above a dimension 2 subspace <img src="https://latex.codecogs.com/gif.latex?W"/> is given by <img src="https://latex.codecogs.com/gif.latex?(S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual)_{&#x5C;PP%20W}%20=%20W^&#x5C;dual%20&#x5C;wedge%20W^&#x5C;dual"/>.
  
Then <img src="https://latex.codecogs.com/gif.latex?&#x5C;theset{&#x5C;phi_1,%20&#x5C;phi_2}"/> determine a section <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_1"/> of <img src="https://latex.codecogs.com/gif.latex?S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual"/> by <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_1(&#x5C;PP%20W)%20=%20&#x5C;restrictionof{&#x5C;phi_1}{W}%20&#x5C;wedge%20&#x5C;restrictionof{&#x5C;phi_2}{W}"/>, where lines intersection <img src="https://latex.codecogs.com/gif.latex?L_1"/> correspond exactly to zeros of <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma_1"/>.
  
We can do the same thing for the other <img src="https://latex.codecogs.com/gif.latex?L_i"/> and combine them to get a section of <img src="https://latex.codecogs.com/gif.latex?V%20&#x5C;definedas%20&#x5C;oplus_{i=1}^4S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual"/>, whose zeros are the lines we're looking for.
  
Is this bundle relatively orientable? <img src="https://latex.codecogs.com/gif.latex?&#x5C;det%20TX%20=&#x5C;OO(4),%20&#x5C;det%20V%20=%20(S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual)^{&#x5C;tensor%204}"/>, which are both tensor squares, so yes.
  
Following the recipe, we need to identify <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> with a function. To compute <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_{&#x5C;PP%20W}(&#x5C;sigma)"/>, choose local coordinates on <img src="https://latex.codecogs.com/gif.latex?&#x5C;Gr(1,3)"/>. So we need to choose dimension 2 subspaces parameterized by <img src="https://latex.codecogs.com/gif.latex?&#x5C;Af^4"/>, so we'll pick the lines which intersect <img src="https://latex.codecogs.com/gif.latex?&#x5C;theset{&#x5C;phi_3=%20&#x5C;phi_4%20=%200}"/>, yielding a new basis
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;begin{align*}&#x5C;tilde%20e_1%20&amp;=%20e_1%20&#x5C;&#x5C;&#x5C;tilde%20e_2%20&amp;=%20e_2%20&#x5C;&#x5C;&#x5C;tilde%20e_3%20&amp;=%20xe_1%20+%20ye_2%20+%20e_3%20&#x5C;&#x5C;&#x5C;tilde%20e_4%20&amp;=%20x&#x27;e_1%20+%20y&#x27;e_2%20+%20e_4%20&#x5C;&#x5C;&#x5C;end{align*}"/></p>  
  
  
We then have an open subset
<p align="center"><img src="https://latex.codecogs.com/gif.latex?U%20=&#x5C;spec(k[x,y,x&#x27;,y&#x27;])%20&#x5C;injects%20&#x5C;Gr(1,3)%20&#x5C;&#x5C;(x,y,x&#x27;,y&#x27;)%20&#x5C;mapsto%20&#x5C;PP(k&#x5C;tilde%20e_3%20+k&#x5C;tilde%20e_4),"/></p>  
  
  
so we have some local coordinates. Let <img src="https://latex.codecogs.com/gif.latex?&#x5C;tilde%20&#x5C;phi_i"/> be the dual basis.
  
Next we choose a local trivialization, where <img src="https://latex.codecogs.com/gif.latex?S^&#x5C;dual%20&#x5C;wedge%20S^&#x5C;dual"/> can be locally trivialized by <img src="https://latex.codecogs.com/gif.latex?&#x5C;tilde&#x5C;phi_3%20&#x5C;wedge%20&#x5C;tilde%20&#x5C;phi_4"/> which are compatible with some relative orientation.
  
The expression for the function <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma"/> will depend on our choice of line, and instead of notating all of them, just assume that <img src="https://latex.codecogs.com/gif.latex?L_1%20=%20&#x5C;PP(ke_3%20&#x5C;oplus%20ke_4)"/>. We then get <img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma%20=(&#x5C;phi_1%20&#x5C;wedge%20&#x5C;phi_2,%20?,%20?,%20?)"/> where we just didn't notate the other components. So what is this first component in terms of <img src="https://latex.codecogs.com/gif.latex?x&#x27;,%20y&#x27;"/>? This amounts to finding the coordinate of <img src="https://latex.codecogs.com/gif.latex?&#x5C;tilde&#x5C;phi_3%20&#x5C;wedge%20&#x5C;tilde&#x5C;phi_4"/> is in <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi_1%20&#x5C;wedge%20&#x5C;phi_2"/>, which is just a linear algebra problem.
  
We want to find the coefficient <img src="https://latex.codecogs.com/gif.latex?c"/> in 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;restrictionof{(&#x5C;phi_1%20&#x5C;wedge%20&#x5C;phi_2)}{k&#x5C;tilde%20e_3%20&#x5C;oplus%20k&#x5C;tilde%20e_4}%20=%20c%20(&#x5C;tilde&#x5C;phi_3%20&#x5C;wedge%20&#x5C;tilde&#x5C;phi_4)"/></p>  
  
  
How many <img src="https://latex.codecogs.com/gif.latex?&#x5C;tilde%20e_3"/> are in <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi_1"/>? We can evaluate <img src="https://latex.codecogs.com/gif.latex?&#x5C;phi_1(&#x5C;tilde%20e_3)"/> to get how many <img src="https://latex.codecogs.com/gif.latex?&#x5C;tilde%20&#x5C;phi_3"/>s we need, but that's just <img src="https://latex.codecogs.com/gif.latex?x"/>. So the RHS evaluates to <img src="https://latex.codecogs.com/gif.latex?(x%20&#x5C;tilde&#x5C;phi_3%20&#x5C;wedge%20y&#x5C;tilde&#x5C;phi_4)%20+%20(x&#x27;&#x5C;tilde&#x5C;phi_3%20&#x5C;wedge%20y&#x27;&#x5C;tilde&#x5C;phi_4)"/>, and we obtain <img src="https://latex.codecogs.com/gif.latex?c%20=%20xy&#x27;%20-yx&#x27;"/>. We can thus write
<p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;sigma:%20&#x5C;Af^4%20&#x5C;to%20&#x5C;Af^4%20&#x5C;&#x5C;&#x5C;sigma(x,y,x&#x27;,y&#x27;)%20=%20(xy&#x27;%20-yx&#x27;,%20?,%20?%20,%20?)"/></p>  
  
  
Now we can compute the local degree by taking the Jacobian and taking the determinant, but what AG/Arithmetic information is contained in this huge polynomial in <img src="https://latex.codecogs.com/gif.latex?x,y,x&#x27;,y&#x27;"/>s? Is there an AG interpretation of this local degree <img src="https://latex.codecogs.com/gif.latex?&#x5C;deg_P(&#x5C;sigma),%20where"/>P=L<img src="https://latex.codecogs.com/gif.latex?is%20a%20point%20on%20the%20Grassmannian?Well"/>L=\PP W<img src="https://latex.codecogs.com/gif.latex?intersects"/>L_i<img src="https://latex.codecogs.com/gif.latex?,%20so%20we%20have%204%20points%20on"/>L\cong \PP^1_{k(L)}<img src="https://latex.codecogs.com/gif.latex?,%20and%20therefore%20we%20have%20a%20cross-ratio"/>\lambda<img src="https://latex.codecogs.com/gif.latex?.We%20can%20get%20another%20cross-ratio%20by%20looking%20at%20planes%20in"/>\PP^3<img src="https://latex.codecogs.com/gif.latex?containing"/>L<img src="https://latex.codecogs.com/gif.latex?,%20i.e.%20dimension%203%20subspaces"/>V<img src="https://latex.codecogs.com/gif.latex?containing"/>W<img src="https://latex.codecogs.com/gif.latex?,%20so%20we%20have%20&lt;p%20align=&quot;center&quot;&gt;&lt;img%20src=&quot;https:&#x2F;&#x2F;latex.codecogs.com&#x2F;gif.latex?W%20&amp;#x5C;subseteq%20V%20&amp;#x5C;subseteq%20k(L)^4&quot;&#x2F;&gt;&lt;&#x2F;p&gt;%20%20where"/>\dim V = 1<img src="https://latex.codecogs.com/gif.latex?,%20so%20each%20plane%20is%20a"/>\PP^1_{k(L)}<img src="https://latex.codecogs.com/gif.latex?.%20We%20get%204%20planes%20containing"/>L<img src="https://latex.codecogs.com/gif.latex?,%20namely%20the%204%20planes%20spanned%20by%20each%20pair"/>(L, L_i)<img src="https://latex.codecogs.com/gif.latex?.%20This%20provides%20a%20second%20cross-ratio"/>\mu<img src="https://latex.codecogs.com/gif.latex?Although%20there%20was%20choice,%20since%20our%20section%20was%20determined%20not%20by"/>L<img src="https://latex.codecogs.com/gif.latex?but%20rather%20by%20the%20zero%20set%20of%20some%20functions,%20normalizing%20things%20correctly%20yields&lt;p%20align=&quot;center&quot;&gt;&lt;img%20src=&quot;https:&#x2F;&#x2F;latex.codecogs.com&#x2F;gif.latex?&amp;#x5C;deg_L(&amp;#x5C;sigma)%20=%20&amp;#x5C;Tr_{k(L)%20&amp;#x2F;%20k}&amp;#x5C;generators{&amp;#x5C;lambda-&amp;#x5C;mu}.&quot;&#x2F;&gt;&lt;&#x2F;p&gt;%20%20We%20thus%20obtain%20a%20theorem:**Theorem**:&lt;p%20align=&quot;center&quot;&gt;&lt;img%20src=&quot;https:&#x2F;&#x2F;latex.codecogs.com&#x2F;gif.latex?&amp;#x5C;sum_{&amp;#x5C;quad%20L%20&amp;#x5C;suchthat%20&amp;#x5C;&amp;#x5C;%20L%20&amp;#x5C;intersect%20L_i%20&amp;#x5C;neq&amp;#x5C;emptyset}&amp;#x5C;Tr_{k(L)%20&amp;#x2F;%20k}&amp;#x5C;generators{&amp;#x5C;lambda-&amp;#x5C;mu}%20=%20&amp;#x5C;generators{1}%20+%20&amp;#x5C;generators{-1}%20=%20h&quot;&#x2F;&gt;&lt;&#x2F;p&gt;"/>\qed<img src="https://latex.codecogs.com/gif.latex?#%20Where%20Things%20Are%20Going-%20Gromov-Witten%20invariants%20with%20Jake%20and%20Jesse-%20Welschinger%20invariants,%20Mark%20LevineThese%20produce%20more%20than%20just%20the%201s%20appearing%20in"/>h<img src="https://latex.codecogs.com/gif.latex?,%20and%20have%20ties%20to%20things%20like%20modular%20forms."/>\qed$
  
  