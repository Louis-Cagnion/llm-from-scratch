# MA24. Numerical linear algebra

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA14, MA21 | none directly (used by L27, L33 and the analysis tools of the LLM plan) |

## Why this module

LAPACK is not allowed, so every matrix algorithm the project needs must be written by hand: Cholesky for GPTQ quantization, Newton-Schulz iterations for the Muon optimizer, a Hadamard transform for rotation-based quantization, an SVD and a PCA for analyzing weights and activations. This module teaches how these algorithms work and how to make them numerically reliable.

## Objectives

After this module, you can implement and analyze the core algorithms of numerical linear algebra: factorizations, eigenvalue and singular value algorithms, iterative orthogonalization, fast transforms and principal component analysis.

## Competences evaluated

1. Compute LU factorization with partial pivoting, explain why pivoting is needed, and solve systems with forward and backward substitution.
2. Compute the Cholesky factorization of a symmetric positive definite matrix and use it to solve systems and invert matrices.
3. Compute the dominant eigenvector with power iteration, and the eigenvalues of a symmetric matrix with the QR algorithm or the Jacobi method.
4. Compute an SVD (through the eigen-decomposition of AᵀA and through a more stable method) and explain the difference in accuracy.
5. Apply the Newton-Schulz iteration to orthogonalize a matrix, explain its convergence condition, and relate it to the Muon optimizer.
6. Compute the fast Walsh-Hadamard transform and explain why random rotations spread outliers before quantization.
7. Perform a principal component analysis and interpret explained variance.
8. Explain randomized methods (randomized range finder, randomized SVD) at the level of ideas.
9. Analyze the stability and cost of each algorithm, and choose the right one for a given matrix.

## Notions, in learning order

1. **Direct solvers**: Gaussian elimination as LU, pivoting, triangular solves, cost.
2. **Cholesky**: existence for positive definite matrices, algorithm, uses.
3. **Eigenvalue algorithms**: power iteration, inverse iteration, the QR algorithm, the Jacobi method for symmetric matrices.
4. **Singular value decomposition**: algorithms, accuracy, truncated SVD.
5. **Iterative orthogonalization**: polar decomposition, Newton-Schulz iteration, convergence.
6. **Fast transforms**: Walsh-Hadamard transform, randomized rotations.
7. **Principal component analysis**: covariance, eigen-decomposition or SVD, explained variance.
8. **Randomized numerical linear algebra**: sketching, randomized range finder.
9. **Stability and cost**: backward stability, condition numbers (from MA14 and MA21), flop counts.

## Practice

- Small factorizations by hand (3 × 3 LU and Cholesky, a few iterations of power iteration).
- Once IN06 is validated: a numerical linear algebra library in pure Python (LU with pivoting, Cholesky, Jacobi eigenvalues, SVD, Newton-Schulz, Walsh-Hadamard, PCA), each algorithm tested against its mathematical properties (A = LU, QᵀQ = I, reconstruction errors) on random and ill-conditioned matrices.

## Evaluation format

One session, about 3 hours: hand computations on small matrices, algorithms to implement and test, and questions on stability and cost. Pass mark 100 %.

## References

- Lloyd N. Trefethen and David Bau, *Numerical Linear Algebra* (book, not free).
- Gene H. Golub and Charles F. Van Loan, *Matrix Computations* (book, not free).
- Nathan Halko, Per-Gunnar Martinsson and Joel A. Tropp, *Finding Structure with Randomness* (2011, free paper).
