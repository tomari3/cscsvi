![[Pasted image 20241209165741.png|Intro to Linear Algebra, Gilbert Strang]]

**Matrices carry data, and other matrices operate on that data. The goal is to "see into the matrix" by understanding its eigenvalues and eigenvectors and singular values and singular vectors.**

> [!question] Ponder These
> 1. Taking three straight lines of length $r,s,t$ on a page, what are the conditions that will make them into a triangle, if you can choose their angle
> 2. Suppose the direction of three straight lines $u,v,w$ are fixed and different, can you make a closed triangle using any numbers $a,b,c$ such that $au,bv,cw$?
> 3. Suppose you have four lines $u,v,w,z$ in different directions in 3-dimentional space, can you choose $a,b,c,d\neq0$ such that $au+bv+cw+dz=0$?
# 1	[[Vectors]] and [[Matrices]]
- Linear algebra is about vectors $v$ and matrices $A$
$$
v=\begin{bmatrix}
v_{1} \\
v_{2}
\end{bmatrix} = \begin{bmatrix}
2 \\
4
\end{bmatrix},
w=\begin{bmatrix}
w_{1}, \\
w_{2}
\end{bmatrix}=\begin{bmatrix}
1 \\
3
\end{bmatrix},
v+w=\begin{bmatrix}
3 \\
7
\end{bmatrix}
$$
- The **linear combination of $v$ and $w$ are the vectors $cv+dw$ for all numbers $c, d$** 
- The linear combination **fills the $xy$ plane**
$$
c \begin{bmatrix}
2 \\
4
\end{bmatrix} + d \begin{bmatrix}
1 \\
3
\end{bmatrix} = \begin{bmatrix}
2c+1d \\
4c+3d
\end{bmatrix}
$$
- The **Length** of that vector $w$ is $||w||=\sqrt{ 10 }=\sqrt{ w^2_{1}+w^2_{2} }=\sqrt{ 1+9 }$
- The **Dot Product** of $v$ and $w$ is $v\cdot w = v_{1}w_{1}+v_{2}w_{2}=(2)(1)+(4)(3)=14$
- **Matrix** $A$ can contain column vectors, in this case the matrix is 2 by 2
$$
A=\begin{bmatrix}
v & w
\end{bmatrix}=\begin{bmatrix}
2 & 1 \\
4 & 3
\end{bmatrix}
$$
- When a **Matrix** multiplies a **Vector** we get a combination $cv+dw$ of its columns
$$
A\times \begin{bmatrix}
c \\
d
\end{bmatrix}=\begin{bmatrix}
2 & 1 \\
4 & 3
\end{bmatrix}\begin{bmatrix}
c \\
d
\end{bmatrix} = \begin{bmatrix}
2c+1d \\
4c+3d
\end{bmatrix} = cv+dw
$$
- The **column space of the matrix A** is all the combinations $Ax$ by $c,d$, in this case its a plane
- In the following matrix $B$ there are 3 columns, but column $z$ is a combination of $v$ and $w$ so the column space is still the $xy$ plane
	- $v,w$ are **independent** while $v,w,z$ are **dependent**
	- A combination produces zero:
$$
B=\begin{bmatrix}
v & w & z
\end{bmatrix}=\begin{bmatrix}
2 & 1 & 3 \\
4 & 3 & 7
\end{bmatrix} \text{if } B\begin{bmatrix}
1 \\
1 \\
-1
\end{bmatrix}=v+w-z=\begin{bmatrix}
2 \\
4
\end{bmatrix}+\begin{bmatrix}
1 \\
3
\end{bmatrix}-\begin{bmatrix}
3 \\
7
\end{bmatrix}=\begin{bmatrix}
0 \\
0
\end{bmatrix}
$$
- The final goal is to understand **matrix multiplication $AB=A \times \text{each column of }B$**

## 1.1	[[Vectors]] and [[Linear Combinations]]
> [!note]
> 1. $2v-3w$ is a **linear combination** $cv+dw$ of the vectors $v,w$
2. for $v=\begin{bmatrix}4\\1\end{bmatrix}, w=\begin{bmatrix}2\\-1\end{bmatrix}$ that combination is $2\begin{bmatrix}4\\1\end{bmatrix}-3\begin{bmatrix}2\\-1\end{bmatrix}=\begin{bmatrix}5\\2\end{bmatrix}$
3. All combinations $c \begin{bmatrix}4\\1\end{bmatrix}+d\begin{bmatrix}2\\-1\end{bmatrix}$ fill the $xy$ plane. They produce every $\begin{bmatrix}x\\y\end{bmatrix}$
4. The vectors $c \begin{bmatrix}1\\1\\2\end{bmatrix}+d\begin{bmatrix}0\\0\\4\end{bmatrix}$ fill a **plane** in $xyz$ space, $\begin{bmatrix}1\\2\\3\end{bmatrix}$ is not on that plane

- Linear combinations of vectors are built on two basic operations:
	- **Multiply a vector by a number** $3v=3\begin{bmatrix}2\\1\end{bmatrix}=\begin{bmatrix}6\\3\end{bmatrix}$
	- **Add vectors $v$ and $w$** of the same dimension $v+w=\begin{bmatrix}2\\1\end{bmatrix}+\begin{bmatrix}4\\3\end{bmatrix}=\begin{bmatrix}6\\4\end{bmatrix}$
- Together they form a **linear combination** $cv+dw$ of $v$ and $w$
$c=5,d=-2\implies 5v-2w=5\begin{bmatrix}2\\1\end{bmatrix}-2\begin{bmatrix}4\\3\end{bmatrix}=\begin{bmatrix}10\\5\end{bmatrix}-\begin{bmatrix}8\\6\end{bmatrix}=\begin{bmatrix}2\\1\end{bmatrix}$
## 1.2	[[Dot Products]]
>[!info]
> 1. The **Dot Product** of $v=\begin{bmatrix}1\\2\end{bmatrix}, w=\begin{bmatrix}4\\6\end{bmatrix}$ is $v\cdot w=(1)(4)+(2)(6)=4+12=16$
> 2. The **Length** of $v(1,3,2)$ is $\sqrt{ v\cdot v }=\sqrt{ 1^2+3^2+2^2 }=\sqrt{ 1+9+4 }=\sqrt{ 14 }=||v||$
> 3. $v=(1,3,2)$ is **perpendicular** to $w=4,-4,4$ because $v\cdot w=0$
> 4. The angle $\theta=45^\circ$ between $v=\begin{bmatrix}1\\0\end{bmatrix}$ and $w=\begin{bmatrix}1\\1\end{bmatrix}$ has $\cos\theta=\frac{v\cdot w}{||v||\cdot||w||}=\frac{1}{(1)(\sqrt{ 2 })}$
> 5. All angles have $\cos\theta\leq1$. All vectors have Schwarz inequality $|v\cdot w|\leq||v||\cdot||w||$ and Triangle inequality $||v+w||\leq||v||+||w||$

> [!def] Dot Product
> $v=\begin{bmatrix}v_{1}\\v_{2}\end{bmatrix}, w=\begin{bmatrix}w_{1}\\w_{2}\end{bmatrix}\,v\cdot w=v_{1}w_{1}+v_{2}w_{2}$ 
> $v\cdot w=v_{1}w_{1}+v_{2}w_{2}+\dots+v_{n}w_{n}=w\cdot v$

> [!def] Unit Vector
> A **unit vector** $u$ has length $||u||=1$ and $v\neq0\to u=\frac{v}{||v||}$ is a unit vector
> A unit vector always have the length of 1

> [!def] Perpendicular Vectors
> Perpendicular vectors have $v\cdot w=0$ Then $||v+w||^2=||v||^2+||w||^2$
## 1.3	[[Column Space]]
> [!info]
> 1. $A=\begin{bmatrix}1&2\\3&4\\5&6\end{bmatrix}$ is a **3 by 2 matrix**: $m=3, n=2$. Rank $2$
> 2. The 3 components of $Ax$ are the **dot products** of the 3 rows of $A$ with the vector $x$
> $\begin{bmatrix}1&2\\2&4\\5&6\end{bmatrix}\begin{bmatrix}7\\8\end{bmatrix}=\begin{bmatrix}1\cdot7+2\cdot8\\3\cdot7+4\cdot8\\5\cdot7+6\cdot8\end{bmatrix}=\begin{bmatrix}23\\53\\83\end{bmatrix}$
> 3. $Ax$ is also a **combination of the columns** of $A$. $\begin{bmatrix}1&2\\3&4\\5&6\end{bmatrix}\begin{bmatrix}7\\8\end{bmatrix}=7\begin{bmatrix}1\\3\\5\end{bmatrix}+8\begin{bmatrix}2\\4\\6\end{bmatrix}$ 
> 4. The **column space of $A$** contains **all combinations** $Ax=x_{1}a_{1}+x_{2}a_{2}$
> 5. **Rank one matrices**: All columns of $A$ are on **one line**

- **Identity Matrix**: $$\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}$$
- **Diagonal Matrix**: $$
\begin{bmatrix}
2 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 5
\end{bmatrix}
$$
- **Triangular Matrix**: $$
\begin{bmatrix}
2 & 1 & -3 \\
0 & 4 & 7 \\
0 & 0 & 5
\end{bmatrix}
$$
- **Symmetric Matrix**: $$
\begin{bmatrix}
2 & 1 & -3 \\
1 & 4 & 7 \\
-3 & 7 & 5
\end{bmatrix}
$$

> [!info]
> The **Row Picture** of $Ax$ will come from **dot product** of $x$ with the rows of $A$
> The **Column Picture** will come from **linear combinations** of the columns of $A$
## 1.4	[[Matrix Multiplication]]

> [!info]
> 1. To multiply $AB$ we need *row length* for $A =$ *column length* for $B$
> 2. The number in row $i$ column $j$ of $AB$ is $\text{row i of A}\cdot\text{column j of B}$
> 3. By columns: $A \times\text{column j of B}=\text{column j of AB}$
> 4. Usually $AB\neq BA$ but always $(AB)C=A(BC)$
> 5. if $A$ has $r$ independent columns in $C$, then $A=CR=(m\times r)(r\times n)$

> [!def] Columns $j$ of $AB=A\times\text{column }j\text{ of }B$
> if $B=\begin{bmatrix}b_{1}\dots b_{p}\end{bmatrix}$ then $AB=\begin{bmatrix}Ab_{1}\dots Ab_{p}\end{bmatrix}$

$$
Ab_{1}=\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}\begin{bmatrix}
0 \\
1
\end{bmatrix}=\begin{bmatrix}
2  \\
4
\end{bmatrix}, A_{b_{2}}=\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}\begin{bmatrix}
1 \\
0
\end{bmatrix}=\begin{bmatrix}
1 \\
3
\end{bmatrix}, AB=\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}=\begin{bmatrix}
2 & 4 \\
3 & 1
\end{bmatrix}
$$

- Row way : Dot Products
$$
Ab_{1}=\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}\begin{bmatrix}
5 \\
7
\end{bmatrix}=\begin{bmatrix}
\text{row 1}\cdot b_{1} \\
\text{row 2}\cdot b_{1}
\end{bmatrix}=\begin{bmatrix}
1\cdot5+2\cdot7 \\
3\cdot5+3\cdot7
\end{bmatrix}=\begin{bmatrix}
19 \\
43
\end{bmatrix}
$$
- Column way : Combine Columns
$$
Ab_{1}=\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}\begin{bmatrix}
5 \\
7
\end{bmatrix}=5\begin{bmatrix}
1 \\
3
\end{bmatrix}+7\begin{bmatrix}
2 \\
4
\end{bmatrix}=\begin{bmatrix}
5 \\
15
\end{bmatrix}+\begin{bmatrix}
14 \\
28
\end{bmatrix}=\begin{bmatrix}
19 \\
43
\end{bmatrix}
$$

- When $A$ is $m\times n$ and $B$ is $n\times p$ then $AB$ is $m\times p$ 
- **Matrix multiplication is not commutative**. in general $BA\neq AB$
- **Matrix multiplication is associative** 
	- $(AB)C=A(BC), (AB)x=A(Bx)$
- **Matrix multiplication is distributive**
	- $A(B+C)=AB+AC$
## 1.5	Rank one matrices
- **All columns of rank one matrix lie on the same line** which is the column space of $A$
- **Only one independent row when there is only one independent column**
> [!info] $A=CR$
> 1. $C$ contains a full set of $r$ **independent columns** in $A$
> 2. $R=\begin{bmatrix}I&F\end{bmatrix}$ contains the **identity matrix $I$** in the same $r$ columns that held $C$
> 3. **The dependent columns of $A$ are combinations $CF$** of the independent columns in $C$

> [!def]
> Columns $j$ of $A=C\times$ columns $j$ of $R$. Row $i$ of $A=$ row $i$ of $C\times R$

- if all columns of $A$ are independent then $C=A$ and $R=I$
$$
A=\begin{bmatrix}
a_{1} & a_{2} & 3a_{1}+4a_{2}
\end{bmatrix}=\begin{bmatrix}
a_{1} & a_{2}
\end{bmatrix}\begin{bmatrix}
1 & 0 & 3 \\
0 & 1 & 4
\end{bmatrix}=CR
$$

- for a random $m\times n$ matrix $A$ we expect:
	- $m<n$ Probably many solutions to the $m$ equations $Ax=b$
	- $m=n$ Probably one solutions to the $n$ equations $Ax=b$
	- $m>n$ Probably no solutions. too many equations with only $n$ unknowns in $x$
- **Rank $r$** tells us the real size of our problem

# 2	Solving Linear Equations $Ax=b$
- We will talk about square matrices, $n\times n$
- $Ax=b$ give $n$ equations with $n$ unknowns in the vector $x$
- if there is one solution $x$ for each $b$ the matrix $A$ has an inverse $A^{-1}$ and $A^{-1}A=I, AA^{-1}=I$
- Multiplying $Ax=b$ by $A^{-1}$ produces $x=A^{-1}b$
- We will try to find $x$ without computing $A^{-1}$
$$
\begin{align*}
\left[\begin{array}{c|c}
\text{Square} & \\
\text{matrix} & b \\
A & 
\end{array}\right] 
\xrightarrow{\text{elimination}} 
\left[\begin{array}{c|c}
\begin{array}{c}
\text{Triangle} \\
U \\
\text{Zeros}
\end{array} & c
\end{array}\right]
\xrightarrow{\text{back substitution}}
\left[\begin{array}{c}
x
\end{array}\right]
\\[1em]
& Ax = b \\
& Ux = c \\
& x = U^{-1}c \\
& x = A^{-1}b
\end{align*}
$$
---
- Coefficient Matrix $A$
- Elimination Matrix $E_{ij}$
- Permutation Matrix $P$
- Upper Triangular $U$
- Overall Elimination $E$
- Transpose Matrix $A^T$
- Lower Triangular $L$
- Inverse Matrix $A^{-1}$
- Symmetric Matrix $S=S^T$
---
- to get $x$ we will do $A\to EA=U\to A=E^{-1}U=LU \to x$
	- If a step fails, it means $Ax=b$ has no solution for most $b$
## 2.1	Elimination and Back Substitution
> [!info]
> 1. Elimination subtracts $\ell_{ij}$ times row $j$ from row $i$, leaves a zero in row $i$
> 2. $Ax=b$ becomes $Ux=c$ or else there is no solution
> 3. $Ux=c$ is solved by back substitution because $U$ is upper triangular

- Systematic way of solving for $Ax=b$ where $n$ equations for $n$ unknown aka square matrix $A$ is $n\times n$
- Three options
	1. **Exactly one solution to $Ax=b$**: 
		- $A$ has an independent columns.
		- The rank is $n$
		- The only solution to $Ax=0$ is $x=0$
		- $A$ has an **inverse matrix $A^{-1}$** 
	1. **No solution to $Ax=b$**:
		- $b$ is not a combination of the columns of $A$
		- $b$ is not in the column space of $A$
		- The rank is $1$
	1. **Infinite solutions to $AX=0$**:
		- There are dependent columns
		- There are many ways to produce the zero vector $b=0$
		- We can multiply $X$ by any number $\alpha$
		- For any number $\alpha, A(x+\alpha X)=Ax+\alpha AX=b+0=b$

### 2.1.1	Back Substitution to Solve $Ux=c$
- Elimination produces upper triangular $U$ then $Ax=b\implies Ux=c$
1. Apply elimination to $Ax=b$
2. The result is $Ux=c$
3. Back substitute to find $x$
$$
Ux=c \implies \begin{bmatrix}
2 & 3 & 4 \\
0 & 5 & 6 \\
0 & 0 & 7
\end{bmatrix}\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{bmatrix}= \begin{bmatrix}
19 \\
18 \\
14 \\
\end{bmatrix}
$$

- $2,5,7$ are **pivot** and are non zero
> [!info]
> **Back Substitution** last row is $7x_{3}=14\implies x_{3}=2$
> **Work Upwards** next is $5x_{2}+6(2)=17\implies x_{2}=1$
> **Upwards** first row is $2x_{1}+3(1)+4(2)=19\implies x_{1}=4$
> **Conclusion** One solution to $Ux=c$ is $x=(4,1,2)$

$$Ax=b\implies Ux=c\implies x=U^{-1}c=A^{-1}b$$

- If we reach a pivot point $=0$ we know that matrix $A^*$ is not full rank meaning theres a dependent column and a non zero solution

### 2.1.2	Dependent or INdependent Columns

- **A triangular matrix $U$ has full rank exactly when its main diagonal has no zeros**
	- Which means the columns of $U$ are independent

```tikz
\usepackage{amsmath}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1.5]
    % First plot
    \begin{scope}[xshift=0cm]
        % Grid and axes
        \draw[->] (-0.5,0) -- (3.5,0) node[right] {$x$};
        \draw[->] (0,-1) -- (0,3.5) node[above] {$y$};
        
        % Grid lines (light gray)
        \draw[very thin,color=gray!30] (-0.5,-1) grid (3.5,3.5);
        
        % Lines with extended range
        \draw[thick] (0,1/2) -- (3,2) node[right] {$x-2y=-1$};
        \draw[thick] (0,-1/2) -- (3,1) node[right] {$x-2y=1$};
        
        % Points exactly at x=1,2,3
        \fill (1,1) circle (2pt);
        \fill (1,0) circle (2pt);
        \fill (3,2) circle (2pt);
        \fill (3,1) circle (2pt);
        
        % Matrix aligned with x-axis
        \node at (3.75,3) {$A=\begin{bmatrix} 1 & -2 \\ 1 & -2 \end{bmatrix}$};
    \end{scope}
    
    % Second plot
    \begin{scope}[xshift=6cm]
        % Grid and axes
        \draw[->] (-0.5,0) -- (3.5,0) node[right] {$x$};
        \draw[->] (0,-1) -- (0,3.5) node[above] {$y$};
        
        % Grid lines (light gray)
        \draw[very thin,color=gray!30] (-0.5,-1) grid (3.5,3.5);
        
        % Lines with extended range
        \draw[thick] (0,1/2) -- (3,2) node[right] {$x-2y=-1$};
        \draw[thick] (0,2) -- (2,0) node[right] {$x+y=2$};
        
        % Intersection point (1,1)
        \fill (1,1) circle (2pt);
        \node[above right] at (1,1) {$(1,1)$};
        
        % Matrix
        \node at (3.75,3) {$A=\begin{bmatrix} 1 & -2 \\ 1 & 1 \end{bmatrix}$};
    \end{scope}
\end{tikzpicture}
\end{document}
```

- Parallel lines means **no solution**
- Intersecting lines means **one solution**
- overlapping lines mean **infinite solutions**

## 2.2	Elimination Matrices and Inverse Matrices
> [!info]
> 1. Elimination multiplies $A$ by $E_{21},\dots E_{n_{1}}$ then $E_{32},\dots,E_{n2}$ as $A$ becomes $EA=U$
> 2. In reverse order, the inverses of the $E$ multiply $U$ to recover $A=E^{-1}U$ which is $A=LU$
> 3. $A^{-1}A=I$ and $(LU)^{-1}=U^{-1}L^{-1}$ then $Ax=b$ becomes $x=A^{-1}b=U^{-1}L^{-1}b$

### 2.2.1	Facts About Inverse Matrices

> [!def] The matrix $A$ is invertible if there exists a matrix $A^{-1}$ that inverts $A$
> **Two sided inverse** $A^{-1}A=I,AA^{-1}=I$

- Not all matrices have inverses
	- Columns must be independent
- The inverse exists if and only if elimination produces $n$ pivots
- The matrix $A$ cannot have two different inverses
	- $B(AC)=(BAC)\implies BI=IC\implies B=C$
- If $A$ is invertible, the only solution to $Ax=b$ is $x=A^{-1}b$
	- $(Ax=b)\times A^{-1}\implies x=A^{-1}Ax=A^{-1}b$
- if there is a nonzero vector $x$ such that $Ax=0$ then $A$ has dependent columns and cannot have an inverse. No matrix can bring $0$ back to $x$
	- if $A$ is invertible then $Ax=0$ only has the zero solution $x=A^{-1}0=0$
- A square matrix is invertible $\iff$ its columns are independent
- A $2\times2$ matrix is invertible $\iff$ the number $ad-bc$ is not zero
	- $\begin{bmatrix}a&b\\c&d\end{bmatrix}^{-1}=\frac{1}{ad-bc}\begin{bmatrix}d&-b\\-c&a\end{bmatrix}$
	- $ad-bc$ is the **determinant** of $A$
	- $A$ is invertible if its determinant is not zero
- A triangular matrix has an inverse provided no diagonal entries $d_{i}$ are zero
$$
A=\begin{bmatrix}
d_{1} & \times & \times & \times \\
0  & \cdot & \times & \times \\
0 & 0 & \cdot & \times \\
0 & 0 & 0 & d_{n}
\end{bmatrix} \to A^{-1}=\begin{bmatrix}
\frac{1}{d_{1}} & \times & \times & \times \\
0 & \cdot & \times & \times \\
0 & 0 & \cdot & \times \\
0 & 0 & 0 & \frac{1}{d_{n}}
\end{bmatrix}
$$

### 2.2.2	The inverse of a Product $AB$

- The Product of matrices $AB$ is invertible $\iff$ $A$ and $B$ are separately invertible and the same size
> [!note] If $A$ and $B$ are invertible (same size) then the inverse of $AB$ is $B^{-1}A^{-1}$
> $(AB)^{-1}=B^{-1}A^{-1}\implies(AB)(B^{-1}A^{-1})=AIA^{-1}=AA^{-1}=I$

- $(ABC)^{-1}=C^{-1}B^{-1}A^{-1}$
- if $AC=I$ then for square matrices $CA=I$
- **for square matrices, an inverse on one side is automatically an inverse on the other side**
### 2.2.3	$L$ is the inverse of $E$
$$
E^{-1}=\begin{bmatrix}
1 &  &  \\
\ell_{21} & 1 &  \\
0 & 0 & 1
\end{bmatrix}\begin{bmatrix}
1 &  &  \\
0 & 1 &  \\
\ell_{31} & 0 & 1
\end{bmatrix}\begin{bmatrix}
1 &  &  \\
0 & 1 &  \\
0 & \ell_{32} & 1
\end{bmatrix}=\begin{bmatrix}
1 &  &  \\
\ell_{21}  & 1 &  \\
\ell_{31} & \ell_{32} & 1
\end{bmatrix}=L
$$

## 2.3	Matrix Computation and $A=LU$

> [!info]
> 1. The elimination steps from $A$ to $U$ const $\frac{1}{3}n^3$ multiplication and subtractions
> 2. Each right side $b$ costs only $n^2$: forward to $Ux=c$ then back substitute for $x$
> 3. Elimination without row exchanges factor $A$ into $LU$

$$
AA^{-1}=I\implies A\begin{bmatrix}
 \\
x_{1} & \dots & x_{n} \\
 \\

\end{bmatrix}\begin{bmatrix}
 \\
e_{1} & \dots & e_{n} \\
 \\

\end{bmatrix}\implies A\begin{bmatrix}
 \\
x_{1} & \dots & x_{n} \\
 \\

\end{bmatrix}=\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
- **Gauss-Jordan elimination**: using matrix $\begin{bmatrix}A&I\end{bmatrix}$ producing $\begin{bmatrix}I&A^{-1}\end{bmatrix}$
	- Solve $AX=I\implies X=A^{-1}$ slower than solving $Ax=b$

$$
\begin{bmatrix}
A & I
\end{bmatrix}=
\begin{bmatrix}
\begin{array}{ccc|ccc}
1 & 0 & 0 & 1 & 0 & 0 \\
-1 & 1 & 0 & 0 & 1 & 0 \\
0 & -1 & 1 & 0 & 0 & 1
\end{array}
\end{bmatrix}\to
\begin{bmatrix}
\begin{array}{ccc|ccc}
1 & 0 & 0 & 1 & 0 & 0 \\
0 & 1 & 0 & 1 & 1 & 0 \\
0 & -1 & 1 & 0 & 0 & 1
\end{array}
\end{bmatrix}\to
\begin{bmatrix}
\begin{array}{ccc|ccc}
1 & 0 & 0 & 1 & 0 & 0 \\
0 & 1 & 0 & 1 & 1 & 0 \\
0 & 0 & 1 & 1 & 1 & 1
\end{array}
\end{bmatrix}=\begin{bmatrix}
I  & A^{-1}
\end{bmatrix}
$$

## 2.4	Permutation and Transposes
- **TODO**: read and summarize
## 2.5	Derivatives and Finite Difference Matrices
- **TODO**: read and summarize

# 3	The Four Fundamental Subspaces

## 3.1	Vector Spaces and Subspaces

> [!note]
> 1. Requirement: All linear combinations $cv+dw$ must stay in the vector space
> 2. The row space of $A$ is "spanned" by the rows of $A$. The columns of $A$ span $C(A)$
> 3. Matrices $M_{1}$ to $M_{N}$ and functions $f_{1}$ to $f_{n}$ span matrix spaces and function spaces

- The space $\mathbb{R}^n$ contains all column vector $v$ of length $n$
	- $v_{1}\dots v_{n}\in \mathbb{R}$
	- when complex numbers are allowed, the space becomes $\mathbb{C}^n$
	- A line in$\mathbb{R}^n$ is **not** a vector space unless it goes through the center point $(0,\dots,0)$

> [!def] A **subspace** of a vector space is a set of vectors (including 0) that satisfies two requirements: if $v$ and $w$ are vectors in the subspace, and $c$ is any scalar, then:
> 1. $v+w$ is in the subspace
> 2. $cv$ is in the subspace

> [!def] The rules of subspaces
> **A subspace containing $v$ and $w$ must contain all linear combination $cv+dw$**

> [!def] The columns space of $A$
> The column space consists of all linear combination of ht columns. 
> All possible vectors $Ax$, They fill the columns space $C(A)$
> To solve $Ax=b$ is to express $b$ as a combination of the columns, hence $b$ has to be inside the column space, else it has no solution
> $Ax=b$ is solvable $\iff$ $b$ is in the columns space of $A$

## 3.2	The Null-space of $A$: Solving $Ax=0$

>[!note]
> 1. The **nullspace** $N(A)$ in $\mathbb{R}^n$ contains all solutions $x$ to $Ax=0$ including $x=0$
> 2. Elimination from $A$ to $R_{0}$ to $R$ does not change the nullspace: $N(A)=N(R_{0})=N(R)$
> 3. The reduced row echelon rom $R_{0}$ has $I$ in $r$ columns and $F$ in $n-r$ columns
> 4. if column $j$ is dependent on previous columns, $Ax=0$ has a special solution with $x_{j}=1$
> 5. The $n-r$ special solutions to $Ax=0$ contains $-F$ and $I$
> 6. Every short wide matrix with $m<n$ has nonzero solutions to $Ax=0$ in its nullspace

- When $A$ is a square invertible matrix (rank $r=n$) the only solution is $x=0$ and the null space contains the zero vector; The columns of $A$ are independent
 
## 3.3	The Complete Solution to $Ax=b$

## 3.3	Independence, Basis, and Dimension

## 3.4	Dimension of the Four Subspaces