**a. Proving A²B = BA²**

1. **Given:** A, AB, and BA are symmetric matrices. This means:
    
    - A = A<sup>T</sup> (1.13.1 Definition - Symmetric Matrix)
        
    - (AB) = (AB)<sup>T</sup> (1.13.1 Definition - Symmetric Matrix)
        
    - (BA) = (BA)<sup>T</sup> (1.13.1 Definition - Symmetric Matrix)
        
2. **Theorem 1.8.5:** For any matrices A and B where the product AB is defined, (AB)<sup>T</sup> = B<sup>T</sup>A<sup>T</sup>.
    
3. **Applying the theorem and givens:**
    
    - (AB)<sup>T</sup> = B<sup>T</sup>A<sup>T</sup> = BA (because A is symmetric)
        
    - Since AB is symmetric, AB = (AB)<sup>T</sup>. Therefore, AB = BA.
        
4. Now consider A²B:
    
    - A²B = A(AB)
        
    - Since AB=BA, we have A²B = A(BA) = (AB)A (Associative Law of Matrix Multiplication).
        
    - Again since AB=BA, we have A²B = (BA)A = BA².
        

Therefore, A²B = BA².

**b. Proving A and B are invertible**

1. **Given:** C = BA² + AB² is invertible.
    
2. From part (a), we know AB = BA. Thus, we can rewrite C:
    
    - C = BA² + AB² = BA² + BAB = BA² + B²A = B(A² + AB) = B(A² + BA) = BA(A+B)
        
3. **Theorem about invertible matrices:** A matrix is invertible if and only if its determinant is non-zero. Thus |C| ≠ 0.
    
4. **Theorem 3.5.4:** For square matrices A,B and C, it holds that |ABC|=|A||B||C|. So, |C| = |BA(A+B)| = |B||A||A+B|.
    
5. Since |C| ≠ 0, it must be that |B| ≠ 0 and |A| ≠ 0 and |A+B| ≠ 0 (because the product of these determinants is non-zero).
    
6. **Theorem about invertible matrices:** A matrix is invertible if and only if its determinant is non-zero. Therefore, since |A| ≠ 0 and |B| ≠ 0, both A and B are invertible.
    

Therefore, both matrices A and B are reversible.