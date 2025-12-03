Let me help you solve this step by step.

1. First, let's prove that there is a non-trivial solution to $Ax=x$ or $Ax=-2x$

Step 1: From the given equation $A^2+A-2I=0$
We can rewrite this as: $A^2+A=2I$
Or: $(A+2I)(A-I)=0$

Step 2: This is a product of matrices equal to zero. A fundamental property of matrices tells us that if a product of matrices is zero, then at least one of them must have a non-trivial null space.

Step 3: Therefore, either:
- $(A-I)x=0$ has a non-trivial solution, which means $Ax=x$ has a non-trivial solution
OR
- $(A+2I)x=0$ has a non-trivial solution, which means $A x=-2x$ has a non-trivial solution

This proves the first part.

2. Now, let's prove that if $A^k=I$ for some $k\in \mathbb{N}$, then $A=I$

Step 1: We know that $A^2+A-2I=0$
This means $(A-I)(A+2I)=0$

Step 2: Let's assume $A\neq I$. Then from part 1, we know that either:
- $A$ has eigenvalue 1, or
- $A$ has eigenvalue -2

Step 3: If $A^k=I$, then all eigenvalues of $A$ must be $k$th roots of unity (i.e., complex numbers that when raised to power $k$ give 1)

Step 4: But we know any eigenvalue of $A$ must be either 1 or -2
- 1 is a $k$th root of unity for any $k$
- -2 is not a $k$th root of unity for any $k\in \mathbb{N}$ because $|-2|>1$

Step 5: Therefore, $A$ cannot have -2 as an eigenvalue. From part 1, this means $A$ must have 1 as an eigenvalue.

Step 6: Since $A^2+A-2I=0$, if we substitute any eigenvalue $\lambda$ of $A$, it must satisfy:
$\lambda^2+\lambda-2=0$

Step 7: We know 1 is an eigenvalue, and indeed it satisfies this equation:
$1^2+1-2=0$

The other possible eigenvalue would be -2, but we proved this is impossible if $A^k=I$

Step 8: Therefore, 1 is the only possible eigenvalue of $A$. Since $A$ is diagonalizable (as $A^k=I$ implies diagonalizability), this means $A=I$

Thus, we have proved that if $A^k=I$ for some $k\in \mathbb{N}$, then $A=I$.


Ah, good question! Let me help you prove this fundamental property, which is sometimes called the "zero product property" for matrices.

Theorem: If $P,Q$ are $n×n$ matrices and $PQ=0$, then either $\text{null}(P)\neq\{0\}$ or $\text{null}(Q)\neq\{0\}$.

Proof:

1) Let's prove this by contradiction. Suppose both matrices have trivial null spaces.

2) If $\text{null}(Q)=\{0\}$, then by the rank-nullity theorem:
   $\text{rank}(Q) + \text{null}(Q) = n$
   $\text{rank}(Q) + 0 = n$
   Therefore, $\text{rank}(Q)=n$

3) This means $Q$ is invertible, as a matrix is invertible if and only if it has full rank.

4) Similarly, if $\text{null}(P)=\{0\}$, then $P$ is invertible.

5) Now, if $PQ=0$, we can multiply both sides by $P^{-1}$ on the left (since $P$ is invertible):
   $P^{-1}(PQ)=P^{-1}0$
   $(P^{-1}P)Q=0$
   $IQ=0$
   $Q=0$

6) But if $Q=0$, then its null space is all of $\mathbb{R}^n$, which contradicts our assumption that $Q$ has trivial null space.

7) Therefore, our initial assumption must be false, and at least one of $P$ or $Q$ must have a non-trivial null space.

This proof shows why it's impossible for both matrices to have trivial null spaces when their product is zero. The key insights are:
- A matrix with trivial null space must be invertible
- If both matrices were invertible, their product would also be invertible
- But the zero matrix is not invertible
- Therefore, at least one matrix must be non-invertible (have non-trivial null space)

This property is crucial in linear algebra and appears in many proofs, including the one we just used for the original problem.