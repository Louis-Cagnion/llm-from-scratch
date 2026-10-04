# MA08. Linear algebra I

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 2. Core mathematics and programming | MA02, MA03 | MA14, MA15, MA22 |

## Why this module

A language model is mostly matrix products: every layer multiplies a vector of activations by a matrix of weights, attention compares vectors with dot products, embeddings are vectors whose angles carry meaning. This module gives the concrete, computational side of linear algebra; MA14 adds the abstract structure.

## Objectives

After this module, you can compute with vectors and matrices by hand, interpret dot products and norms geometrically, solve linear systems by Gaussian elimination, and compute inverses, determinants and ranks.

## Competences evaluated

1. Compute linear combinations of vectors, and interpret them geometrically in 2D and 3D.
2. Compute dot products, norms (L1, L2, L∞), distances and angles; compute a cosine similarity and interpret it.
3. Compute matrix-vector and matrix-matrix products, state when they are defined, and count their multiplications and additions.
4. Use the properties of the matrix product (associativity, distributivity, non-commutativity) and of the transpose ((AB)ᵀ = BᵀAᵀ).
5. Recognize special matrices (identity, diagonal, triangular, symmetric, permutation) and their properties.
6. Solve a linear system by Gaussian elimination (row reduction to echelon form), and describe its solution set (unique, none, infinitely many).
7. Compute the inverse of a matrix by Gauss-Jordan elimination, and decide whether a matrix is invertible.
8. Compute determinants (2 × 2, 3 × 3, cofactor expansion, through row reduction) and use their properties.
9. Compute the rank of a matrix and relate it to the solutions of the system.
10. Interpret a 2 × 2 matrix as a transformation of the plane (rotation, scaling, shear, projection).

## Notions, in learning order

1. **Vectors**: coordinates, addition, scalar multiplication, linear combinations, geometric view.
2. **Dot product and norms**: definition, geometric meaning, Cauchy-Schwarz (statement), orthogonality, the three norms, cosine similarity.
3. **Matrices**: notation, rows and columns, matrix-vector product as a linear combination of columns and as dot products with rows.
4. **Matrix product**: definition, cost (n³ for square matrices), properties, block products, transpose.
5. **Special matrices**: identity, diagonal, triangular, symmetric, permutation, orthogonal (first look).
6. **Linear systems**: matrix form Ax = b, Gaussian elimination, echelon forms, pivots, free variables.
7. **Inverse**: definition, Gauss-Jordan method, inverse of a product, when no inverse exists.
8. **Determinant**: 2 × 2 and 3 × 3 formulas, cofactor expansion, effect of row operations, determinant of a product, geometric meaning (area and volume scaling).
9. **Rank**: definition through echelon form, relation to invertibility and to systems.
10. **Matrices as transformations**: geometric effect of 2 × 2 matrices, composition of transformations as products.

## Practice

- Hand computations of every operation, small and then larger.
- Geometry exercises: angle between two vectors, projection of one vector onto another, image of a square under a matrix.
- Once IN02 is validated: a hand-written matrix module with lists of lists (product, transpose, Gaussian elimination with exact fractions, inverse, determinant, rank), tested on many random cases against each other (A·A⁻¹ = I).

## Evaluation format

One written session without a calculator, about 2 hours: around 15 exercises covering every competence, including one system of 4 equations to solve by elimination. Pass mark 100 %.

## References

- Gilbert Strang, *Introduction to Linear Algebra* and MIT OpenCourseWare *18.06 Linear Algebra* (free lectures).
- 3Blue1Brown, *Essence of Linear Algebra* (free videos).
- Marc Peter Deisenroth, A. Aldo Faisal and Cheng Soon Ong, *Mathematics for Machine Learning* (free book), chapter 2.
