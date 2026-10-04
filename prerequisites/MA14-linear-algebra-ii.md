# MA14. Linear algebra II

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 4. Multivariable mathematics, statistics and systems | MA08 | MA16, MA23, MA24, MA26 |

## Why this module

The structure behind the computations: why low-rank adapters (LoRA) work is the singular value decomposition, why some layers train badly is a condition number, why initializations preserve norms is orthogonality, and tensors with many indices are handled with Einstein summation. This module gives the theory that turns matrix computations into understanding.

## Objectives

After this module, you can reason with vector spaces, bases and linear maps, compute and interpret eigenvalues, eigenvectors and singular values, and manipulate tensors of any order.

## Competences evaluated

1. Decide whether a set is a vector space or a subspace, whether vectors are linearly independent, and find a basis and the dimension.
2. Represent a linear map by a matrix in given bases, compute its kernel and image, and apply the rank theorem.
3. Change basis and compute the matrix of a map in a new basis.
4. Compute eigenvalues and eigenvectors of small matrices, diagonalize when possible, and explain when it is not.
5. State and apply the spectral theorem for symmetric matrices, and recognize positive definite matrices.
6. Recognize orthogonal matrices, compute orthogonal projections, and apply the Gram-Schmidt process and the QR decomposition by hand.
7. Explain the singular value decomposition, compute it for a small matrix, and use it for the best low-rank approximation (Eckart-Young).
8. Compute the Frobenius and spectral norms, the condition number, and explain their effect on numerical stability.
9. Compute Kronecker products and manipulate tensors of order 3 and more (shapes, contractions, permutations of axes).
10. Write and read Einstein summation (einsum) expressions for products, traces, batched products and attention-style contractions.

## Notions, in learning order

1. **Vector spaces**: axioms, examples (ℝⁿ, polynomials, matrices), subspaces, spans.
2. **Independence, bases, dimension**: linear independence, bases, coordinates, dimension.
3. **Linear maps**: definition, matrix representation, kernel, image, rank theorem, invertibility.
4. **Change of basis**: transition matrices, similar matrices.
5. **Eigenvalues and eigenvectors**: characteristic polynomial, eigenspaces, diagonalization, powers of matrices.
6. **Symmetric matrices**: spectral theorem, quadratic forms, positive definite and semi-definite matrices.
7. **Orthogonality**: orthonormal bases, orthogonal matrices, projections, Gram-Schmidt, QR decomposition, least squares as a projection.
8. **Singular value decomposition**: geometric meaning, computation for small matrices, low-rank approximation, pseudo-inverse.
9. **Norms and conditioning**: vector and matrix norms, condition number, sensitivity of linear systems.
10. **Tensors**: arrays of any order, shapes, axes, contractions, Kronecker product, einsum notation.

## Practice

- Proof and computation exercises by hand on small matrices.
- Interpreting the SVD of an image (as a matrix of pixels): reconstruction with few singular values.
- Once IN04 is validated: extending the MA08 matrix module with QR by Gram-Schmidt, power iteration for the largest eigenvalue, and a small einsum interpreter that evaluates expressions such as `ij,jk->ik` and `bhqd,bhkd->bhqk` on nested lists.

## Evaluation format

One written session, about 2 hours 30: around 15 exercises covering every competence, including one proof and one SVD computation by hand. Pass mark 100 %.

## References

- Gilbert Strang, *Introduction to Linear Algebra* and MIT OpenCourseWare *18.06 Linear Algebra* (free lectures).
- Sheldon Axler, *Linear Algebra Done Right* (free online edition).
- Marc Peter Deisenroth, A. Aldo Faisal and Cheng Soon Ong, *Mathematics for Machine Learning* (free book), chapters 2 to 4.
