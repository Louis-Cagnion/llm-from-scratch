# MA15. Multivariable calculus

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 4. Multivariable mathematics, statistics and systems | MA10, MA11, MA08 | MA16, MA17, MA20 |

## Why this module

A loss depends on millions of parameters at once, so training needs derivatives in many variables: the gradient points to the steepest increase, the Jacobian describes how a layer transforms small changes, the Hessian describes curvature, and the multivariable chain rule is exactly what backpropagation computes. This module extends differentiation to many dimensions.

## Objectives

After this module, you can compute partial derivatives, gradients, Jacobians and Hessians, apply the multivariable chain rule, find and classify extrema with or without constraints, and compute multiple integrals.

## Competences evaluated

1. Describe functions of several variables with level sets and graphs.
2. Compute partial derivatives, the gradient, and directional derivatives, and interpret the gradient geometrically (direction of steepest ascent, orthogonal to level sets).
3. Compute the Jacobian matrix of a function from ℝⁿ to ℝᵐ and use it as the best linear approximation.
4. Apply the multivariable chain rule, in matrix form (product of Jacobians), on chains of vector functions.
5. Compute the Hessian matrix and write the second-order Taylor expansion of a function of several variables.
6. Find critical points and classify them (minimum, maximum, saddle point) with the Hessian.
7. Recognize convex functions of several variables (Hessian criterion).
8. Solve constrained optimization problems with Lagrange multipliers.
9. Compute double and triple integrals, and change variables with the Jacobian determinant (polar coordinates, including the Gaussian integral).

## Notions, in learning order

1. **Functions of several variables**: domains, graphs, level curves and sets, limits and continuity (overview).
2. **Partial derivatives**: definition, computation, higher order, Schwarz's theorem.
3. **Gradient and directional derivatives**: definition, geometric meaning, steepest ascent.
4. **Differentiability and the Jacobian**: the differential, linear approximation, Jacobian matrices.
5. **The chain rule**: composition of vector functions, product of Jacobians, computation graphs with several inputs and outputs.
6. **Second order**: Hessian, second-order Taylor expansion, quadratic approximation.
7. **Extrema**: critical points, Hessian test, saddle points, global extrema on compact sets.
8. **Convexity**: definition, criteria, why convex problems are easy.
9. **Constrained optimization**: Lagrange multipliers, geometric meaning, several constraints.
10. **Multiple integrals**: double and triple integrals, Fubini, change of variables, polar and spherical coordinates, the Gaussian integral.

## Practice

- Gradient and Jacobian computations by hand on the building blocks of neural networks (a linear layer, an elementwise activation, a sum of squares).
- Following a gradient by hand for a few steps on a two-variable function, and plotting the path on its level curves.
- Once IN04 is validated: a program that checks hand-computed gradients and Jacobians with finite differences, and draws level curves and a gradient descent path as SVG.

## Evaluation format

One written session, about 2 hours 30: around 15 exercises covering every competence, including one chain-rule computation in matrix form and one Lagrange problem. Pass mark 100 %.

## References

- OpenStax, *Calculus Volume 3* (free).
- MIT OpenCourseWare, *18.02 Multivariable Calculus* (free).
- Marc Peter Deisenroth, A. Aldo Faisal and Cheng Soon Ong, *Mathematics for Machine Learning* (free book), chapter 5.
