# MIT Course 18.06, Fall 2022

This is a repository for the course [18.06: Linear Algebra](http://web.mit.edu/18.06) at MIT in Fall 2022.   See [other branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/viewing-branches-in-your-repository) of this repository for previous semesters.

**Instructor**: [Prof. Steven G. Johnson](http://math.mit.edu/~stevenj).  Course administrator: [Sergei Korotkikh](https://math.mit.edu/directory/profile.php?pid=2113).

**Lectures**: MWF11 in 26-100.  [Handwritten notes](https://www.dropbox.com/s/a1xy4oh6wb2i5ub/18.06%20Fall%202022.pdf?dl=0) are posted online, along with video recordings ([on Canvas Panopto Video](https://mit.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=87c54afd-f3c7-4cb8-b173-af0e00faf1d0)) and other materials (slides, further reading) in the lecture summaries below.

**Exams**: 11am in 26-100, on 10/7, 11/14, & 12/9.  Final exam: 12/22 9am-noon in Dupont Gym.

**Recitations**:

 * R01,R02 — [Chirag Falor](https://web.mit.edu/directory/?id=cfalor&d=mit.edu): T9 in 2-143, T10 in 2-146 (office hours Mon 3pm [via Zoom](https://mit.zoom.us/j/96071172098), Wed 3pm in 2-449).
 * R03,R05 — [Melissa Sherman-Bennett](https://sites.google.com/view/mshermanbennett): T11 in 2-147, T12 in 2-147 (office hours Wed 10am [via Zoom](https://mit.zoom.us/j/96071172098), Thurs 10am in 2-136).
 * R04 — [Sergei Korotkikh](https://math.mit.edu/directory/profile.php?pid=2113): T11 in 2-146 (office hours Tues 6pm [via Zoom](https://mit.zoom.us/j/96071172098), Thurs 6pm in 2-231D).
 * R06,R09 — [Victor Rong](https://web.mit.edu/directory/?id=vrong&d=mit.edu): T12 in 2-146, T1 in 2-146 (office hours Mon 8pm [via Zoom](https://mit.zoom.us/j/96071172098), Tues 2pm in 2-361).
 * R07,R08 — [Mitchell Harris](https://math.mit.edu/directory/profile.php?pid=2180): T12 in 2-361, T1 in 2-142 (office hours Mon 2pm [via Zoom](https://mit.zoom.us/j/96071172098), Fri 2pm in 32-D707).
 * R10,R11 — [Ishan Levy](https://math.mit.edu/directory/profile.php?pid=2185): T1 in 2-136, T2 in 2-142 (office hours Thurs 10:30am [via Zoom](https://mit.zoom.us/j/96071172098), Wed 2pm in 2-390).
 * R12,R13 — [Gefei Dang](https://math.mit.edu/directory/profile.php?pid=2178): T2 in 2-146, T3 in 2-142 (office hours Thurs 4pm [via Zoom](https://mit.zoom.us/j/96071172098), Wed 5pm in 2-239).

**Undergraduate Assistants**: Raza Abbas, Alvin Chen, Christina Mirro, and Daniel Villagran.   Email them at **1806fall22_ua ατ mit.edu** for 1-on-1 technical help with Julia or other questions that don't work well over Piazza etc.

**Resources**: [Piazza discussion forum](https://piazza.com/class/l7g5ixuivav3rm), [math learning center](https://math.mit.edu/learningcenter/), [TSR^2 study/resource room](https://ome.mit.edu/programs/talented-scholars-resource-room-tsr2), [pset partners](https://psetpartners.mit.edu/).

This document is a *brief* summary of what was covered in each 18.06
lecture, along with links and suggestions for further reading.  It is
*not* a good substitute for attending lecture, but may provide a
useful study guide.  (You can also look at the analogous summaries from [Spring 2022](https://github.com/stevengj/1806/blob/spring22/README.md).)

## Lecture 1 (Sep 7)

* [course overview/syllabus](https://docs.google.com/presentation/d/1ivbV1nr67XfasBdXezZF9UWILzDoQtQev8vSqRKBfu0/edit?usp=sharing)
* [pset 1](psets/pset1.ipynb): due **Friday Sep 16 at 11am** (submit your solutions on Gradescope).
* [video](https://mit.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=19855fd0-d2be-4252-aa41-af0900816383)

Slides giving the syllabus and the "big picture" of what 18.06 is about.  Introduction to thinking about matrices as linear operations, not just as "bags of numbers".

**Further reading**: Strang, chapter 1, and section 8.1 on linear transformations.  3blue1brown has a nice video on [matrix multiplication as composition of linear transformations](https://youtu.be/XkY2DOUCWMU).  If you've forgotten the basics of how to multiply matrices by vectors or matrices by matrices, google for some tutorial material online (e.g. [Khan academy](https://www.khanacademy.org/math/precalculus/x9e81a4f98389efdf:matrices/x9e81a4f98389efdf:multiplying-matrices-by-matrices/a/multiplying-matrices)) and do a quick brush-up.

## Lecture 2 (Sep 9)

* handwritten notes: see link above (at beginning)
* [video](https://mit.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=b9662b0d-6280-448a-b745-af090062417b)

[Gaussian
elimination](https://en.wikipedia.org/wiki/Gaussian_elimination) for **Ax=b**:  I
started with the grade-school/high-school viewpoint of writing out three equations
in three unknowns, adding/subtracting multiples of equations until we
were left with one equation in one unknown.  Then, I wrote the
same equations in matrix form, and renamed this process "Gaussian
elimination": we add/subtract multiples of matrix rows to introduce
zeros below the diagonal, i.e. to make the matrix [upper
triangular](https://en.wikipedia.org/wiki/Triangular_matrix) **U**.  We then do the same row operations to the right hand side **b** to get a new vector **c**.  Finally, we solve **Ux=c** for x by working from bottom (1 equation in 1 variable) to top, a process called "backsubstitution".

To do the same operations to both **A** and **b**, a useful trick for hand calculations is to [augment](https://en.wikipedia.org/wiki/Augmented_matrix) the matrix with a new column representing the right-hand side, forming **[A b]** before starting Gaussian elimination.

What comes next?  The problem with expressing Gaussian elimination this way, as operations on individual numbers in the matrix, is that it is impossible to follow the process in detail for anything except a very tiny matrix.   We need a higher-level "algebraic" way to express the process, both to help us understand it and also to help us to *use* it (e.g. to perform additional algebraic transformations afterwards).   To do this, we want to express the process, not as operations on individual numbers, but as matrix operations.

Rewrote Gaussian elimination in matrix form: we multiply a matrix A on the *left* by a sequence of **lower**-triangular "elimination matrices" Eₙ to arrive at an **upper**-triangular matrix U = EA.  To solve Ax=b, we can think of the earlier process as multiplying *both sides* on the *left* by **E**, the linear operator representing the composition (product) of all of the elimination steps, yielding Ux=EAx on the left and c=Eb on the right.

We're not done: it turns out to be even more fruitful to *reverse* the process, and write A = LU: L represents the operations required to turn the matrix U back into A, and turns out toe be a **lower**-triangular matrix whose entries are just a record of the elimination steps.  This **LU factorization** is extremely useful and important because it allows us to replace a *complicated* matrix A with two *much simpler* (triangular) ones.  For example, solving Ax=b turns into LUx=b, and we can do this just by two "triangular" solves.  More on this next time.

**Further reading:** Textbook sections 2.1, 2.2, 2.3.  Strang [lecture 2 video](https://www.youtube.com/watch?v=QVKj3LADCnA&list=PLE7DDD91010BC51F8&index=3).   And there is a Gaussian-elimination [Julia notebook](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Gaussian-elimination.ipynb) that covers the same steps in Julia form.
See also "The key reason why A = LU" in section 2.6 of the textbook.

## Lecture 3 (Feb 4): recorded

* video (only): see the [spring 2022 recording](https://mit.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=885fb286-4dab-4aa6-9ef0-ae2e00f05ceb), lecture 3
* handwritten notes
* [Matrix inverse and LU notebook](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Inverses-LU-intro.ipynb)

(Prof. Johnson is sick and so we will use the recorded lecture from spring.)

Showed that Gaussian elimination can be viewed as **LU factorization**:

* Gaussian elimination A ⟿ U=EA (without row swaps) can be thought of as A=LU: factorizing A into a **product of two simpler (triangular) matrices** (L=lower, U=upper).  U is the matrix that you normally get when you do elimination by hand, and L (the inverse of the elimination steps L=E⁻¹, a lower-triangular matrix with 1's on the diagonal) is essentially a *"record" of the elimination steps*.

L is the matrix that "reverses" Gaussian elimination: it tells you how to get A back from L.   Despite this, I showed in lecture that L is actually *easier* to get than E: all you do is make a diagonal matrix of 1's, and then fill in the *multipliers* from the elimination steps (flipping subtraction to addition) below the diagonal.  So, L just requires bookkeeping, and *no* computation.

Computing U is hard (elimination is a lot of work, even for a computer), but once you have U and L then many things that you might want to do with A become easy.

* For example, suppose you want to solve Ax=b, given A=LU.  Write LUx=b=L(Ux), and let y=Ux.  Then Ly=b, and we can solve for y by forward-substitution.  Given y, we can then solve Ux=y by back-substitution.  Both of these steps are easy because the systems are triangular.
  - Moreover, solving Ly=b turns out to *exactly* correspond to applying the elimination steps from A ⟿ U to b.   (The 1's on L's diagonal mean that there are no divisions required, either.)
* This means that we can re-use L and U to solve Ax=b for *many right-hand sides*.   In contrast, if you "augment" A with b and then do elimination (A|b)⟶(U|y), you get the *same* new right-hand side y but you haven't kept a record of the elimination steps, so if you have a new right-hand side you might naively repeat the whole elimination process (hard!) rather than solving Ly=b (easy!).
* More generally, whenever you have A as a product of "simpler" matrices (e.g. triangular, diagonal, …), you can solve Ax=b by a sequence of "simpler" solves.

Introduction to the concept of a matrix inverse more generally as the matrix that reverses the action of a linear operator.  Key ideas from the notebook:

* A⁻¹ is the matrix that does the "reverse" of A:  A⁻¹(Ax)=x for any x.   It also follows that A is the reverse of A⁻¹: A(A⁻¹x)=x for any x, i.e. (A⁻¹)⁻¹=A.
   -  That is, if Ax=b, then A⁻¹b=x (for any x).  (Equivalently, it gives the solution to Ax=b.)
   - It only exists for **square, nonsingular** matrices A.  (i.e. an m×m matrix A must give m nonzero pivots when you do elimination.)
* Equivalently, A⁻¹ is the matrix for which A⁻¹A = A⁻¹A = I (the m×m identity matrix).
  - I is an identity matrix, the matrix that gives Ix=x for any x or IA=A and AI=A for any A.  There are m×m identity matrices for all m, and when we write "I" we usually infer from context how big an I we mean.

In the next lecture (which will start with the end of this notebook), we will look at calculating inverses more generally (although it turns out that this is something that you should almost never do explicitly, even on a computer!).

**Further reading:** Textbook sections 2.5, 2.6.  Strang [lecture 4 video](https://www.youtube.com/watch?v=5hO3MrzPa0A) and [lecture 3 video](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-3-multiplication-and-inverse-matrices/).  See also "The key reason why A = LU" in section 2.6 of the textbook.

## *Optional* Julia Tutorial: recorded

* [video recording](https://mit.zoom.us/rec/share/w7o2TQjDOnHsaRlJvbS1iysu5Sh23gGVFt3nX_VShRoRBr5UCsPlMhEu1EeyQrk.Vq1WOfArkC3v-Lma?startTime=1643839179000)

(No live tutorial since Prof. Johnson is sick.)

A basic overview of the Julia programming environment for numerical computations that we will use in 18.06 for simple computational exploration.   This (Zoom-based) tutorial will cover what Julia is and the basics of interaction, scalar/vector/matrix arithmetic, and plotting — we'll be using it as just a "fancy calculator" and no "real programming" will be required.

* [Tutorial materials](https://github.com/mitmath/julia-mit) (and links to other resources)

If possible, try to install Julia on your laptop beforehand using the instructions at the above link.  Failing that, you can run Julia in the cloud (see instructions above).

## Lecture 4 (Sep 14)

* [video recording](https://mit.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=faf2a3ef-fcc2-4ff4-a928-af0900628908)
* [Matrix inverse and Gauss–Jordan](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Gauss-Jordan.ipynb)

Reviewed matrix inverses and key properties thereof.

Went through how to explicitly compute A⁻¹ by solving AA⁻¹ = I.   Essentially, this is just solving Ax=b multiple times, where b is each column of I. A common way to organize this for *hand* calculation (ugh) is the Gauss–Jordan algorithm (on a 3×3 example that can also be found in the textbook): If we do row operations on A to get I, then the *same* row operations on I give A⁻¹!  To carry this out by hand, we augment (A|I), do ordinary Gaussian elimination to get (U|C), and then do elimination "upwards" to get (I|A⁻¹).

Matrix inverses are mainly a *conceptual* tool that we use to move matrices around *symbolically* in equations.   Once you are through with your algebraic manipulations, you might end up with an expression like A⁻¹b — but when it comes time to actually *compute* the answer, you should **read "A⁻¹b" as "solve Ax=b for x by the best available method"**.

**Further reading:** Textbook sections 2.5, 2.6.  Strang [video lecture 3](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-3-multiplication-and-inverse-matrices/).


## Lecture 5 (Sep 16)

* [Video recording](https://mit.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=32b37815-81a0-42aa-a2a5-af0c00d75c55)
* [pset 1 solutions](psets/pset1sol.ipynb)
* [pset 2](psets/pset2.ipynb): due **Mon** Sep 26 (Friday is a holiday).
* [LU factorization for real](https://nbviewer.org/github/mitmath/1806/blob/master/notes/LU-for-real.ipynb)

Brief review of previous topics in LU factorization with some more examples in the notebook:

* How the L matrix entries are just the multipliers from Gaussian elimination.  No extra work is required!
* How in practice, one rarely "augments" the matrix with the right-hand side.  Instead, you compute A=LU, substitute this into Ax=b=LUx, let c=Ux, solve Lc=b, then solve Ux=c.  In particular, solving Lc=b is *exactly* the same as performing the Gaussian-elimination steps on c.  (The "augmented" method is a little easier for human bookkeeping, but has essentially no advantage for the computer.)

Some new information about LU to complete the story:

* Given A=LU, you can efficiently solve multiple right-hand sides, or equivalently the **matrix equation** AX=B.
* How row swaps lead to the factorization PA=LU: in practice, the computer *almost always* does row swaps, and *always* gives you a permutation matrix P (or its equivalent).

We apply PA=LU to Ax=b in much the same way as for LU; the only difference is that we have to first apply the permutation P to b.

Permutation matrices P are a great example of a linear operator that is often easier to understand (and more efficient) if you *don't* write it as a matrix, but instead write it as a "vector" `p` of the permuted indices 1…n in the new order.  Then Px is just `x[p]` in Julia (and very similarly in Matlab and Numpy): just make a new vector by extracting the components p₁,p₂,… of x.

**Further reading:** Textbook sections 2.7 (on permutations; we will talk about transposes soon), and 11.1.  Strang [video lecture 4](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-4-factorization-into-a-lu/) and [video lecture 5](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-5-transposes-permutations-spaces-r-n/).   For 18.06, I *don't expect you to know* the details of how the permutation P in PA=LU is constructed even though you don't know the permutation in advance … you only need to know how to *use* PA=LU if it (or something similar) is *given* to you … but if you are interested this "partial pivoting" algorithm is described in lecture 21 of *Numerical Linear Algebra* by Trefethen and Bau, or in many other textbooks on numerical linear algebra.

## Lecture 6 (Sep 19)

* video: Panopto Video link on Canvas
* handwritten notes
* [Computational complexity](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Complexity.ipynb)

Complexity of matrix operations: why matrix × vector or backsubstitution scale like n² for n×n matrices, while matrix × matrix or Gaussian elimination (LU factorization) scale like n³.   Matrices much bigger than a few thousand square quickly become impractical, and really large problems are only tractable because they have special structure like [sparsity](https://en.wikipedia.org/wiki/Sparse_matrix).

The next few weeks will be devoted to problems arising from **singular** and **non-square** matrices.   A "singular" square matrix is one for which we "run out of pivots" when doing elimination (we hit zeros on the diagonal we can't remove with row swaps).   Non-square matrices are either "tall" (arising in **overdetermined** systems with more equations than unknowns, leading to **fitting** problems and *approximate* solutions) or "wide" (arising in **underdetermined** systems with more unknowns than equations, leading to *freedom* in the choice of solution and *regularization* techniques to impose "priors" on this choice).   A key technique that will help us understand these equations is to **break vectors into simpler/smaller vectors**.   To do this we must first broaden our concept of a "vector".

Introduced **vector spaces** (informally, a set V of anything you can add x±y and multiply by scalars αx) and **subspaces** (a subset of V such that vector operations *stay in the subspace*).  Examples of vector spaces include real n-component vectors (ℝⁿ, or ℂⁿ for complex numbers), real m×n matrices, functions f(x) (ℝ↦ℝ, real numbers to real numbers).  Examples of subspaces includes planes or lines through the origin in ℝ³, or the origin itself.   The goal of this is to break vector spaces into smaller pieces that we can still do linear algebra on (hence the need for a subspace, not just any arbitrary subset).  Subspaces are especially important to help us understand the solutions (if any) of Ax=b for **non-square** matrices A.

**Further reading:** Textbook sections 2.6 ("The cost of elimination") and 11.1.   Section 3.1 and 3.2 on vector spaces and subspaces.

## Lecture 7 (Sep 21)

* video: Panopto Video link on Canvas
* Handwritten notes

Reviewed **vector spaces** (informally, a set V of anything you can add x±y and multiply by scalars αx) and introduced **subspaces** (a subset of V such that vector operations *stay in the subspace*).  Examples of vector spaces include real n-component vectors (ℝⁿ, or ℂⁿ for complex numbers), real m×n matrices, functions f(x) (ℝ↦ℝ, real numbers to real numbers).  Examples of subspaces includes planes or lines through the origin in ℝ³, or the origin itself.   The goal of this is to break vector spaces into smaller pieces that we can still do linear algebra on (hence the need for a subspace, not just any arbitrary subset).  Subspaces are especially important to help us understand the solutions (if any) of Ax=b for **non-square** matrices A.

For an m×n matrix A, introduced two important subspaces.

* First, the **column space C(A)**: the set {Ax for all x ∈ ℝⁿ}.  This is the set of *right-hand sides* b such that Ax=b is *solvable*, and is a subspace of the "output space" ℝᵐ (not ℝⁿ unless m=n!).  Equivalently, C(A) is all linear combinations of the *columns* of A, which we call the **span** of the columns.

* Second, the **null space N(A)** (also called the "kernel"): the set {x such that Ax=0} ⊆ ℝⁿ (i.e., a subspace of the "input space" ℝⁿ).  Given any solution x to Ax=b, then x+z is also a solution if z ∈ N(A) (i.e. Az=0 ⟹ A(x+z)=Ax+Az=Ax=b).

These are very important subspaces because they tell us a lot about the matrix A and solutions to Ax=b.  As a trivial example, if A is an n×n *invertible* matrix, C(A)=ℝⁿ and N(A)={0}.  Conversely, if A is an m×n matrix of zeros, then C(A)={0} and N(A)=ℝⁿ.

Defined a **basis** for a vector space as a *minimal* set of vectors (we will later say that they have to be *linearly independent*) whose
**span** (all linear combinations) produces everything in the space.  The number of vectors in any basis is the **dimension** of the vector space.

Showed that the **nullspace is preserved by elimination (row) operations**, but that the column space is not.   So, to find N(A), we can instead do elimination and find N(U)=N(A) for the upper-triangular form U.   We now want to find *all* possible solutions to Ax=0.

**Further reading:** Textbook, sections 3.1—3.3; Strang [video lecture 6](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-6-column-space-and-nullspace/) and [lecture 7](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-7-solving-ax-0-pivot-variables-special-solutions/).   Note that Strang's lectures and book emphasize the "reduced row echelon" ("rref") form, which is essentially a bookkeeping trick (similar to Gauss–Jordan for inverses) to do the back-solves for the special solutions all at once.  I will *not* emphasize rref form this semester, but you can use it if you want.  (In practical applications, rref form is virtually never used, and for that matter one doesn't actually use elimination at all to find null spaces; instead, one uses something called the [SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition) that we will cover later.)

## Lecture 8 (Sep 26)

* video: Panopto Video link on Canvas
* handwritten notes
* [pset 2 solutions](psets/pset2sol.ipynb)
* [pset 3](psets/pset3.ipynb): due **Friday** Sep 30

Went through two examples of finding the special solutions as a basis for the nullspace.  They key point is always this: given the free variables, we can easily solve for the corresponding pivot variables.

We can now find the **complete solution** (i.e., all solutions) to a non-square linear system Ax=b.  Elimination turns this into Ux=c. We look for solutions in the form xₚ + xₙ: a **particular solution** xₚ plus any vector xₙ in N(A) (specified explicitly from the basis).  The particular solution xₚ can be *any* solution to Ax=b, but the simplest one to find is usually to *set the free variables* to zero.  That is, we write the solution xₚ=(p; 0) where p is the unknown values in the pivot rows, setting the other (free) rows to zero, then plug into Uxₚ=c to get p.  Since this extracts the part of U that is upper triangular, we can easily solve it.   Then we add in anything in N(A).

I used a 3×4 example matrix A (similar in spirit to one in the textbook, section 3.3) that was **rank deficient**: after elimination, we only had two pivots (rank r=2) in the first two rows, and a whole row of zeros.   Furthermore, its pivot columns were the first and *third* columns, with the second and fourth columns being free — this is possible (albeit unusual)!   Showed that we could still get the special solutions by solving for the pivot variables in terms of the free variables = (1,0,…) etcetera, and we still got dimension n-r (= 2) for the null space.   When solving Ax=b by elimination into Ux=c, however, we *only got a solution x if c was zero in the same rows as U*.  If the zero third row of U was matched by a zero third row of c, then we got a particular solution as before by setting the free variables to zero.  If the zero third row of U was *not* matched by a zero third row of c, then there is *no* solution: b was *not in the column space* C(A).  This gives an easy way to check whether the right-hand-side is in the column space.  Went through an example right-hand-sides with no solutions, and in next lecture I'll cover one with infinitely many solutions.

**Further reading:** Textbook sections 3.3–3.4, [lecture 8](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-8-solving-ax-b-row-reduced-form-r/).  As noted in lecture 7, I'm not emphasizing the trick of "rref" form (used extensively by Strang's book and lectures) which makes hand calculation *slightly* easier, but might push students towards memorizing formulas (which are useless in the long run).

## Lecture 9 (Sep 28)

* handwritten notes and lecture video (see links above).

Finished the discussion of "complete solutions" of Ax=b from last lecture, by choosing a right-hand side b ∈ C(A), finding the particular solution (by setting the free variables to zero and solving for the pivot variables), and then adding in the null-space vectors to describe all possible solutions.

### Linear independence and C(A)

Bases, dimension, and independence.   Earlier, I defined a basis as a minimal set of vectors whose span gives an entire vector space, and the dimension of the space as the size of the basis.  Now, we want to think more carefully about the term "minimal".   If we have too many vectors in our basis, the problem is that some of the vectors might be redundant (you can get them from the other basis vectors).  We now rephrase this as saying that such vectors are *linearly dependent*: some linear combination (with nonzero multipliers) of them gives the zero vector, and we want every basis to be **linearly independent**.    The **dimension** of a subspace is still the number of basis vectors.

What does it mean to be linearly independent?  Given a set of n vectors {x₁, ⋯, xₙ}, if we matrix a matrix X whose columns
are x₁⋯xₙ, then C(X) is precisely the span of x₁⋯xₙ.   To check whether
the x₁⋯xₙ form a *basis* for C(X), we need to check whether they
are *linearly independent*.  There are three equivalent ways to think about
this:

1. We want to make sure that none of x₁⋯xₙ are "redundant": make sure
   that no xⱼ can be made from a linear combination of the other xᵢ's.

2. Equivalently, we don't want any linear combination of x₁⋯xₙ to give
   zero unless all the coefficients are zero.

3. Equivalently, we want N(X) = {0}.

In this way, we reduced the concept of independence to thinking about the
null space.   Since the nullspace is preserved by elimination, it follows
that *columns of A are dependent/independent if and
only if the corresponding columns of R are dependent/independent*.
By looking at R, we can see by inspection that the *pivot columns* form
a maximal set of independent vectors, and hence are a basis for C(R).
Hence, the *pivot columns of A* (i.e. the columns of A corresponding to
the columns of R or U where the pivots appear) are a basis for C(A).

It follows that the dimension of C(A) is exactly rank(A).

### Four important cases for Ax=b

Went through four important cases for an m×n matrix A of rank r.  (Note that we must have r ≤ m and n: you can't have more pivots than there are rows or columns.)

1. If r=n, then A has **full column rank**.  We must have m ≥ n (it is a "tall" matrix), and N(A)={0} (there are no free columns).  Hence, any solution to Ax=b (if it exists at all) must be *unique*.  (If m > n, the problem is "overdetermined": more equations than unknowns.)

2. If r=m, then A has **full row rank**.  We must have n ≥ m (it is a "wide" matrix), and C(A)=ℝᵐ.  Ax=b is *always solvable* (but the solution will not be unique unless m=n).  (If m < n the problem is "underdetermined": more unknowns than equations.)

3. If r=m=n, then A is a square **invertible** matrix.  Ax=b is always solvable and the solution x=A⁻¹b is unique.

4. If r < m and r < n, then A is **rank deficient**.  Solutions to Ax=b may not exist and will not be unique if they do exist.

Cases (1)-(3) are called **full rank**: the rank is as big as possible given the shape of A.  In practice, most matrices that one encounters are full rank (this is essentially always true for *random* matrices).  If the matrix is rank deficient, it usually arises from some special structure of the problem (i.e. you usually want to look at where A came from to help you figure out why it is rank deficient, rather than computing the rank etcetera by mindless calculation).   (A separate problem is that of matrices that are *nearly* rank deficient because the pivots are very small, but the right tools to analyze this case won't come up until near the end of the course.)

**Further reading:** Textbook sections 3.3–3.4, [lecture 9](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-9-independence-basis-and-dimension/).

## Lecture 10 (Sep 30)

* handwritten notes and lecture video (see links above).
* [pset 3 solutions](psets/pset3sol.ipynb)
* [pset 4](psets/pset4.ipynb): a short pset due Wed Oct 5

### Dot products, transposes, & orthogonality

Reviewed the dot product or **inner product** of two real column vectors, x⋅y, defined as ∑ᵢxᵢyᵢ.  In linear-algebra terms, we write this as x⋅y=xᵀy in terms of the *transpose* of the vector x: if x is a column vector, xᵀ is a row vector (sometimes more technically called a "dual" vector or "covector").  The *length* (or **norm**) of a vector is is the square root of the dot product with itself: ‖x‖=√xᵀx.

The [transpose](https://en.wikipedia.org/wiki/Transpose) Aᵀ of a linear operator A is defined  so that xᵀAy = x⋅(Ay) = (Aᵀx)⋅y = (Aᵀx)ᵀy: transposes move linear operators from one side to the other in an inner product.  In consequence, we find for matrices that Aᵀ is constructed by **swapping rows with columns** in A.   Key properties:

* (AB)ᵀ=BᵀAᵀ
* αᵀ = α for scalars.  Hence xᵀy = yᵀx (i.e. x⋅y = y⋅x)
* (A⁻¹)ᵀ = (Aᵀ)⁻¹

[Orthogonal](https://en.wikipedia.org/wiki/Orthogonality) vectors are those for which xᵀy = 0.   Defined the [orthogonal complement](https://en.wikipedia.org/wiki/Orthogonal_complement) S<sup>⟂</sup> of a subspace S ⊆ V as
{x ∈ V such that xᵀy=0 for all y ∈ S}.  Combining a basis for S and S<sup>⟂</sup> gives a basis for the whole vector space V, so the dimensions of S and S<sup>⟂</sup> sum to the dimension of V.

Taking the orthogonal complements of C(A) and N(A) leads us to the **four fundamental subspaces** for an m×n matrix A of rank r:

* column space C(A) ⊆ ℝᵐ, dimension r
* C(A)<sup>⟂</sup> = left nullspace N(Aᵀ) ⊆ ℝᵐ, dimension m-r
* nullspace N(A) ⊆ ℝⁿ, dimension n-r
* N(A)<sup>⟂</sup> = row space C(Aᵀ) ⊆ ℝⁿ, dimension r

(The consequence of this is an amazing fact: A and Aᵀ have the **same rank** r, since C(A) and C(Aᵀ) must have the same dimension r.   Thus, if you do Gaussian elimination on A and Gaussian elimination on Aᵀ, you will get the **same number of pivots** in both cases even though the elimination processes are quite different.)

**Further reading:** Textbook sections 3.5, 4.1; video
[lecture 10](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-10-the-four-fundamental-subspaces/), video [lecture 14](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-14-orthogonal-vectors-and-subspaces/).  Julia [notebook on transposes and orthogonality](https://github.com/mitmath/1806/blob/master/notes/Transposes.ipynb).

## Lecture 11 (Oct 3)

* handwritten notes and lecture video (see links above).
* [slides](https://docs.google.com/presentation/d/1SXAmVB07xdLRa8eBQFF5wI0RDpjC1u1-zHd1oPEtkXM/edit?usp=sharing)

Reviewed and broadened differential calculus (18.01 and 18.02) from the perspective of 18.06, where we view a derivative f′(x) as a **linear operator** acting on a small change in the input (dx) to give you the change in the output (df) to *first order* in dx ("linearized").   This viewpoint makes it easy to generalize derivatives, to scalar-valued functions of vectors where f′(x) is the transposed gradient (∇f)ᵀ, to vector-valued functions of vectors where f′(x) is the [Jacobian matrix](https://en.wikipedia.org/wiki/Jacobian_matrix_and_determinant), and even to matrix-valued functions of matrices like f(x)=A⁻¹ where f′(x) is the linear operator f′(x)[dA]=–A⁻¹dAA⁻¹.

Derivatives viewed as linear approximations have many important applications in science, machine learning, statistics, and engineering. For example, went over the **multidimensional Newton** algorithm for finding roots f(x)=0 of systems of nonlinear equations. At each step, you just solve a *linear* system of equations with the Jacobian matrix of f(x), and it converges incredibly rapidly.   (See notebook for

**Further reading**: This material was presented in much greater depth in our [18.S096: Matrix Calculus](https://github.com/mitmath/matrixcalc) course in IAP 2022 and IAP 2023.    The viewpoint of derivatives as linear operators (also called [Fréchet derivatives](https://en.wikipedia.org/wiki/Fr%C3%A9chet_derivative)) was covered in lectures 1 and 2, Newton's method was covered in lecture 4, and automatic differentiation was covered in lecture 5 — see the posted lecture materials and the further-reading links therein.   This [notebook](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Newton-Thomson-example.ipynb) has a Newton's method example demo where we solve a 2d version of the famous [Thomson problem](https://en.wikipedia.org/wiki/Thomson_problem) to find the equilibrium position of N repulsive "point charges" constrained to lie on a circle; more generally, a sphere or hypersphere.

## Lecture 12 (Oct 5)

* handwritten notes and lecture video (see links above).
* [pset 4 solutions](psets/pset4sol.ipynb)
* [pset 5](psets/pset5.ipynb), due Friday Oct 14

*Continued from lecture 11*: Analyzed derivatives of matrix-valued functions of matrices, like f(x)=A⁻¹ where we showed that f′(x) is the linear operator f′(x)[dA]=–A⁻¹dAA⁻¹.  Using this, if we have a matrix A(p) as a function of a parameter p, showed that we can compute d(A⁻¹)/dp = –A⁻¹(dA/dp)A⁻¹ easily.  This has enormous applications, for example in engineering optimization where you often want to differentiate the solution to a physical problem (often expressed as Ax=b) with respect to parameters of the problem (in A and/or b), in order to optimize the physics (e.g. to maximize the strength of a structure with a given amount of material): see slides from lecture 11.

### Orthonormal bases

Talked about the viewpoint that solving Ax=b when A has full column rank (i.e. independent columns) is equivalent to a change of basis, or writing b in a "new coordinate system".

However, viewing the columns of A as a basis or "coordinate system", it becomes clear that some bases are nicer than others.  (Especially if the basis vectors are *nearly linearly independent* (e.g. nearly parallel), or equivalently if *A is nearly singular*, then the new coordinate system can be difficult and confusing to use.)

A *much nicer* "coordinate system" is an [orthonormal basis](https://en.wikipedia.org/wiki/Orthonormal_basis): vectors q₁,q₂,…,qₙ that are orthogonal to one another and have length 1.   One way of looking at this: **to change "coordinates" to an orthonormal basis just involves dot products.**
  - If you have a non-orthonormal basis a₁,a₂,…, then to write an arbitrary vector b in this basis, i.e. b = a₁x₁ + a₂x₂ + ⋯ with coefficients x₁,x₂,…, you need to solve a linear system Ax=b for x.  Hard!  (∼m³).
  - For an orthonormal basis q₁,q₂,… then to write b = q₁x₁ + q₂x₂ + ⋯ you can **just take dot products** xᵢ=qᵢᵀb.  For example, if you take the dot product q₁ᵀb, then you get x₁ (the coefficient of q₁), because all the other terms have dot product *zero*.

Equivalently, we can put these q₁,q₂,…,qₙ into a matrix Q:

* Saying that the columns of Q are orthonormal vectors is *equivalent* to saying QᵀQ = I.
* If Qx=b is solvable, then the solution simply is x=Qᵀb, which is *equivalent* to taking the dot products of b with each qₖ vector to get xₖ as above.

We will have much more to say about such Q matrices in the coming lectures.

**Further reading:** 3blue1brown has a [nice video on changes of basis](https://www.youtube.com/watch?v=P2LTAUO1TdA).  Textbook sections 3.5, 4.1; video
[lecture 10](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-10-the-four-fundamental-subspaces/), video [lecture 14](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-14-orthogonal-vectors-and-subspaces/).

## Exam 1 (Friday Oct 7 at 11am in 26-100)

Exam 1 will cover the material through **lecture 10** and **pset 4**, including: linear operators, matrix–matrix and matrix–vector operations and interpretations thereof, writing/working with equations in matrix form, solving systems of equations with one or more right-hand sides, Gaussian elimination, back/forward-substitution and triangular matrices, LU factorization and PA=LU, permutation matrices, matrix inverses and Gauss–Jordan, singular matrices, computational costs (which operations are ~ m² or ~ m³ etc and arranging calculations efficiently), rank of a matrix (= number of pivots), vector space & subspaces, null space & special solutions, pivot/free columns column spaces, bases and dimensions of vector spaces, checking whether Ax=b is solvabe, complete solutions to Ax=b (including non-square matrices), transposes and dot products, orthogonality and orthogonal complements, the four fundamental subspaces.

The exam is **closed book/notes**. (No calculators or computers either.)

* [Exam 1](exams/exam1.pdf) and [solutions](exams/exam1sol.pdf)

* (Optional) **review session**: Thursday 5/6 4–5pm via Zoom: see [recording](https://mit.zoom.us/rec/share/RVnjARqopGxQtnhnCqP57okdWmccGq2MQac8FSuZVkQnmB_WVUH5MQx6GAvP1Z7R.g-ofGE6IRBUuAD2L?startTime=1665086667000), [handwritten notes](https://www.dropbox.com/s/xnowl6zoe1js1t8/18.06%20Fall%2022%20Exam%20Reviews.pdf?dl=0), and practice problems: [spring 2022 exam 1](https://github.com/mitmath/1806/blob/spring22/exams/exam1.pdf) problems 1 and 3 ([solutions](https://github.com/mitmath/1806/blob/spring22/exams/exam1sol.pdf)), fall 2014 exam 1 (below) problem 4, spring 2008 exam 1 (below) problem 1, [spring 2022 final exam](https://github.com/mitmath/1806/blob/spring22/exams/final.pdf) problems 1 and 5 ([solutions](https://github.com/mitmath/1806/blob/spring22/exams/finalsol.pdf)).

Some practice problems: [spring 2017 exam 1](http://web.mit.edu/18.06/www/Spring17/exam1.pdf) problems 1–4 ([solutions](http://web.mit.edu/18.06/www/Spring17/exam1-sol.pdf)); [fall 2017 exam 1](https://github.com/stevengj/1806/blob/fall17/exams/exam1.pdf) problems 1-4 ([solutions](https://github.com/stevengj/1806/blob/fall17/exams/exam1-sol.pdf)); [fall 2017 exam 2](https://github.com/stevengj/1806/blob/fall17/exams/exam2.pdf) problem 1a,b ([solutions](https://github.com/stevengj/1806/blob/fall17/exams/exam2-sol.pdf));
[fall 2014 exam 1](http://web.mit.edu/18.06/www/Fall14/midterm1_F14.pdf) problems 1, 2, 3, 4c/d/e  ([solutions](http://web.mit.edu/18.06/www/Fall14/Midterm1solF14.pdf));
[fall 2012 exam 1](http://web.mit.edu/18.06/www/Fall12/Exam%201/quiz1-1806-f12.pdf) problems 1–4 ([solutions](http://web.mit.edu/18.06/www/Fall12/Exam%201/quiz1-1806-f12-solution.pdf));
[spring 2008 exam 1](http://web.mit.edu/18.06/www/Spring08/quiz1-1806-S08.pdf) problems 1–4 ([solutions](http://web.mit.edu/18.06/www/Spring08/quiz1-1806-S08-soln.pdf));  [fall 2011 exam 1](http://web.mit.edu/18.06/www/Fall11/q1_f11.pdf) problem 1–3 ([solutions](http://web.mit.edu/18.06/www/Fall11/q1_f11_solution.pdf));
[spring 2012 exam 1](http://web.mit.edu/18.06/www/Spring12/q1_sp12.pdf) problems 1–4 ([solutions](http://web.mit.edu/18.06/www/Spring12/q1_sp12_sol.pdf));
[fall 2013 exam 1](http://web.mit.edu/18.06/www/Fall13/exam1_f13.pdf) problems 1, 2, 3, 5 ([solutions](http://web.mit.edu/18.06/www/Fall13/exam1_f13_sol.pdf));
[fall 2009 exam 1](http://web.mit.edu/18.06/www/Fall09/exam1.pdf) problems 1, 2, 3, 4 ([solutions](http://web.mit.edu/18.06/www/Fall09/exam1soln.pdf));
[spring 2008 exam 1](http://web.mit.edu/18.06/www/Spring08/quiz1-1806-S08.pdf) problems 1, 3, 4
([solutions](http://web.mit.edu/18.06/www/Spring08/quiz1-1806-S08-soln.pdf))

## Lecture 13 (Oct 12)

* handwritten notes and lecture video (see links above).

Started talking about **orthogonal projection**: for any subspace S ⊆ V, any vector b ∈ V can be written as a sum of two vectors, one in S and one in S<sup>⟂</sup>.   The former is the orthogonal projection Pb of b onto S, where P is the *projection matrix*, and the latter is b–Pb=(I–P)b (the orthogonal projection of b onto S<sup>⟂</sup>).  Covered:

* Projection matrix P = aaᵀ/aᵀa onto 1d subspaces with a basis vector a.  If a=q (normalized), then P = qqᵀ
* Projection matrix P = A(AᵀA)⁻¹Aᵀ onto n-dimensional subspaces C(A), where A is m×n with full column rank (rank n), i.e. its columns are a basis.
* Projection onto C(Q), i.e. a subspace with an orthonormal basis is simply QQᵀ.

**Further reading:** Textbook 4.2; video [lecture 15](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-15-projections-onto-subspaces/).

## Lecture 14 (Oct 14)

* handwritten notes and lecture video (see links above).
* [pset 5 solutions](psets/pset5sol.ipynb)
* [pset 6](psets/pset6.ipynb) due Oct 21

More on projections:

* Key properties P²=P, P=Pᵀ, C(P)=C(A), N(P)=C(A)<sup>⟂</sup>=N(Aᵀ).
* P = I for full-row-rank A, for which C(A) is all of ℝᵐ.
* Why AᵀA is invertible for full-column-rank A, and why the normal equations AᵀAx̂=Aᵀb are solvable for *any* A: rank(AᵀA) = rank(A), N(AᵀA) = N(A), and C(Aᵀ) = C(AᵀA).
* Projection I-P onto the orthogonal complement of C(A), i.e onto N(Aᵀ).
* Equivalence between orthogonal projection and least-squares: minimizing ‖b-Ax‖ is equivalent to minimizing ‖b-y‖ over y∈C(A), and the solution is p=Ax̂=Pb, where AᵀAx̂=Aᵀb.

Introduced the topic of least-square approximation: the projection p=Ax̂ of b onto C(A) is the *closest* vector to b in C(A), and hence is the solution that *minimizes* ‖b-Ax‖ over all possible x.  The vector x̂ is an **approximate solution** to Ax=b that *minimizes* the error ‖b-Ax‖ when no exact solution exists.

**Further reading:** Textbook section 4.3 and video [lecture 16](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-16-projection-matrices-and-least-squares/).

## Lecture 15 (Oct 17)

* handwritten notes and lecture video (see links above).
* [Least-square fitting examples](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Least-Square%20Fitting.ipynb)

Introduced the topic of least-square fitting of data to curves.  As long as the fitting function is linear in the unknown coefficients x, showed that minimizing the sum of the squares of the errors corresponds to minimizing the norm of the residual ‖b-Ax‖.  Went through several examples (see Julia notebook).

Derived the fact that minimizing ‖b-Ax‖ or ‖b-Ax‖² (least squares) corresponds to orthogonal projection (hence AᵀAx̂=Aᵀb) using either algebra (showing ‖b-Ax‖²≥‖b-Ax̂‖² for any x) or calculus (setting ∇‖b-Ax‖²=0).

**Further reading:** Textbook section 4.3 and video [lecture 16](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-16-projection-matrices-and-least-squares/).   There are many, many books and other materials on [linear least-squares fitting](https://en.wikipedia.org/wiki/Linear_least_squares), from many different perspectives (e.g. numerical linear algebra, statistics, machine learning…) The brief discussion at the end of the notebook on [Runge phenomena](https://en.wikipedia.org/wiki/Runge%27s_phenomenon) and equally spaced vs. [Chebyshev points](https://en.wikipedia.org/wiki/Chebyshev_nodes) in polynomial fitting was an entry point into [approximation theory](https://en.wikipedia.org/wiki/Approximation_theory); if you are interested, the [book by Trefethen](https://people.maths.ox.ac.uk/trefethen/ATAP/) and accompanying [video lectures](https://people.maths.ox.ac.uk/trefethen/atapvideos.html) are a great place to start.

## Lecture 16 (Oct 19)

* handwritten notes and lecture video (see links above).

**Gram-Schmidt orthogonalization**: given a non-orthonormal basis a₁,a₂,…, we can *convert* it to an orthonormal basis that **spans the same space**.  All we do is to **take each vector and subtract the projections onto the previous vectors** to make them orthogonal, and divide by their lengths to normalize them.

To go directly from a₁,a₂,… to q₁,q₂,…:
1. q₁ = a₁ / ‖a₁‖
2. q₂ = (a₂ - q₁q₁ᵀa₂) / ‖⋯‖: subtract the projection q₁q₁ᵀa₂ of a₂ onto q₁ to make them orthogonal.
3. q₃ = (a₃ - q₁q₁ᵀa₃ - q₂q₂ᵀa₃) / ‖⋯‖: subtract the projections of a₃ onto q₁ and q₂
4. etcetera

(The process described above and in the book is known as "classical" Gram-Schmidt.  In practice, the computer actually uses more sophisticated algorithms.  But classical Gram-Schmidt is still a good way to *think* about the process.

Writing Gram–Schmidt in matrix form: it turns out that what we are "really" doing is factoring A=QR, where Q is a matrix with orthonormal columns spanning C(A) and R is an invertible upper-triangular matrix.

Using QR to solve the least-squares problem: given A=QR, the normal equations AᵀAx̂=Aᵀb turn into the triangular system of equations Rx̂=Qᵀb.

Talked about the computational complexity/scaling: for an m×n matrix A, solving least-squares problem by *either* the normal equations or by QR scale roughly as ~ mn² (dominated by the the cost of forming AᵀA for the normal equations in the former case, or by the cost of Gram–Schmidt or other algorithms for QR factorization in the latter case).  (In practice, the AᵀA normal-equations method is easier by hand, and is actually slightly faster on a computer too, but computers generally prefer the QR method for reasons discussed below.)

Some practical tips to keep in mind if you ever need to do least-squares or orthogonal basis for real-world problems (not 18.06 exams!) involving data with finite precision:

* Rarely (on a computer) explicitly form AᵀA or solve the normal equations: it turns out that this greatly exacerbates the sensitivity to numerical errors (in 18.335, you would learn that it squares the [condition number](https://en.wikipedia.org/wiki/Condition_number))  Instead, use the A=QR factorization and solve Rx̂=Qᵀb.  Better yet, just do `A \ b` (in Julia or Matlab) or the equivalent in other languages (e.g. [`numpy.linalg.lstsq`](https://numpy.org/doc/stable/reference/generated/numpy.linalg.lstsq.html)), which will use a good algorithm.   (Even professionals can [get confused about this](https://discourse.julialang.org/t/efficient-way-of-doing-linear-regression/31232/33?u=stevengj).)

* Rarely use Gram–Schmidt for large matrices, which turns out to be notoriously sensitive to small errors if some vectors are nearly parallel.  People still compute the "same" QR factorization, just using different methods! There is an improved version called "modified Gram–Schmidt" described in the book (or you can also do Gram–Schmidt twice), but in practice computers mostly use a completely different algorithm called "Householder reflections."  You should just use the built-in `qr(A)` function in Julia (or similarly other languages), which will do the right thing most of the time.

This is not unusual: there is often a difference between the way we conceptually *think* about linear algebra and the more sophisticated tricks that are required to make it *work well* on *large matrices* of real data.

**Further reading:** Strang, section 4.4, and video [lecture 17](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-17-orthogonal-matrices-and-gram-schmidt/).   Many advanced linear-algebra texts talk about the practical aspects of roundoff errors in QR and least-squares, e.g. *Numerical Linear Algebra* by Trefethen and Bau (the 18.335 textbook), but this is beyond the scope of 18.06.   A nice historical review can be found in the article [Gram-Schmidt orthogonalization: 100 years and more](https://doi.org/10.1002/nla.1839).

## Lecture 17 (Oct 21)

* lecture video (see link above).
* [SVD introduction](https://nbviewer.org/github/stevengj/1806/blob/master/notes/SVD-intro.ipynb)
* [SVD low-rank approximation demos](https://computationalthinking.mit.edu/Spring21/structure/) from the spring 2021 *Computational Thinking* class
* [pset 6 solutions](https://nbviewer.org/github/mitmath/1806/blob/master/psets/pset6sol.ipynb)
* [pset 7](psets/pset7.ipynb): due Friday Oct 28.

Guest lecture by Prof. Alan Edelman.

Introduction to the [singular value decomposition](https://en.wikipedia.org/wiki/Singular_value_decomposition) (**SVD**), the fact that it gives the "right" orthonormal bases for the row and column spaces of a matrix, and its application to [low rank approximation](https://en.wikipedia.org/wiki/Low-rank_approximation).

(Traditionally, the SVD is often left to near the end of an introductory linear algebra course.  One reason for this is that it takes a lot of linear-algebra machinery to *derive* the SVD, much less to calculate yourself.  In fact, it is almost completely impractical to compute by hand except for the nearly useless 2×2 case.   So at this point, **don't worry** about *why* the SVD exists, and trust Julia to calculate it for you.  The main goal for now is to understand what the SVD tells you once you have it.)

**Further reading:** Beware that there are several slightly different forms of the SVD; what I've used in the notebook is called the "compact" SVD on Wikipedia and is denoted by an "r" subscript in Strang section 7.2; you can expand this to other forms by augmenting U and V with bases for the left and right nullspaces, respectively, and correspondingly adding rows and columns of zeros to Σ.   Strang, sections 7.1–7.2, and video [lecture 29](https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-29-singular-value-decomposition/).  Note, however, that the connection of SVD to eigenvalues/eigenvectors of AᵀA is something that we won't cover until later in 18.06.   A cool example that uses the SVD to pull out a few key vectors from a big pile of data is the [eigenwalker demo](https://www.biomotionlab.ca/html5-bml-walker/).  The name for this technique in statistics is [principal component analysis (PCA)](https://en.wikipedia.org/wiki/Principal_component_analysis).  Strang section 4.2 on orthogonal projection.

## Lecture 18 (Oct 24)

* [Orthogonal polynomials](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Orthogonal-Polynomials.ipynb)
* [Fourier sine series](https://nbviewer.org/github/mitmath/1806/blob/master/notes/Sine-series.ipynb)

Another wonderful and far-reaching application of these ideas is to realize that the same concepts of orthogonal bases and Gram–Schmidt can be applied to *any* vector space once we define a dot product (giving a so-called [Hilbert space](https://en.wikipedia.org/wiki/Hilbert_space), though we won't use that level of abstraction much in 18.06).  In particular, it turns out to be especially powerful to think about **orthogonal/orthonormal bases of functions**.  Introduced a dot product f⋅g=∫fg for functions defined on x∈[-1,1], and we'll use it to make an orthogonal basis of polynomials, the [Legendre polynomials](https://en.wikipedia.org/wiki/Legendre_polynomials).

Showed another important example of orthogonal functions: Fourier series, and in particular the [Fourier sine series](https://en.wikipedia.org/wiki/Fourier_sine_and_cosine_series).

**Further reading (polynomials):** For example, see these [TAMU notes on orthogonal polynomials](http://www.math.tamu.edu/~yvorobet/MATH304-503/Lect4-04web.pdf) and [these 18.06 notes on orthogonal polynomials](http://web.mit.edu/18.06/www/Spring09/legendre.pdf), or many other sources, e.g. [this book by Szego (1975)](https://people.math.osu.edu/nevai.1/SZEGO/szego=szego1975=ops=OCR.pdf).

**Further reading (Fourier):** Strang, section 10.5 (Fourier series) and these [18.06 sine-series notes](http://web.mit.edu/18.06/www/Spring09/sines.pdf).  There is a [3blue1brown video](https://youtu.be/r6sGWTCMz2k) on Fourier series, along with many, many other resources and videos you can find online… Fourier series and their generalizations are vastly important for lots of applications as well as being a deep and beautiful mathematical subject for their own sake!
