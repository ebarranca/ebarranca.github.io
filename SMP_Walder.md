## A CHARACTERIZATION OF VARIOUS SEIDEL EQUIVALENCE CLASSES OF GRAPHS 

## Isabel Walder 

Project advised by Dr. Emily Barranca 

ST. MARY’S PROJECT 

ST. MARY’S COLLEGE OF MARYLAND MAY 2026 

## **Acknowledgments** 

I would like to thank Dr. Emily Barranca for all of the time, patience, and support that went into advising this project. I appreciate all of the mathematical guidance you have provided, as well as all of the additional mentoring that you have put into developing my ability to communicate math comfortably and all of the effort that you have put into making math research fun. Thank you for a constant supply of eye-roll worthy jokes and themed office supplies. 

I would like to express my gratitude to the math department for their emphasis on community which has made the math lounge a safe place to be myself and for funding to present my work at multiple conferences. I would like to acknowledge St. Mary’s College of Maryland for providing funding for the summer term where this work originated. 

I would like to thank Dr. Sara Chari for her support, encouragement, patience, and help with mathematical writing and presentations. Thank you to Haley Galloway for help researching relevant past work on the Seidel matrix. 

I would also like to thank Noah Hanscom for being a great research accountability buddy and supplier of Swedish Fish. Thank you to Amelia Fleming for being a friend, sharing good music, and showing up for every step of my research journey and in particular, every presentation, unasked. 

2 

## **Contents** 

|**Contents**|**Contents**|**Contents**||||
|---|---|---|---|---|---|
|**Acknowledgments**|||||**2**|
|**Introduction**|||||**4**|
|**1**|**Graph preliminaries**||||**4**|
||1.1|Graph complements|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|5|
||1.2|Subgraphs . . . . . .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|5|
||1.3|Graph isomorphisms|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|6|
|**2**|**Linear algebra preliminaries**||||**7**|
||2.1|The determinant . .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|7|
||2.2|Eigenvalues and the characteristic polynomial . . . . . . . . . . . . . . . . . . . . . . . . . . .|||8|
||2.3|Similar matrices<br>. .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|9|
|**3**|**Abstract algebra preliminaries**||||**10**|
||3.1|Permutations . . . .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|10|
||3.2|Permutation defnition of the determinant . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|||10|
||3.3|Equivalence relations|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|11|
|**4**|**Spectral graph theory**||||**12**|
||4.1|The adjacency matrix|. .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|12|
|||4.1.1<br>Cospectral graphs||. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|12|
|||4.1.2<br>Graphs determined||by their spectrum<br>. . . . . . . . . . . . . . . . . . . . . . . . . . .|13|
||4.2|The Seidel matrix . .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|14|
|**5**|**Seidel switching**||||**14**|
||5.1|Matrix switching . .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|14|
||5.2|Graph switching<br>. .|. . .|. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|16|
||5.3|Godsil-McKay switching .||. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|17|
||5.4|Seidel equivalence classes||. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|24|
|**6**|**New **|**results on the Seidel matrix**|||**25**|
|**7**|**Conclusion**||||**39**|



3 

**Abstract** Let _G_ = ( _V, E_ ) be a graph with adjacency matrix _A_ ( _G_ ) and Seidel matrix _S_ ( _G_ ) = _J −_ 2 _A_ ( _G_ ) _− I_ . Influenced by results for adjacency matrices and the adjacency spectrum, we examine the characteristic polynomial _ϕ_ ( _S_ ( _G_ )) of the Seidel matrix. We provide relevant mathematical background then proceed to introduce original results. We prove a general form for the coefficients of some terms of _ϕ_ ( _S_ ( _G_ )) for all graphs on _n_ vertices. We also prove a general form for the Seidel characteristic polynomial for the complete bipartite switching class and its complement. 

## **Introduction** 

In this project we approach studying graph theory through a linear algebraic lens. Graph theory is a subfield of combinatorics in which we can study the relationships between different structures. The graphical representation of data structures allows for their detailed mathematical analysis which is useful in many applications of computer science, including the construction of neural networks and the study of transit systems. One particularly useful way to represent the structural arrangement of a graph is by encoding this data as a matrix. Once in matrix form, the field of linear algebra can be applied to better study specific graph properties. 

In the first five sections of this paper we give relevant background information and results on topics such as graph theory, combinatorics, linear algebra, and abstract algebra. Additionally, we give detailed proofs of some well established results in linear algebra and spectral graph theory. 

In Section 6 we discuss original research regarding the Seidel characteristic polynomial and spectrum of graphs. We then examine the organization of graphs through their relationship to the Seidel matrix. We conclude this paper with proposed conjectures and directions for future research. 

## **1 Graph preliminaries** 

A _graph_ is a tuple _G_ = ( _V_ ( _G_ ) _, E_ ( _G_ )) where _V_ ( _G_ ) denotes a set of vertices of _G_ and _E_ ( _G_ ) denotes a set of 2-element subsets of _V_ ( _G_ ), indicating edges of _G_ . For _v_ 1 _, v_ 2 _∈ V_ ( _G_ ), _v_ 1 and _v_ 2 are _adjacent_ if _{v_ 1 _, v_ 2 _} ∈ E_ ( _G_ ). A _simple_ graph is a graph containing no loops or multiple edges between the same pair of vertices; all graphs referred to here will be simple, undirected graphs. Thus any edge _{vi, vj} ∈ E_ ( _G_ ) can be equivalently expressed as _{vj, vi}_ [4]. We will use _n_ to denote the number of vertices in a graph _G_ . The _degree_ of a vertex _v_ is the number of edges incident to _v_ . 

Consider the graph _G_ in Figure 1 with _n_ = 4 vertices where vertices of the same color have the same degree. We see that vertex _d_ has degree 1, _a_ has degree 3, and _b_ and _c_ both have degree 2. When all _n_ vertices in _G_ have the same degree _k_ , we say that G is a _k-regular graph_ . 

Consider graphs _G_ and _H_ in Figure 1. Since _G_ has vertices of different degrees it is not a regular graph. _H_ has all vertices with degree 2 so _H_ is 2-regular. 

**==> picture [238 x 88] intentionally omitted <==**

**----- Start of picture text -----**<br>
a c a c<br>b d b d<br>G H<br>**----- End of picture text -----**<br>


Figure 1: non-regular graph ( _G_ ) and 2-regular graph ( _H_ ) 

Next we will define terms relating to graph traversal and see a small example. A _walk_ on a graph is an 

4 

alternating list of vertices and edges, a _trail_ is a walk with no repeated edges, and a _path_ is a trail with no repeated vertices. The _distance_ , dist( _vi, vj_ ) of a pair of vertices is the length of the shortest path between them. For the graph _G_ in Figure 1 the distance between vertices _b_ and _d_ is 2. The _diameter_ is the maximum distance between any pair of vertices of _G_ . A graph is _connected_ if there exists a walk between any two vertices. Otherwise, we say that a graph is _disconnected_ . 

The remainder of this section will provide specifications for well known types of graphs and their properties. See Figure 2 for examples of each type of graph. A graph with an empty edge set is called an _empty graph En_ . In a _complete graph Kn_ , every pair of vertices has an edge between them. A _cycle graph Cn_ is a connected graph such that all vertices have degree 2. A _path graph Pn_ contains _n−_ 2 vertices of degree 2 and two vertices of degree 1. We can also define a path by its construction: it is a graph formed by removing one edge from _Cn_ . 

A graph whose vertex set can be partitioned into subsets _A_ and _B_ with respective orders _a_ and _b_ such that no two vertices of the same set are adjacent is known as a _bipartite graph_ . In a _complete bipartite graph Ka,b_ , every vertex in _A_ is adjacent to every vertex in _B_ . A subclass of bipartite graphs are trees. A _tree_ is a connected graph containing no cycles. Any vertex of degree 1 in a tree is called a _leaf_ . A graph made up of a disjoint union of trees is called a _forest_ . A path graph is an example of a tree and has two leaves. 

**==> picture [366 x 166] intentionally omitted <==**

**----- Start of picture text -----**<br>
empty graph, En complete graph, Kn cycle, Cn<br>E 4 K 4 C 4<br>path, Pn complete bipartite graph, Ka,b<br>P 4 K 2 , 3<br>**----- End of picture text -----**<br>


Figure 2: common graph examples 

## **1.1 Graph complements** 

One structural process we can examine is taking the complement of a graph. Consider a graph _G_ with _n_ vertices and edge set _E_ ( _G_ ). The _graph complement_ of _G_ , denoted _G_[¯] is the graph with edge set _E_ ( _G_[¯] ). _G_[¯] is defined such that _V_ ( _G_ ) = _V_ ( _G_[¯] ) and _E_ ( _G_ ) _∪ E_ ( _G_[¯] ) = _E_ ( _Kn_ ) and _E_ ( _G_ ) _∩ E_ ( _G_[¯] ) = _∅_ where _E_ ( _Kn_ ) gives all possible edges for a graph on _n_ vertices. We can observe that superimposing _G_ and _G_[¯] gives the complete graph _Kn_ . For a trivial example, consider the superimposition of graph complements _En_ and _Kn_ . Next consider the superimposition of graph complements _K_ 2 + _K_ 2 and _C_ 4 as shown in Figure 3. 

There exist methods for finding the number of edges present in _Kn_ other than superimposing graph complements. We can observe from Figure 3 that _|E_ ( _G_ ) _|_ + _|E_ ( _G_[¯] ) _|_ = _|E_ ( _Kn_ ) _|_ = � _n_ 2�, since the number of edges in a complete graph is equal to the counting number � _n_ 2� which is called the _binomial coefficient_ � _nk_ � and is given by _k_ !( _nn−_ ! _k_ )![for][integers][0] _[ ≤][k][≤][n]_[.] 

## **1.2 Subgraphs** 

Another tool for the examination of graphs is to find and study their subgraphs. Consider graphs _G_ and _H_ . If _V_ ( _H_ ) _⊆ V_ ( _G_ ) and _E_ ( _H_ ) _⊆ E_ ( _G_ ) then we call _H_ a _subgraph_ of _G_ . A subgraph _H_ of graph _G_ is an _induced_ 

5 

Figure 3: The superimposition of _K_ 2 + _K_ 2 and _C_ 4 is _K_ 4 

_subgraph_ if _E_ ( _H_ ) contains all of _E_ ( _G_ ) which have both endpoints in _V_ ( _H_ ). A _component_ of a graph _G_ is a maximal connected subgraph of _G_ . 

An example of a graph with multiple components is given in Figure 4. We use a (+) to denote multiple components in a graph. Let _G_ = _K_ 2 + _K_ 1 _,_ 3. Then _K_ 1 _,_ 3 is a component of _G_ . The subgraph _P_ 3 is not a component of _G_ because it is not a maximal connected subgraph. 

**==> picture [104 x 62] intentionally omitted <==**

Figure 4: _G_ made up of components _K_ 2 with vertex set _{a, b}_ and _K_ 1 _,_ 3 with vertex set _{c, d, e, f }_ 

. 

## **1.3 Graph isomorphisms** 

An important skill while studying graphs is the ability to detect distinct graphs from those which are structurally identical in order to better classify them. We say that given two graphs _G_ and _G[′]_ , if there exists a mapping of _G[′]_ that preserves the adjacencies of _G_ then we say that _G[′]_ is an _isomorphism_ of _G_ , or that the graphs _G_ and _G[′]_ are _isomorphic_ . We are interested in examining uniquely structured graphs; therefore, it is important that we are able to distinguish isomorphisms from uniquely structured graphs in order to exclude them from our data set. 

Consider the graphs in Figure 5. When we rearrange vertices _a, b, c, d_ of both graphs so that they are in the same positions, we see that we have an identical graph structure. 

**==> picture [232 x 62] intentionally omitted <==**

Figure 5: _C_ 4 isomorphisms 

6 

## **2 Linear algebra preliminaries** 

This project examines topics in the intersection of graph theory and linear algebra. In this section we provide definitions for relevant matrix types and their properties adapted from _Linear Algebra and applications: An inquiry-based approach_ by Alayont and Schlicker [1] and _Matrix analysis and applied linear algebra_ by Meyer [7]. We then perform calculations to find information which characterizes a matrix which will have implications for graph structure in future sections. We conclude this section with results on matrix symmetry and invertibility. 

Consider an _n × n_ matrix _A_ = [ _a_ ] _ij_ where _i_ and _j_ denote row and column positions, respectively. The _main diagonal_ of _A_ consists of entries [ _a_ ] _ii_ where the row and column numbers are equal ( _j_ = _i_ ). The _trace_ of a matrix is the sum of its main diagonal entries, denoted 

**==> picture [72 x 28] intentionally omitted <==**

We will use _In_ to denote the identity matrix and _Jn_ to denote the square matrix where every entry has value 1. When the dimensions are clear from context, we simply use _I_ or _J_ . 

A matrix _A_ is a _diagonal matrix_ if _aij_ = 0 for all _i_ = _j_ and is _upper or lower triangular_ if all entries of _A_ are zero below and above the main diagonal respectively. The _transpose_ of an _m × n_ matrix _A_ = [ _aij_ ] is the _n × m_ matrix _A[T]_ whose _i, j_ th entry is _aji_ [1]. A matrix _A_ is _symmetric_ if it is equal to its transpose, that is, _A_ = _A[T]_ . When an _n × n_ matrix _A_ is invertible, a unique _A[−]_[1] exists such that _AA[−]_[1] = _A[−]_[1] _A_ = _I_ , and we say that _A_ is _nonsingular_ . If _A_ is not invertible, then _A_ is _singular_ . An orthogonal matrix _P_ is an _n × n_ matrix such that _P[T]_ = _P[−]_[1] and thus _P[T] P_ = _I_ . 

While we can often invert a matrix using row reduction and other common methods, another method from which we can approach the problem of inverting a matrix is to apply the formula in Lemma 2.1. This is particularly useful since computing inverses of matrices can be a lengthy process so by decomposing this operation into more manageable pieces we can simplify our computations. 

**Lemma 2.1.** _(Miller [8]) Let Q be matrix and let P be an n × n nonsingular matrix. If P and P_ + _Q are invertible and Q has rank_ 1 _then,_ 

**==> picture [200 x 24] intentionally omitted <==**

## **2.1 The determinant** 

A property that can often be used to describe important information about square matrices is the determinant. If _A_ is an _n × n_ matrix, the _determinant_ of _A_ is the scalar det( _A_ ) = _a_ 11 _C_ 11 + _a_ 12 _C_ 12 + _..._ + _a_ 1 _nC_ 1 _n_ where _Cij_ = ( _−_ 1) _[i]_[+] _[j]_ det( _Aij_ ) is the _ij_ -cofactor of _A_ , and _Aij_ is the matrix obtained by removing row _i_ and column _j_ of matrix _A_ . If _A_ is upper or lower triangular, then det( _A_ ) is the product of the main diagonal _n_ entries of _A_ , or det( _A_ ) = � _aii_ . _i_ =1 

In terms of row operations, adding a multiple of a row to another row does not change the determinant of a matrix. However, multiplying a row by a constant _c_ multiplies the determinant by _c_ , and swapping two _−_ rows multiplies the determinant by ( 1). The determinant can be used to describe specific matrix properties including invertibility. For example _A_ is invertible if and only if det( _A_ ) _̸_ = 0. 

Given _n × n_ matrices _A_ and _B_ the following properties hold: 

- (1) det( _AB_ ) = det( _A_ ) det( _B_ ) 

- (2) det( _A[k]_ ) = (det( _A_ )) _[k]_ 

7 

(3) det( _A[T]_ ) = det( _A_ ). 

We can use the structure of block matrices in order to more efficiently perform operations such as finding the determinant. The following theorem provides a formula for the computation of the determinant of a block matrix. 

**Theorem 2.2.** _[7] Consider a matrix M with blocks A, B, C, D, where A and D are square matrices then_ 

**==> picture [307 x 31] intentionally omitted <==**

_The Schur complements are the matrices D − CA[−]_[1] _B and A − BD[−]_[1] _C of A and D repectively._ 

## **2.2 Eigenvalues and the characteristic polynomial** 

We will make great use of the concept of eigenvalues which can represent various matrix properties. Therefore we will define relevant operations and follow an example to which we will apply our knowledge of the determinant. Consider a square matrix _A_ and vector _⃗v_ = _[⃗]_ 0. A scalar _λ_ which satisfies the expression _A⃗v_ = _λ⃗v_ is an _eigenvalue_ of _A_ and _⃗v_ is an _eigenvector_ of _A_ corresponding to _λ_ . Any eigenvectors corresponding to distinct eigenvalues are linearly independent. 

To calculate the eigenvalues of _A_ we first calculate det( _A − λI_ ). This expression is the _characteristic polynomial_ of _A_ , denoted _ϕ_ ( _A_ ). Then we can set the characteristic polynomial equal to 0 and solve for _λ_ . Consider the matrix 

**==> picture [74 x 37] intentionally omitted <==**

Then, 

**==> picture [168 x 148] intentionally omitted <==**

Thus, 

**==> picture [204 x 114] intentionally omitted <==**

8 

When factored, this gives eigenvalues _λ_ 1 = 2 _, λ_ 2 = _−_ 1 _, λ_ 3 = _−_ 1. Observe that _A_ 3 _×_ 3 has 3 real eigenvalues. From here we can calculate the corresponding eigenvectors by finding solutions for ( _A − λI_ ) _⃗v_ = _[⃗]_ 0. We proceed by row reducing the augmented matrix _A −_ 2 _I_ , 

**==> picture [200 x 117] intentionally omitted <==**

which gives the eigenvector _[⃗]_ 13 _×_ 1. Next we find the eigenvectors corresponding with the eigenvalue _−_ 1. We now row reduce the matrix _A_ + _I_ 

which gives the eigenvectors 

**==> picture [96 x 37] intentionally omitted <==**

We can verify the eigenpairs of ( _λ,⃗v_ ) by checking equality for _A⃗v_ = _λ⃗v_ . 

**Theorem 2.3.** _An n × n matrix A that is real and symmetric has n real eigenvalues._ 

_Proof._ Let _A_ be a real matrix. Suppose _λ_ with _⃗v_ = _[⃗]_ 0 are an eigenvalue and eigenvector of _A_ respectively with values in C. Let _⃗v[∗]_ denote the conjugate transpose of _⃗v_ . 

Then _⃗v_ 1 _×m⃗vm[∗] ×_ 1[=] _[ ⃗r]_[1] _[×]_[1][where] _[⃗r]_[is][real][for][any] _[ ⃗v]_[.][By][definition][of][eigenvalues,] _[λ⃗v]_[=] _[ A⃗v]_[.][So:] 

**==> picture [73 x 39] intentionally omitted <==**

We proceed by taking the conjugate transpose of both sides ( _λ⃗r_ ) _[∗]_ = ( _⃗v[∗] A⃗v_ ) _[∗]_ . Since _⃗r_ is real _⃗r[∗]_ = _⃗r[T]_ which is also real. Hence: 

**==> picture [163 x 74] intentionally omitted <==**

Thus _λ[∗]_ = _λ_ . Since this property holds only for real numbers, eigenvalues _λ_ of a real and symmetric matrix will be real numbers. 

## **2.3 Similar matrices** 

When we are comparing matrices we can often learn useful structural information about a matrix by determining if it is similar to another matrix. We say that _n × n_ matrices _A_ and _B_ are _similar_ if there exists a nonsingular matrix _P_ such that _B_ = _P[−]_[1] _AP_ . Properties of similar matrices include equivalent characteristic polynomials, trace, determinants, and eigenvalues. That is, we can show that two matrices have the same multiset of eigenvalues by showing that they are similar. 

9 

## **3 Abstract algebra preliminaries** 

In this section we examine permutations and equivalence relations and use these structures to solve problems from linear algebra. Definitions are adapted from _Matrix analysis and applied linear algebra_ by Meyer [7]. We conclude this section with an algebraic examination of the structural relationships between graphs. 

## **3.1 Permutations** 

We now proceed to study permutations and their various properties, some of which lend well to the study of graphs. Permutations as seen through a more combinatorial lens can be considered to be an arrangement where order matters. In terms of abstract algebra, a _permutation_ on [ _n_ ] = _{_ 1 _,_ 2 _, ..., n}_ is a bijection _σ_ : [ _n_ ] _→_ [ _n_ ]. The set of bijections from [ _n_ ] to [ _n_ ] forms the symmetric group _Sn_ . Note that there exist _n_ ! total permutations on [ _n_ ]. We can write each of these orderings of elements in a form known as cycle notation which gives a map between elements. It is known that every permutation can be written as a composition of 2-cycles. Note that in _σ_ 1, the identity permutation, all elements map to themselves so it is a composition of zero 2-cycles. See Figure 6 for details of the group _S_ 3. 

|permutation|ordering|cycle notation|composition of 2- cycles|
|---|---|---|---|
|_σ_1|_{_123_}_|(1)(2)(3)||
|_σ_2|_{_132_}_|(1)(23)|(23)|
|_σ_3|_{_213_}_|(12)(3)|(12)|
|_σ_4|_{_231_}_|(132)|(12)(13)|
|_σ_5|_{_312_}_|(123)|(13)(12)|
|_σ_6|_{_321_}_|(13)(2)|(13)|



Figure 6: _S_ 3: the permutation group on the set [3] 

Consider _σ_ 3. We read the cycle as indicating element 1 maps to element 2 which maps back to element 1, so we have a 2-cycle. As 3 maps to itself it is in a 1-cycle. Observe that 1-cycles are elements that are fixed by a permutation. 

Every permutation has an associated property known as the sign of a permutation, denoted sgn( _σ_ ) such that sgn( _σ_ ) = ( _−_ 1) _[n][−][k]_ where _k_ is the number of disjoint cycles of any length in _σ_ . Equivalently, sgn( _σ_ ) is equal to negative one raised to the number of 2-cycles. If sgn( _σ_ ) = _−_ 1 then _σ_ is an _odd permutation_ , and if sgn( _σ_ ) = 1 then _σ_ is an _even permutation_ . 

## **3.2 Permutation definition of the determinant** 

As an alternative to linear algebra techniques, we can use permutations and their properties to calculate the determinant of a matrix _A_ with dimensions _n × n_ , following the formula: 

**==> picture [200 x 24] intentionally omitted <==**

10 

||||||
|---|---|---|---|---|
|permutation|sgn(_σ_)|(_a_1_,π · · · an,π_)|product|value|
|_σ_1|1|(_a_11_a_22_a_33)|1_·_(_−λ_)(_−λ_)(_−λ_)|_−λ_3|
|_σ_2|_−_1|(_a_11_a_23_a_32)|_−_1_·_(_−λ_)(1)(1)|_λ_|
|_σ_3|_−_1|(_a_12_a_21_a_33)|_−_1_·_(1)(1)(_−λ_)|_λ_|
|_σ_4|1|(_a_12_a_23_a_31)|1_·_(1)(1)(0)|0|
|_σ_5|1|(_a_13_a_21_a_32)|1_·_(0)(1)(1)|0|
|_σ_6|_−_1|(_a_13_a_22_a_31)|_−_1_·_(0)(_−λ_)(0)|0|



Figure 7: terms of _ϕ_ ( _A_ ) 

Consider using this permutation definition of the determinant to find the characteristic polynomial of the matrix 

**==> picture [74 x 37] intentionally omitted <==**

To find _ϕ_ ( _A_ ) we find the determinant of the matrix: 

**==> picture [124 x 37] intentionally omitted <==**

To find the determinant of the 3 _×_ 3 matrix _A_ we must use _S_ 3. Let _i_ = 1 _, ...,_ 6 enumerate the permutations of _S_ 3. We proceed by finding the product of sgn( _σi_ ) and the matrix entries and then sum these products to find the value of the determinant seen in Figure 7. The sum of the rightmost column gives the determinant of _A − λI_ . That is, we have found _ϕ_ ( _A_ ) = _−λ_[3] + 2 _λ_ . 

## **3.3 Equivalence relations** 

Other algebraic structures present in our results are equivalence relations on sets of graphs. Let _Gn_ be the set of graphs on _n_ vertices. Let _G, G[′] , G[′′]_ be graphs in _Gn_ . An equivalence relation _∼_ on _Gn_ is a relation from _Gn_ to _Gn_ that satisfies, 

i. _G ∼ G_ 

ii. if _G ∼ G[′]_ then _G[′] ∼ G_ 

iii. if _G ∼ G[′]_ and _G[′] ∼ G′′_ then _G ∼ G′′_ 

An equivalence relation will partition a set into _equivalence classes_ . For an example, matrix similarlity, as defined in Section 2.3, is an equivalence relation on the set of square matrices. Graph isomorphisms, as defined in Section 1.3, also form equivalence classes. 

11 

## **4 Spectral graph theory** 

In addition to properties defined in Section 1, we also study graph properties found through matrix operations. We apply some applications of linear algebra to the study of graph structure. 

Given a graph _G_ we can construct a matrix _A_ ( _G_ ) encoding the structure of _G_ . We have seen that we can calculate the eigenvalues of a matrix. Note that when we examine a graph matrix we refer to the eigenvalues of this matrix as the eigenvalues of the graph. 

While a variety of graph matrices exist, in the following section we will focus on the adjacency matrix, which is a very commonly studied matrix. In later sections, we will use known results on this matrix as motivation to examine the less commonly studied Seidel matrix. 

## **4.1 The adjacency matrix** 

The _adjacency matrix_ of a graph _G_ with vertex set _{v_ 1 _, v_ 2 _, ..., vn}_ is the _n × n_ matrix denoted _A_ ( _G_ ) = [ _a_ ] _ij_ . The entries of the adjacency matrix are given by 

**==> picture [129 x 31] intentionally omitted <==**

All simple, undirected graphs have symmetric adjacency matrices with _tr_ ( _A_ ) = 0. 

The set containing the eigenvalues of the adjacency matrix of _G_ and their multiplicities is known as the _adjacency spectrum_ of _G_ . Since the adjacency matrix _A_ is real and symmetric, _A_ has _n_ real eigenvalues by Theorem 2.3. Consider the characteristic polynomial of _K_ 3 given by _ϕ_ ( _K_ 3) = det( _A_ ( _K_ 3) _− λI_ ). The characteristic polynomial is calculated in Section 2.2 and gives _ϕ_ ( _K_ 3) = _−λ_[3] + 3 _λ_ + 2 which we factor to find eigenvalues _λ_ 1 = 2 _, λ_ 2 = _−_ 1 _, λ_ 3 = _−_ 1. Thus the spectrum of _K_ 3 is _{_ 2[(1)] _, −_ 1[(2)] _}_ , where multiplicities are denoted by superscripts [6]. 

**==> picture [40 x 40] intentionally omitted <==**

Figure 8: the graph _K_ 3 

There are a variety of structural graph properties that we understand from the adjacency spectrum and characteristic polynomial. The number of vertices of a graph _G_ can be determined from the spectrum as it is equal to the number of eigenvalues present, which is equal to the degree of the adjacency characteristic polynomial. The number of edges in _G_ is given by the magnitude of third coefficient of the characteristic polynomial. Consider the example in Figure 8. We can count 3 edges in our graph and observe that the coefficient of the degree _n −_ 2 term in _ϕ_ ( _K_ 3) has a magnitude of 3, matching the edge number. 

## **4.1.1 Cospectral graphs** 

While certain structural properties of graphs can be determined from a graph’s spectrum, there are other properties which cannot be determined in this way. Next we will examine graphs whose structural properties provide insight into what can be discerned about a graph by spectrum alone. 

Graphs that share the same spectrum are said to be _cospectral_ . All pairs of isomorphic graphs are cospectral to one another. Here, we will refer to non-isomorphic sets of graphs which share the same spectrum as cospectral graphs. Note that all graphs cospectral to one another with respect to the adjacency matrix must contain the same number of vertices and edges. 

12 

The smallest set of adjacency cospectral graphs has 5 vertices and has spectrum _{_ 2[(1)] _,_ 0[(3)] _, −_ 2[(1)] _}_ . The two nonisomorphic graphs with this adjacency spectrum are given in Figure 9. This example illustrates that structural properties such as whether a graph is a tree or is connected cannot be implied from an examination of the spectrum alone. 

**==> picture [67 x 68] intentionally omitted <==**

**==> picture [67 x 68] intentionally omitted <==**

Figure 9: Saltire Pair 

## **4.1.2 Graphs determined by their spectrum** 

We have seen that not all graph properties can be determined by a graph’s spectrum. In this section we will investigate which graphs can be fully constructed from information in the spectrum. A graph _G_ is said to be _determined by its spectrum (DS)_ with respect to a matrix _A_ or _S_ if there does not exist any graph _G[′]_ cospectral and nonisomorphic to _G_ . The spectrum of a _DS_ graph is unique to that graph, so if we know the spectrum, we can build only one uniquely structured graph. Equivalently all graphs with this spectrum are isomorphic to the original.The number of non- _DS_ graphs with respect to _A_ increases over _n_ = 5 _, ...,_ 10 vertices. However, the percentage of non- _DS_ graphs on greater than 10 vertices appears to decrease according to computational evidence [3]. In general, it is easier to prove that graphs are not _DS_ than it is to show that a graph is _DS_ . 

|||
|---|---|
|_DS_ graph|spectrum|
|_Kn_|_{_(_n −_1)(1)_,_(_−_1)(_n−_1)_}_|
|_En_|_{_0(_n_)_}_|
|_Cn_|_{_2 cos( 2_kπ_<br>_n_ ) :_k_ = 0_, . . . , n −_1_}_|
|_Pn_|_{_2 cos( _kπ_<br>_n_+1) :_k_ = 1_, . . . , n}_|



Figure 10: some common _DS_ graphs 

Note that the disjoint union of _DS_ graphs does not necessarily create another _DS_ graph. There are some exceptions, including the disjoint union of _r_ path graphs _Pn_ 1 + _..._ + _Pnr_ which is _DS_ with respect to _A_ . This is also true for the disjoint union of _r_ complete graphs _Kn_ 1 + _..._ + _Knr_ , and the disjoint union of cycle graphs _Cn_ 1 + _..._ + _Cnr_ . Examples of _DS_ graphs and their spectra are given in Figure 10. 

Since there exist no adjacency cospectral pairs on fewer than 5 vertices, all graphs with 4 or fewer vertices are _DS_ . In contrast, when we examine the Seidel matrix we find that for _n >_ 1 vertices there are no Seidel- _DS_ 

13 

graphs. 

## **4.2 The Seidel matrix** 

The _Seidel matrix_ of a graph _G_ with vertex set _{v_ 1 _, v_ 2 _, ..., vn}_ is the _n × n_ matrix denoted _S_ ( _G_ ) = [ _s_ ] _ij_ . The entries of the Seidel matrix are given by: 

**==> picture [134 x 43] intentionally omitted <==**

Equivalently the Seidel matrix _S_ is given by _S_ = _J −_ 2 _A − I_ . 

## **5 Seidel switching** 

In this section we define and compare specific types of switching operations on graphs and matrices. We conclude the section with a detailed proof of a well known switching result from spectral graph theory. 

The Seidel matrix is strongly related to a structural operation on graphs known as Seidel switching which removes certain edges of a graph and then adds others. _Seidel switching_ on a graph _G_ constructs graphs which are cospectral to _G_ with respect to the Seidel matrix. Seidel switching is an equivalence relation that determines equivalence classes, called _Seidel classes_ or _switching classes_ , for the set of graphs on _n_ vertices. Switching equivalent graphs have similar Seidel matrices and therefore the same Seidel spectrum and characteristic polynomial. The switching classes for _G_ 4 are given in Figure 11. 

All Seidel cospectral graphs possess the same number of vertices, but they may contain a different number of edges. Seidel switching which is described below can be accomplished through both matrix and graph switching to build each class of Seidel cospectral graphs. 

**==> picture [200 x 132] intentionally omitted <==**

Figure 11: _G_ 4 Seidel classes 

## **5.1 Matrix switching** 

There exist multiple methods for conducting a Seidel switch. We will define the process of matrix switching before characterizing another method. A _Seidel switch_ requires the vertices of _G_ to be partitioned into two vertex sets. We can then partition the Seidel matrix into submatrices corresponding to these vertex sets such that blocks _S_ 11 and _S_ 22 represent the adjacencies between vertices of the same vertex set and blocks _S_ 12 and _S_ 21 represent the adjacencies between vertices of different vertex sets, resulting in: 

**==> picture [105 x 24] intentionally omitted <==**

14 

Note that _S_ 21 = _S_ 12 _[T]_[for][all][possible][partitions;][so][we][can][rewrite] _[S]_[(] _[G]_[)][as][follows:] 

**==> picture [105 x 25] intentionally omitted <==**

To perform a Seidel switch we replace blocks _S_ 12 and _S_ 12 _[T]_[with][their][negatives.][This][produces][the][Seidel] matrix: 

**==> picture [119 x 25] intentionally omitted <==**

Once� a Seidel� switch has been performed, we can find the graph that is switching equivalent to _G_ , denoted _G_ , using _S_ ( _G_ ) to determine vertex adjacencies. 

A graph _G_[�] that is cospectral to _G_ with respect to the Seidel matrix is rarely an isomorphism of _G_ . Since entries of _−_ 1 represent an edge between 2 vertices, while entries of 1 represent no edge between vertices, when the number of _±_ 1 entries varies from _S_ to _S_[�] in the _S_ 12 block, the result is a that _G_[�] will posses a different number of edges than _G_ , meaning no isomorphism is possible. _G_[�] will only possess the same number of edges as _G_ in a special case which allows for the possibility of an isomorphism, when _S_ 12 has an equal number of 1’s and _−_ 1’s in the Seidel matrix _S_ ( _G_ ). 

There exist conditions on the graphs and on their vertex partitions where Seidel switching can also produce cospectral graphs with respect to the adjacency matrix, but in general this is not the case. We will discuss this special occurence in Section 5.3. 

For an example of Seidel switching using a matrix, we consider the graph _K_ 2 + _K_ 2. We proceed to perform a Seidel switch on the vertex set _{a, b}_ , as defined in Figure 12, to find the graph _K_ 4 to be Seidel cospectral to _K_ 2 + _K_ 2. 

**==> picture [232 x 61] intentionally omitted <==**

**----- Start of picture text -----**<br>
a c a c<br>−→<br>b d b d<br>**----- End of picture text -----**<br>


Figure 12: Seidel switch with switching set _{a, b}_ 

**==> picture [172 x 94] intentionally omitted <==**

Performing a Seidel switch, we have 

**==> picture [96 x 26] intentionally omitted <==**

15 

**==> picture [120 x 50] intentionally omitted <==**

**----- Start of picture text -----**<br>
0 − 1 − 1 − 1<br> − 1 0 − 1 − 1 <br>= − 1 − 1 0 − 1   .<br>− 1 − 1 − 1 0<br> <br>**----- End of picture text -----**<br>


From _S_[�] we construct the graph _K_ 4 as a Seidel cospectral graph to _K_ 2 + _K_ 2 with switching set _{a, b}_ as shown in Figure 12. 

## **5.2 Graph switching** 

Similarly to matrix switching, _graph switching_ allows us to construct a Seidel switching class, this time without the intermediate step of building matrices. Two graphs _G_ and _GU_ are _switching equivalent_ (or _Seidel equivalent_ ) if and only if _G_ can be redrawn as _GU_ through Seidel switching operations. 

Consider the partition of the vertices of _G_ into sets _U_ and _V − U_ . Let _GU_ denote a graph obtained from _G_ by switching with respect to _U_ . Viewing a Seidel switch directly on the graph, we switch the adjacencies between all pairs ( _u, v_ ) such that _v ∈ U_ and _v ∈ V − U_ . This produces a switching equivalent graph, _GU_ that is equivalent to the the matrix switching process. 

We will further detail the construction of a specific Seidel equivalence class composed of graphs in _G_ 4 in Section 5.4. We define _G_ 4 to be the set of uniquely structured graphs on 4 vertices in Figure 11. Note that the Seidel equivalence classes on _G_ 4 can be found by switching using either a matrix or a graph. We can relate graph switching to matrix switching when we observe that _G_[�] is equivalent to _GU_ where _U_ contains all vertices that make up the _S_ 11 block of matrix _S_ ( _G_ ) given above. So we see that the organization of the Seidel matrix lends well to graph structure. 

**==> picture [276 x 208] intentionally omitted <==**

**----- Start of picture text -----**<br>
a b c d a b c d<br>e f g e f g<br>a b c d a b c f g<br>e f g d e<br>**----- End of picture text -----**<br>


Figure 13: Seidel switch of _K_ 3 _,_ 4 to _K_ 2 _,_ 5 with switching set _{a, b, c, e}_ , teal edges removed, and orange edges added 

For an example of the switching process directly on a graph, consider performing a Seidel switch on the complete bipartite graph _K_ 3 _,_ 4. We use switching set _{a, b, c, e}_ highlighted in Figure 13. We proceed to remove all edges across vertex sets _{a, b, c, e}_ and _{d, f, g}_ . Then we add any edges that were not previously present across our switching sets. When we reorder our vertices, we see that we have switched to the complete 

16 

bipartite graph _K_ 2 _,_ 5. We will prove in Section 6 that a Seidel switch performed on a complete bipartite graph will always generate another complete bipartite graph. 

## **5.3 Godsil-McKay switching** 

There are many constructions of cospectral pairs that are currently known, including Seidel switching and Godsil-McKay switching. A _Godsil-McKay switch (GM switch)_ is a type of Seidel switch used to construct adjacency cospectral graphs _G_ and _G[′]_ beginning with a graph _G_ that satisfies certain conditions. This construction can be thought of as a form of Seidel Switching such that the graph produced is always cospectral with respect to both the adjacency and Seidel matrices. 

Note that the smallest adjacency cospectral graphs that can be constructed by a GM-switch graphs are on 8 vertices, indicating that not every adjacency cospectral pair is obtainable through a GM switch. 

To construct cospectral graphs using a GM switch we start with a graph _G_ and let _π_ be a partition of the vertex set of _V_ ( _G_ ) such that _π_ = _{C_ 1 _, ..., Ck, D}_ . Let _i, j_ , and _k_ be integers such that 1 _≤ i_ and _j ≤ k_ . Since we will only consider this construction for the _k_ = 1 case, we say that _i_ = 1 = _k_ . Then _π_ = ( _C, D_ ). Let _n_ denote the number of vertices within _C_ . That is, _n_ = _|C|_ . 

The specifications for performing a GM Switch are that a graph _G_ must meet the following conditions: 

- (a) _n_ must be even. 

- (b) The induced subgraph formed by the vertex set _C_ must be a regular graph. 

- (c) For all _v ∈ D_ , _v_ must be adjacent to either 0 _, n/_ 2, or _n_ vertices in _C_ . 

If conditions (a),(b), and (c) hold then for every _v ∈ D_ that has _n/_ 2 neighbors in _C_ , we delete these edges and then add edges between _v_ and the _n/_ 2 vertices in _C_ to which _v_ was not previously adjacent. After performing this process, we will have constructed a graph, denoted _G[π]_ , that is guaranteed to be adjacency cospectral to our original graph _G_ . To detail the original proof given by Godsil and McKay in 1982 [5], we define a matrix _Qm_ then first show a series of lemmas. 

Let _Qm_ = ( _m_[2][)] _[J][m][ −][I][m]_[for][any][positive][integer] _[m]_[.][Then] _[Q][m]_[has][the][form:] 

**==> picture [192 x 195] intentionally omitted <==**

**Lemma 5.1.** _Q_[2] _m_[=] _[ I][m][.]_ 

17 

_Proof._ 

**==> picture [352 x 194] intentionally omitted <==**

The entries on the main diagonal, [ _Q_[2] _m_[]] _[ii]_[will][be][in][the][form:] 

**==> picture [453 x 252] intentionally omitted <==**

**==> picture [19 x 8] intentionally omitted <==**

The off diagonal entries [ _Q_[2] _m_[]] _[ij]_[for] _[i][ ̸]_[=] _[ j]_[have][the][form:] 

**==> picture [471 x 71] intentionally omitted <==**

18 

**==> picture [130 x 65] intentionally omitted <==**

**==> picture [19 x 7] intentionally omitted <==**

Then: 

**==> picture [106 x 90] intentionally omitted <==**

**Lemma 5.2.** _Let X be an m × n matrix with constant row sums r and constant column sums c. Then QmXQn_ = _X._ 

_Proof._ Without loss of generality, addition within the dot product can be reordered to show: 

**==> picture [478 x 289] intentionally omitted <==**

Since the _m × n_ matrix _X_ has constant column sums _c_ , without loss of generality, we can simplify the terms in the matrix _QmX_ of the form where: 

**==> picture [242 x 24] intentionally omitted <==**

19 

**==> picture [180 x 149] intentionally omitted <==**

**==> picture [414 x 108] intentionally omitted <==**

Since _X_ has constant row sums, without loss of generality by symmetry, the entries of the matrix ( _QmX_ ) _Qn_ can be expressed in the form: 

**==> picture [360 x 284] intentionally omitted <==**

20 

**==> picture [77 x 22] intentionally omitted <==**

Since the adjacency matrix is square and all submatrices corresponding to subgraphs are also square and symmetric, _m_ = _n_ . Additionally, an adjacency matrix _X_ will have its constant column sums equal to its constant row sums so that _c_ = _r_ . Thus, 

**==> picture [137 x 50] intentionally omitted <==**

So: 

**==> picture [131 x 70] intentionally omitted <==**

**Lemma 5.3.** _Let Q_ 2 _m be a matrix with dimensions_ 2 _m ×_ 2 _m. Let ⃗x be a vector with_ 2 _m entries such that m entries are_ 0 _and m entries are_ 1 _. Let[⃗] j_ 2 _m denote the all ones vector of dimension_ 2 _m. Then Q_ 2 _m⃗x_ = _[⃗] j_ 2 _m−⃗x. Proof._ Recall that matrix _Q_ is defined such that 

**==> picture [111 x 25] intentionally omitted <==**

**==> picture [164 x 143] intentionally omitted <==**

Since entries 01 _, ...,_ 0 _m_ and 11 _, ...,_ 1 _m_ can be written in any order within _⃗x_ , without loss of generality let 

**==> picture [50 x 84] intentionally omitted <==**

21 

Then: 

Since: 

and 

**==> picture [294 x 521] intentionally omitted <==**

Then: 

**==> picture [65 x 85] intentionally omitted <==**

22 

= _[⃗] j_ 2 _m − ⃗x._ 

Now that we have shown the necessary lemmas, we will show that adjacency cospectral graphs always result from a GM switch. Recall that similar matrices have the same multiset of eigenvalues so we can prove that two graphs are cospectral by constructing a similarity transformation matrix. We remind the reader of the theorem here. 

**Theorem 5.4.** _(Godsil, McKay [5]) Let G be a graph and let π_ = ( _C, D_ ) _be a partition of V_ ( _G_ ) _which satisfies conditions_ 

- _(a) |C|_ = _n must be even._ 

- _(b) The induced subgraph formed by the vertex set C must be a regular graph._ 

- _(c) For all v ∈ D, v must be adjacent to either_ 0 _, n/_ 2 _, or n vertices in C._ 

_Then G and G[π] are cospectral graphs._ 

_Proof._ Let _A_ be the adjacency matrix of _G_ and let _B_ be the adjacency matrix of _G[π]_ where _A_ is labeled in an order that follows _π_ = ( _C, D_ ). Then: 

**==> picture [90 x 25] intentionally omitted <==**

where _L_ represents the submatrix denoting the adjacencies between vertices across sets _C_ and _D_ . Based on the properties of _π_ we see that _A_ ( _C_ ) has constant row and constant column sums and that each column of _L_ has either 0 _, n/_ 2, or _n_ ones. 

We will show that _B_ = _QAQ_ where _Q_ is a block diagonal matrix such that: 

**==> picture [76 x 25] intentionally omitted <==**

Next we can examine _QQ_ . We show that _Q_ = _Q[−]_[1] and thus _Q_ is invertible. By the properties of block matrix multiplication: 

**==> picture [136 x 69] intentionally omitted <==**

Then by Lemma 5.1 

**==> picture [76 x 25] intentionally omitted <==**

**==> picture [20 x 7] intentionally omitted <==**

Lemma 5.2 shows that the adjacencies within the subgraphs of _G_ induced by each of _C_ or _D_ will be preserved by conjugation with _Q_ . Lemma 5.3 shows the change of adjacency between neighbors across vertex sets _C_ and _D_ is immediate on vectors with equal numbers of 0’s and 1’s when using _Q_ as a transformation matrix. 

23 

_Qn_ is a symmetric matrix and we can see from the block diagonal matrix _Q_ that _Q_ = _Q[T]_ . That is, _Q_ is also a symmetric matrix. Since _QQ_ = _I_ we can see that _Q_ = _Q[−]_[1] . Therefore _Q[−]_[1] = _Q[T]_ . Then by Lemmas 5.2 and 5.3 the matrix 

**==> picture [220 x 156] intentionally omitted <==**

where for every column in _L_ that is a zero vector, _Qn[⃗]_ 0 = _[⃗]_ 0. For every column in _L_ such that every entry is 1, _Qn[⃗]_ 1 = _[⃗]_ 1, and by Lemma 5.3 for every column in _L_ with exactly half of its entries equal to 0 and the other half equal to 1, left multiplication by _Qn_ switches the 1’s to 0’s and the 0’s to 1’s. Since we haven’t changed the subgraphs induced by _C_ or _D_ , the only difference between _A_ and this matrix are blocks _L[′]_ and _L[T][ ′]_ . 

Observe that _L[′]_ and _L[T][ ′]_ represent the vertex adjacencies across sets _C_ and _D_ , and we have only changed entries in columns with half the entries equal to zero. These columns correspond to vertices _v ∈ D_ that are adjacent to _n/_ 2 vertices in _C_ . Switching 0’s to 1’s in these columns turns nonedges across sets into edges, and switching 1’s to 0’s turns edges into nonedges. Since we do not alter the columns in _L[′]_ corresponding to vertices _v ∈ D_ adjacent to all or no vertices in _C_ , we have described a GM switch, and we conclude that _QAQ[−]_[1] = _B_ . Thus we have preserved the eigenvalues of _A_ such that _A_ and _B_ will be similar matrices. Since _A_ and _B_ are adjacency matrices of _G_ and _G[π]_ respectively, _G_ and _G[π]_ are cospectral graphs. 

## **5.4 Seidel equivalence classes** 

We have just observed the relationship between Seidel switching and adjacency cospectral graphs. There are a finite number of graphs we can switch to and thus Seidel switching partitions graphs of _n_ vertices into equivalence classes. Consider all possible switching sets for the graph _K_ 2 _,_ 2 shown in Figure 14 . When we perform a Seidel switch about each of these sets we find that we have constructed a switching class. 

For some Seidel classes, _C_ we can build a new equivalence class _C_[¯] by taking the complement of each graph in _C_ . Here we will refer to _C_ and _C_[¯] as _complement classes_ . Superimposing complement classes gives the complete graph in every case. That is, for all graphs _G_ in a class _C_ , there exists _G_[¯] in _C_[¯] such that _E_ ( _G_ ) _∪E_ ( _G_[¯] ) = _E_ ( _Kn_ ). Seidel switching preserves the Seidel characteristic polynomial and spectrum. 

**==> picture [290 x 62] intentionally omitted <==**

Figure 14: Switching class obtained by switching from _K_ 2 _,_ 2 to _K_ 1 _,_ 3 with switching set _{a}_ and then by switching from _K_ 1 _,_ 3 to _K_ 0 _,n_ with switching set _{b}_ . 

24 

**Lemma 5.5.** _If_ ( _λ, ⃗x_ ) _is an eigenpair of the Seidel matrix S for a given graph G, then_ ( _−λ, ⃗x_ ) _is an eigenpair of S[c] ._ 

_Proof._ Let _G_ be a graph. Let _S_ and _S[c]_ be the Seidel matrices of _G_ and _G_[¯] respectively. Let ( _λ, ⃗x_ ) be an eigenpair of _S_ . Edges in _G_ become non-edges in _G_[¯] and the converse is true by definition of a complement. In terms of the Seidel matrix, since edges are denoted by _−_ 1 and nonedges by 1, taking the complement turns every _−_ 1 to a 1 and every 1 to a _−_ 1. That is, _S[c]_ = _−S_ . 

By definition of an eigenpair, _S⃗x_ = _λ⃗x_ . Then _S[c] ⃗x_ = _−S⃗x_ = _−λ⃗x_ so ( _−λ, ⃗x_ ) is an eigenpair of _S[c]_ . 

In the first two sets in Figure 15 are the complete bipartite class and its complement class of graphs. Highlighted in the same color are graphs and their complements. Consider superimposing the graphs of the same color across each class, that is the graph _Ki,n−i_ in _C_ with graph _Ki_ + _Kn−i_ in _C_[¯] for _i_ = 0 _, .., n_ . In every case this gives the complete graph. Thus we see that these are complement classes. We will prove in Section 6 that the complete bipartite class of graphs and its complement class of graphs appear in _Gn_ for all _n_ . 

**==> picture [206 x 136] intentionally omitted <==**

**----- Start of picture text -----**<br>
, ,<br>� �<br>, ,<br>� �<br>, , , ,<br>� �<br>**----- End of picture text -----**<br>


Figure 15: _G_ 4 Seidel classes 

A Seidel _switching self-complementary (SSC)_ class of graphs is an equivalence class in which any graph in the class is self complementary or has its complement contained within the same class of graphs. An example is shown in the final set of Figure 15 where graphs of the same color are complements. For graphs on _n_ vertices such that _n ≡_ 3 (mod 4) there exists no _SSC_ class of graphs [10]. 

We have now examined properties of specific graphs as well as various graph operations of significance. Using this background we will proceed to present original results on Seidel switching classes and their associated properties. 

## **6 New results on the Seidel matrix** 

Motivated by strong results on the adjacency matrix and the study of adjacency cospectral graphs, we give results that hold for all graphs before using the Seidel matrix and the associated operation of Seidel switching to show results specific to complete bipartite graphs and their complements. 

We proceed by proving results that hold for all Seidel characteristic polynomials. We show a generalized form for the first three coefficients of the Seidel characteristic polynomial for all graphs. 

**Theorem 6.1.** _The coefficients of the terms of the Seidel characteristic polynomial λ[n] and λ[n][−]_[1] _have magnitudes of_ 1 _and_ 0 _, respectively._ 

25 

_Proof._ Let _G_ be a graph with vertex set [ _n_ ]. Let _S_ denote the Seidel matrix of _G_ . By the permutation definition of the determinant 

**==> picture [351 x 24] intentionally omitted <==**

where _si,σ_ ( _i_ ) for _i_ = 1 _, ..., n_ is an entry of _S − λI_ . 

For the _n × n_ matrix _S − λI_ there are _n_ entries on the main diagonal. Due to the structure of the Seidel matrix, for all _i_ = 1 _, ..., n_ , _sii_ = _−λ_ , and no other _λ_ entry appears in _S − λI_ . The matrix entries _sii_ correspond to fixed elements within a permutation since this indicates element _i_ maps to _i_ . Then every factor _sii_ that contributes to a term of degree _c_ must be the sum of all permutations with the same number _c_ of fixed elements. To find the magnitude of the coefficient of the degree _n_ term, we first find the number of terms with degree _n_ in equation (1). We consider the number of possible permutations on [ _n_ ] with _n_ fixed elements, and observe that the only way to obtain a term of degree _n_ comes from the identity permutation since all _n_ values must be fixed. Thus the term _λ[n]_ has magnitude 1 in our characteristic polynomial. 

To find the number of terms in (1) with degree _n −_ 1 we consider the number of possible permutations on [ _n_ ] with _n −_ 1 fixed elements. If we fix _n −_ 1 elements, the single remaining element has no possible spot to move to and thus must also be fixed. Therefore, any permutation fixing _n −_ 1 elements fixes _n_ elements. Since there are no permutations that fix exactly _n −_ 1 elements, there are 0 terms of degree _n −_ 1 in the sum given in (1). 

Therefore, 1 and 0 are the magnitudes of the coefficients of _λ[n]_ and _λ[n][−]_[1] of every Seidel characteristic polynomial. 

_n_ **Theorem 6.2.** _The coefficient of the λ[n][−]_[2] _term of the Seidel characteristic polynomial has magnitude_ �2� _. Proof._ Following the same logic as in the proof of Theorem 6.1 we examine permutations of [ _n_ ] that fix _n −_ 2 elements. 

Observe that there are � _n_ 2� permutations with _n −_ 2 fixed elements. Thus there are _n −_ 2 entries of ( _−λ_ ) from the main diagonal of ( _S − λI_ ) resulting in terms of degree _λ[n][−]_[2] . Let _σ_ = ( _ij_ ) for _i ̸_ = _j_ be an arbitrary permutation with _n −_ 2 fixed elements. Since only two elements move, they must exchange positions. So we claim that each term in (1) with degree _n −_ 2 is _±λ[n][−]_[2] . 

Since the Seidel matrix is symmetric, _S − λI_ is also symmetric. Thus the value of the entries ( _sij_ ) and ( _sji_ ) are equal. Since the only nondiagonal entries in _S − λI_ are 1 and _−_ 1, ( _sij_ )( _sji_ ) = 1 for every _i_ = _j_ . Permutations of [ _n_ ] with _n −_ 2 fixed elements are transpositions and since each of these terms has the same number of fixed elements in our permutation, they have the same sgn( _σ_ ). 

**==> picture [354 x 76] intentionally omitted <==**

Summing over all pairs of _i, j_ we have[�] ( _−_ 1) _[n][−]_[1] _λ[n][−]_[2] = � _n_ 2�( _−_ 1) _[n][−]_[1] _λ[n][−]_[2] . Thus the coefficient of the _λ[n][−]_[2] _i_ = _j n_ term will have a magnitude of �2�. 

We proceed with our examination of complete bipartite graphs with respect to the operation of Seidel switching. 

26 

**==> picture [386 x 111] intentionally omitted <==**

**----- Start of picture text -----**<br>
SA A \ SA SA B \ SB<br>va va va · · · ua va va va · · · ub ub<br>vb · · · ub ub ua · · · vb<br>SB B \ SB A \ SA SB<br>**----- End of picture text -----**<br>


Figure 16: Seidel switch of a complete bipartite graph 

**Theorem 6.3.** _For all n, the set of graphs in the form Ka,n−a for a_ = 0 _, ..., ⌊[n]_ 2 _[⌋][is][a][Seidel][equivalence] class._ 

_Proof._ Let _C_ be the set of graphs of the form _Ka,n−a_ and let _QKa,n−a_ be the Seidel equivalence class of _Ka,n−a_ . Let _A_ and _B_ be vertex partitions for _Ka,n−a_ such that _|A|_ = _a_ and _|B|_ = _n − a_ . Let _S_ be a subset of _V_ ( _Ka,n−a_ ) and since _Ka,n−a_ is bipartite we have a partition of _S_ such that _S_ = _SA ∪ SB_ . 

Let _va ∈ SA_ , _vb ∈ SB_ , _ua ∈ A\SA_ , and _ub ∈ B\SB_ , as labeled in Figure 16. Note that either _SA_ or _SB_ can be empty. In our original graph _Ka,n−a_ edges _{va, ub}, {va, vb}, {ua, vb}_ , and _{ua, ub}_ are all present. 

We will first show that _QKa,n−a ⊆ C_ . That is, we seek to show that for any switching set _S_ , ( _Ka,n−a_ ) _[S]_ is a complete bipartite graph. 

To perform a Seidel switch ( _Ka,n−a_ ) _[S]_ we remove all edges of the forms _{ua, vb}_ and _{va, ub}_ then add all edges in the forms _{va, ua}_ and _{vb, ub}_ . Thus we have switched from _Ka,n−a_ to a graph _Ka−|SA|_ + _|SB |,n−a−|SB |_ + _|SA|_ with edges _{va, vb}, {ua, ub}, {va, ua}_ , and _{vb, ub}_ . Since this gives all edges which cross partite sets and none within a partite set, _Ka−|SA|_ + _|SB |,n−a−|SB |_ + _|SA|_ is indeed a complete bipartite graph with partite sets _A\SA ∪ B_ and _B\SB ∪ A_ . Therefore _QKa,n−a ⊆ C_ . 

Next we seek to show that _C ⊆ QKa,n−a_ . Let _Ka,n−a_ be fixed. Let _t_ be arbitrary where _t_ = 0 _, ..., ⌊[n]_ 2 _[⌋]_[.] Consider a Seidel switch on the graph _Kt,n−t_ . We will demonstrate that _Kt,n−t_ is in _QKa,n−a_ . That is, we will show that there exists a set _S_ such that ( _Ka,n−a_ ) _[S][∼]_ = _Kt,n−t_ . 

Case 1: Suppose _t_ = _a_ . Then we have in effect performed the Seidel switch with _S_ = _∅_ given by ( _Ka,n−a_ ) _[S]_ = _Kt,n−t_ . 

Case 2: Suppose _t < a_ . Then we choose a switching set of any _a − t_ vertices in _A_ . When we perform a Seidel switch with this set our resulting graph is _Ka−_ ( _a−t_ )+0 _,n−a−_ 0+( _a−t_ ) which reduces to _Kt,n−t_ . 

Case 3: Suppose _t > a_ . Then we choose a switching set of any _t − a_ vertices in _B_ . When we perform a Seidel switch our resulting graph is _Ka−_ 0+( _t−a_ ) _,n−a_ +0 _−_ ( _t−a_ ) which reduces to _Kt,n−t_ . 

In all cases a Seidel switch ( _Ka,n−a_ ) _[S]_ gives the graph _Kt,n−t_ so we can observe that ( _Ka,n−a_ ) _[S][∼]_ = _Kt,n−t_ . Thus _C ⊆ QKa,n−a_ . 

_QKa,n−a ⊆ C_ and _C ⊆ QKa,n−a_ , therefore _QKa,n−a_ = _C_ . Thus the set of complete bipartite graphs on _n_ vertices forms a Seidel equivalence class. 

27 

Next we examine the structure of the Seidel characteristic polynomial for the complete bipartite equivalence class and its complement alongside their spectra. We begin by showing the form of the Seidel spectra for complete bipartite graphs. 

**Theorem 6.4.** _The Seidel spectrum of a complete bipartite graph Ka,b is always of the form {−_ 1[(] _[n]_[)] _,_ ( _n −_ 1)[(1)] _}._ 

_Proof._ Consider a complete bipartite graph _Ka,b_ with partite sets _A, B_ on _n_ vertices, as shown in Figure 17. 

**==> picture [96 x 92] intentionally omitted <==**

Figure 17: The complete bipartite graph _Ka,b_ . 

If we examine the matrix ( _S − λI_ ) of this graph, ordered by the partite sets, we have a block matrix: 

**==> picture [278 x 178] intentionally omitted <==**

Both the _A_ and _D_ blocks have the form below: 

**==> picture [96 x 61] intentionally omitted <==**

where _A_ has dimensions _a × a_ and _D_ has dimensions _b × b_ . Within blocks _A_ and _D_ we have that all off diagonal entries are equal to 1 since the vertices within a partite set of a complete bipartite graph are nonadjacent. Blocks _B_ and _C_ contain all _−_ 1 entries, since these blocks represent pairs of vertices across partite sets. That is, _−J_ blocks give our edges. While both blocks _B_ and _C_ are the matrix ( _−J_ ) they have differing dimensions. Note that _C_ = _B[T]_ , which becomes clear when we write out the dimensions of each block based on the partitions given by complete bipartite graphs in their more generalized forms. That is: 

**==> picture [258 x 24] intentionally omitted <==**

28 

Since we seek to calculate the determinant of a block matrix, we will use the Schur complement of _D_ , along with Theorem 2.2 to calculate det( _D_ )det( _A − BD[−]_[1] _C_ ). We begin by calculating det( _D_ ), which has dimensions _b × b_ , using row operations. So we have: 

**==> picture [279 x 316] intentionally omitted <==**

**==> picture [171 x 11] intentionally omitted <==**

**==> picture [121 x 13] intentionally omitted <==**

Next we consider det( _A − BD[−]_[1] _C_ ). We will begin by calculating _D[−]_[1] . Note that we can rewrite _D_ such that _D_ = _P_ + _Q_ . Recall that _D_ = _J − λI − I_ , so we can let _P_ = _I_ ( _−λ −_ 1) and _Q_ = _J_ . Then the hypotheses of Theorem 2.1 are satisfied and: 

**==> picture [370 x 135] intentionally omitted <==**

29 

**==> picture [325 x 578] intentionally omitted <==**

Now we will compute _BD[−]_[1] _C_ . Note that _B_ has dimensions _a × b_ , _D[−]_[1] has dimensions _b × b_ , and _C_ has 

30 

dimensions _b × a_ . Thus our matrices are comforming and the product will be a matrix with dimensions _a × a_ . 

**==> picture [488 x 345] intentionally omitted <==**

Finally, we calculate _A − BD[−]_[1] _C_ . Let _mij_ denote the entries of _A − BD[−]_[1] _C_ . These entries are given by 

**==> picture [143 x 36] intentionally omitted <==**

Then, the determinant of the Schur complement of _D_ gives: 

**==> picture [324 x 68] intentionally omitted <==**

**==> picture [431 x 106] intentionally omitted <==**

31 

**==> picture [321 x 202] intentionally omitted <==**

**==> picture [282 x 28] intentionally omitted <==**

Now we consider the full formula for the determinant of a block matrix. For these calculations, recall that _a_ + _b_ = _n_ , the number of vertices in the complete bipartite graph _Ka,b_ . Then: 

**==> picture [509 x 28] intentionally omitted <==**

**==> picture [354 x 28] intentionally omitted <==**

**==> picture [291 x 12] intentionally omitted <==**

**==> picture [243 x 141] intentionally omitted <==**

**==> picture [132 x 13] intentionally omitted <==**

This gives the Seidel spectrum _{−_ 1[(] _[n][−]_[1)] _,_ ( _n −_ 1)[(1)] _}_ . 

Observe that this is also known to be the spectrum of _Kn_ with respect to the adjacency matrix. We now give a form of the Seidel characteristic polynomial for the complete bipartite class. 

32 

**Corollary 6.4.1.** _The Seidel characteristic polynomial of a complete bipartite graph is always given by the form:_ 

**==> picture [112 x 29] intentionally omitted <==**

_Proof._ We will consider the binomial theorem and manipulate it to arrive at the factored form of the complete bipartite Seidel characteristic polynomial. We begin by multiplying the binomial theorem by _y[−]_[1] . 

**==> picture [119 x 29] intentionally omitted <==**

**==> picture [168 x 180] intentionally omitted <==**

From here, we calculate the derivative with respect to _y_ . That is, 

**==> picture [284 x 80] intentionally omitted <==**

Then when we let _y_ = 1 and _x_ = _λ_ .We have, 

**==> picture [262 x 29] intentionally omitted <==**

**==> picture [207 x 28] intentionally omitted <==**

Finally, we multiply the expression by ( _−_ 1). 

**==> picture [252 x 28] intentionally omitted <==**

**==> picture [230 x 29] intentionally omitted <==**

33 

**==> picture [223 x 78] intentionally omitted <==**

We have ( _λ_ + 1) _[n][−]_[1] ( _λ_ + 1 _− n_ ) which gives the Seidel characteristic polynomial of a complete bipartite graph as shown in the proof of Theorem 6.4. 

Observe that the complement of a complete bipartite graph is a disjoint union of complete components graph with two complete components. We will show a general form for the Seidel spectrum of this class of graphs. We give a detailed proof of the following corrollary, but we note that it is an immediate application of Theorem 6.4 and Lemma 5.5. 

**Corollary 6.4.2.** _The Seidel spectrum of the complement of a complete bipartite graph, Ka_ + _Kb is always of the form {_ 1[(] _[n]_[)] _,_ (1 _− n_ )[(1)] _}._ 

_Proof._ Consider the matrix _S −λI_ of a graph _Ka_ + _Kb_ . We can then rewrite this as a block matrix partitioned by components _Ka_ and _Kb_ such that we have blocks _A, B, C, D_ with dimensions _a × a, a × b, b × a_ , and _b × b_ respectively. 

**==> picture [298 x 178] intentionally omitted <==**

We will proceed using similar methods to those in Theorem 6.4 with the Schur complement of _D_ which has dimensions _b × b_ . Beginning with det( _D_ ) we have: 

**==> picture [281 x 141] intentionally omitted <==**

34 

**==> picture [244 x 154] intentionally omitted <==**

**==> picture [171 x 11] intentionally omitted <==**

**==> picture [122 x 13] intentionally omitted <==**

From here we calculate _D[−]_[1] and note that _D_ = (1 _− λ_ ) _I_ + ( _−J_ ). Let _P_ = (1 _− λ_ ) _I_ and _Q_ = _−J_ . Then by Lemma 2.1 

**==> picture [346 x 68] intentionally omitted <==**

**==> picture [254 x 258] intentionally omitted <==**

35 

**==> picture [305 x 154] intentionally omitted <==**

Observe that _B_ has dimensions _a × b_ , _D[−]_[1] has dimensions _b × b_ , and _C_ has dimensions _b × a_ . Thus the product _BD[−]_[1] _C_ will be a matrix with dimensions _a × a_ . 

**==> picture [448 x 273] intentionally omitted <==**

**==> picture [133 x 51] intentionally omitted <==**

Now we calculate _A − BD[−]_[1] _C_ . Let _mij_ denote the entries of _A − BD[−]_[1] _C_ . These entries are given by 

**==> picture [143 x 36] intentionally omitted <==**

Then, 

36 

**==> picture [324 x 69] intentionally omitted <==**

Let � _λ_[2] _−_ + _λbλ_ +1 _−−λb−b_ + ( _a −_ 1) _−λλ_ +1 _−_ 1 _−b_ � = _c_ . When we add all rows to row 1 we have 

**==> picture [382 x 424] intentionally omitted <==**

Now we consider the full formula for the determinant of a block matrix. That is: 

**==> picture [514 x 27] intentionally omitted <==**

**==> picture [282 x 13] intentionally omitted <==**

**==> picture [291 x 13] intentionally omitted <==**

37 

**==> picture [243 x 13] intentionally omitted <==**

**==> picture [205 x 172] intentionally omitted <==**

This gives the Seidel spectrum _{_ 1[(] _[n][−]_[1)] _,_ (1 _− n_ )[(1)] _}_ . 

We now give a form of the Seidel characteristic polynomial for the complement class of the complete bipartite class which contains graphs made up of two complete components. 

**Corollary 6.4.3.** _The Seidel characteristic polynomial of graphs in the complete bipartite complement class is always given by the form:_ 

**==> picture [126 x 29] intentionally omitted <==**

_Proof._ Consider the binomial theorem: 

**==> picture [182 x 279] intentionally omitted <==**

38 

**==> picture [304 x 281] intentionally omitted <==**

Let _y_ = _−_ 1 and _x_ = _λ_ . Then, 

So we have ( _λ −_ 1) _[n][−]_[1] ( _λ −_ 1 + _n_ ), which gives the Seidel characteristic polynomial of the complement of a complete bipartite graph, as shown in Corollary 6.4.3. 

Here we have given a form for the magnitudes of the first three coefficients of every Seidel characteristic polynomial. Next we have shown that there exists a complete bipartite switching class for Seidel classes on any _n_ vertices in Theorem 6.3. We provided a characterization of the Seidel spectrum for complete bipartite graphs and their graph complements in Theorem 6.4 and Corollary 6.4.2. We concluded our results by giving a form for the characteristic polynomials of these classes in Corollaries 6.4.1 and 6.4.3. 

## **7 Conclusion** 

In this paper we have examined cospectral graphs with respect to the adjacency and Seidel matrices. We have explained in detail the original proof of the GM-switch. We have also provided a general form of the Seidel characteristic polynomial, _ϕ_ ( _S_ ( _G_ )) for all complete bipartite graphs on _n_ vertices and their complements. 

For future research directions we would be interested in searching the literature on self containing classes for open questions, where self containing Seidel classes are equivalence classes which contain their graph complements. We hope that this could provide insights into what structural similarities graphs in classes without a complement class posses. Similarly, it would be interesting to study graphs in particular complement classes in the hopes of determining a clear structural property shared by all graphs within a class, as was the case for the complete bipartite class and its complement class. We have observed a pattern for golden graphs, graphs that possesses at least one eigenvalue equal to the golden ratio. Based on computational evidence, we conjecture that for any _n >_ 5 in which golden graphs exist, there is a Seidel class containing only golden graphs. 

Other research directions could include an examination of the distribution of adjacency cospectral graphs across Seidel equivalence classes in order to better determine graph properties that give non-DS graphs. 

39 

Because of the relationship between GM switching and Seidel switching, we conjecture that such adjacency cospectral graphs cannot be obtained through a GM switch. 

Finally, we could look into determining a generalizable form for the fourth coefficient of _ϕ_ ( _S_ ( _G_ )). The third coefficient gives the total number of possible edges of _G_ for any graph on _n_ vertices. Therefore it is our hope that the fourth coefficient of _ϕ_ ( _S_ ( _G_ )) has some discernible relationship to graphs on _n_ vertices and in particular the switching class containing _G_ . 

40 

## **References** 

- [1] Feryal Alayont and Steven Schlicker. _Linear Algebra and applications: An inquiry-based approach_ . 2019. 

- [2] Emily Barranca. _Recognizing induced subgraph and tree structure from the adjacency spectrum of a graph_ . url: `https://digitalcommons.uri.edu/oa_diss/1678/` . 

- [3] Edwin R. van Dam and Willem H. Haemers. “Which graphs are determined by their spectrum?” In: _Linear Algebra and its Applications_ 373 (Nov. 2003), pp. 241–272. doi: `10.1016/s0024-3795(03) 00483-x` . 

- [4] Reinhard Diestel. _Graph theory_ . New York: Springer, 2000. 

- [5] C. D. Godsil and B. D. McKay. “Constructing cospectral graphs”. In: _Aequationes Mathematicae_ 25.1 (Dec. 1982), pp. 257–268. doi: `10.1007/bf02189621` . 

- [6] Chris Godsil and Gordon F. Royle. _Algebraic graph theory_ . Springer, 2013. 

- [7] Carl Dean Meyer. _Matrix analysis and applied linear algebra_ . Siam, Society for industrial and applied mathematics, 2000. 

- [8] Kenneth S. Miller. “On the inverse of the sum of matrices”. In: _Mathematics Magazine_ 54.2 (Mar. 1981), pp. 67–72. doi: `10.1080/0025570x.1981.11976898` . 

- [9] A.J. Schwenk. “Computing the Characteristic polynomial of a graph”. In: _Graphs and Combinatorics. Lecture Notes in Mathematics_ 406 (1974). doi: `https://doi.org/10.1007/BFb0066438` . 

- [10] Boumediene Et-Taoui and Augustin Fruchard. “On switching classes of graphs”. In: _Linear Algebra and its Applications_ 549 (July 2018), pp. 246–255. doi: `10.1016/j.laa.2018.03.037` . 

41 

