# MA20. Optimization

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA15, MA16 | MA25 |

## Why this module

Training is optimization: stochastic gradient descent and Adam move billions of parameters to minimize a loss, learning-rate schedules decide how fast, weight decay regularizes, and fitting a scaling law is itself a small optimization problem solved with L-BFGS and a robust loss. This module explains why these methods work and when they fail.

## Objectives

After this module, you can formulate optimization problems, analyze gradient descent and its variants, explain the behavior of the optimizers used to train neural networks, and solve constrained problems with Lagrangian methods.

## Competences evaluated

1. Formulate an optimization problem (variables, objective, constraints) and state optimality conditions.
2. Recognize convex sets and functions and explain why convex problems have no bad local minima.
3. Analyze gradient descent on a quadratic: step size, convergence rate, effect of the condition number, divergence when the step is too large.
4. Apply Newton's method and quasi-Newton methods (BFGS, L-BFGS), and compare their cost and convergence with gradient descent.
5. Explain stochastic gradient descent: noisy gradients, mini-batches, the role of the learning rate and its decay.
6. Explain and simulate momentum and Nesterov acceleration.
7. Derive AdaGrad, RMSProp and Adam, including Adam's bias correction, and explain AdamW's decoupled weight decay.
8. Describe non-convex landscapes: saddle points, plateaus, sharp and flat minima, and how stochastic noise and momentum interact with them.
9. Solve constrained problems with Lagrange multipliers and KKT conditions, and form a dual problem on a simple case.
10. Explain L1 and L2 regularization geometrically, robust losses such as the Huber loss, and line search.

## Notions, in learning order

1. **Optimization problems**: formulation, local and global minima, optimality conditions.
2. **Convexity**: convex sets, convex functions, criteria, strong convexity.
3. **Gradient descent**: algorithm, step size, convergence on smooth convex functions, conditioning.
4. **Second-order methods**: Newton's method, its cost, quasi-Newton methods, L-BFGS.
5. **Stochastic optimization**: stochastic gradients, mini-batches, variance, learning-rate schedules.
6. **Momentum**: heavy ball, Nesterov, the effect on ill-conditioned problems.
7. **Adaptive methods**: AdaGrad, RMSProp, Adam, bias correction, AdamW.
8. **Non-convex optimization**: saddle points, escaping them, landscapes of neural networks (overview).
9. **Constrained optimization**: Lagrangian, KKT conditions, duality.
10. **Regularization and robust fitting**: L1 and L2 penalties, Huber loss, line search.

## Practice

- Gradient descent by hand for a few steps on quadratics with different condition numbers.
- Deriving Adam's bias correction from the exponential moving averages of MA07.
- Once IN04 is validated: an optimizer laboratory on two-dimensional test functions (quadratic, Rosenbrock), where SGD, momentum, Nesterov, Adam and L-BFGS are implemented from scratch and their paths drawn as SVG.

## Evaluation format

One written session, about 2 hours 30: around 12 exercises covering every competence, including one convergence analysis on a quadratic and one derivation of an adaptive optimizer. Pass mark 100 %.

## References

- Stephen Boyd and Lieven Vandenberghe, *Convex Optimization* (free book), chapters 1 to 5 and 9.
- Jorge Nocedal and Stephen J. Wright, *Numerical Optimization* (book, not free), chapters on quasi-Newton methods.
- Diederik P. Kingma and Jimmy Ba, *Adam: A Method for Stochastic Optimization* (2014, free paper).
