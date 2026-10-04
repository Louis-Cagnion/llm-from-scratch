# MA10. Differentiation

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 3. Analysis, probability and algorithms | MA06, MA09 | MA11, MA15, MA21, MA23 |

## Why this module

Training a neural network means following derivatives: the gradient of the loss with respect to each weight tells how to change it. Backpropagation is nothing more than the chain rule applied systematically, and every activation function of the plan comes with its derivative. This module is the heart of the mathematics of learning.

## Objectives

After this module, you can differentiate any function built from the usual ones, explain the chain rule as the basis of backpropagation, study functions with their derivatives, and approximate functions locally with Taylor expansions.

## Competences evaluated

1. Compute a derivative from the definition (limit of the difference quotient) and interpret it as a slope and a rate of change.
2. Apply the rules: sum, product, quotient and chain rule, including long chains of compositions.
3. Differentiate the usual functions: powers, exp, ln, trigonometric functions, sigmoid, tanh, softplus, ReLU (where it is differentiable) and the tanh approximation of GELU.
4. Write the derivative of sigmoid and tanh in terms of the functions themselves (σ' = σ(1 − σ), tanh' = 1 − tanh²).
5. Study a function: sign of the derivative, variations, local and global extrema, convexity and inflection points.
6. Apply the mean value theorem and use it to bound a variation.
7. Write the Taylor expansion of a function at a point to a given order, and use it to approximate values and compute limits.
8. Use L'Hôpital's rule.
9. Apply Newton's method to solve an equation, and explain its convergence speed.
10. Approximate a derivative with finite differences and explain the choice of the step (first look, developed in MA21).

## Notions, in learning order

1. **Rate of change**: average rate, difference quotient, tangent line, instantaneous rate.
2. **The derivative**: definition, differentiability, derivative function, non-differentiable points (|x| and ReLU at 0).
3. **Rules**: linearity, product, quotient, chain rule (and its reading as a product of local derivatives along a chain of operations).
4. **Derivatives of usual functions**: powers, exp, ln, sin, cos, tan, inverse functions, the activation functions of neural networks.
5. **Function analysis**: monotonicity, extrema, second derivative, convexity, inflection points, optimization problems in one variable.
6. **Fundamental theorems**: Rolle, mean value theorem, consequences.
7. **Taylor expansions**: Taylor polynomial, Taylor-Young and Taylor-Lagrange forms, usual expansions, local approximation.
8. **Limits with derivatives**: L'Hôpital's rule, limits through Taylor expansions.
9. **Newton's method**: derivation from the tangent line, quadratic convergence, failure cases, computing √a and 1/a.
10. **Numerical derivatives**: forward and centered differences, truncation and rounding errors (first look).

## Practice

- Many derivatives by hand, including chains of five or more compositions written as a computation graph and differentiated node by node (a first backpropagation on paper).
- Function studies with full variation tables.
- Once IN02 is validated: a program comparing exact derivatives with centered finite differences for all activation functions, and Newton's method computing square roots, compared with `math.sqrt`.

## Evaluation format

One written session without a calculator, about 2 hours: around 15 exercises covering every competence, including one chain-rule computation on a computation graph of at least six nodes and one Taylor expansion. Pass mark 100 %.

## References

- OpenStax, *Calculus Volume 1*, chapters 3 and 4 (free).
- 3Blue1Brown, *Essence of Calculus* (free videos).
- MIT OpenCourseWare, *18.01 Single Variable Calculus* (free).
