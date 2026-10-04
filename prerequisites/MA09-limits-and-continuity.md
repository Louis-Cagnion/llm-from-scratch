# MA09. Limits and continuity

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 3. Analysis, probability and algorithms | MA07 | MA10 |

## Why this module

Derivatives, and therefore gradients and backpropagation, are defined as limits. Limits also describe how a function behaves far away (does a loss explode, does an activation saturate) and how fast an error shrinks, which the O and o notations express in every complexity and accuracy statement of the project.

## Objectives

After this module, you can compute limits of functions, prove simple limits rigorously, reason about continuity, and use asymptotic notation.

## Competences evaluated

1. Compute limits of functions at a point and at infinity, including one-sided limits.
2. Resolve indeterminate forms (0/0, ∞/∞, ∞ − ∞, 0 × ∞) by factoring, conjugates and comparative growth.
3. Prove a limit with the ε-δ definition for simple functions.
4. Use the limit theorems (operations, composition, squeeze theorem).
5. Decide whether a function is continuous at a point and on an interval, including piecewise functions, and extend a function by continuity.
6. Apply the intermediate value theorem (existence of a root) and the extreme value theorem (statement).
7. Find horizontal, vertical and oblique asymptotes.
8. Use Landau notation (o, O, ~) to compare functions and sequences, and simplify expressions with it.

## Notions, in learning order

1. **Intuition of a limit**: approaching a value, tables of values, graphs.
2. **Limits at a point and at infinity**: definitions, one-sided limits, infinite limits.
3. **Rigorous definition**: ε-δ for a point, ε-M for infinity, link with limits of sequences.
4. **Computing limits**: operations, composition, indeterminate forms and their resolution, squeeze theorem, comparative growth (from MA05).
5. **Continuity**: definition, operations on continuous functions, continuity of the reference functions, discontinuities, extension by continuity.
6. **Theorems on continuous functions**: intermediate value theorem (with the bisection method as a constructive proof), extreme value theorem.
7. **Asymptotes**: horizontal, vertical, oblique.
8. **Asymptotic comparison**: equivalents (~), little o, big O, their algebra, link with algorithm complexity.

## Practice

- Limit computations by hand, then ε-δ proofs on simple functions.
- Using the intermediate value theorem to locate roots, then the bisection method by hand.
- Once IN02 is validated: the bisection method as a program, with a stopping criterion and a count of iterations compared with the theory.

## Evaluation format

One written session, about 1 hour 30: around 15 exercises covering every competence, including one ε-δ proof. Pass mark 100 %.

## References

- OpenStax, *Calculus Volume 1*, chapter 2 (limits) (free).
- MIT OpenCourseWare, *18.01 Single Variable Calculus* (free).
