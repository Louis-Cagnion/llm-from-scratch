# MA11. Integration

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 3. Analysis, probability and algorithms | MA10 | MA15, MA17, MA22, MA23 |

## Why this module

Continuous probabilities are integrals: a density integrates to one, an expectation is an integral, and the normal distribution behind weight initialization and exact GELU needs the Gaussian integral and the error function. Integrals also give areas under curves (cumulative quantities) and appear in the theory of diffusion models.

## Objectives

After this module, you can compute integrals with antiderivatives, substitution and integration by parts, handle improper integrals, and approximate integrals numerically.

## Competences evaluated

1. Find antiderivatives of the usual functions and of simple combinations.
2. Interpret a definite integral as a signed area and as a limit of Riemann sums.
3. Apply the fundamental theorem of calculus in both directions, including derivatives of functions defined by an integral.
4. Integrate by substitution and by parts.
5. Compute improper integrals (infinite bounds, unbounded functions) and decide their convergence.
6. Compute the Gaussian integral ∫ e^(−x²) dx over ℝ (with the polar-coordinate argument once MA15 is seen, or admitted here) and use the error function erf.
7. Approximate integrals with the rectangle, trapezoid and Simpson rules, and compare their errors.

## Notions, in learning order

1. **Antiderivatives**: definition, constants, table of usual antiderivatives.
2. **Definite integrals**: area, Riemann sums, properties (linearity, additivity, positivity).
3. **Fundamental theorem of calculus**: both parts, functions defined by integrals.
4. **Techniques**: substitution, integration by parts, partial fractions (simple cases).
5. **Improper integrals**: infinite intervals, singularities, convergence by comparison.
6. **The Gaussian integral and erf**: statement, normalization of the normal density, the error function and its use.
7. **Numerical integration**: rectangle, trapezoid and Simpson rules, error orders, step choice.

## Practice

- Integration drills by technique, then mixed.
- Normalizing densities by hand (finding the constant that makes a function integrate to one).
- Once IN02 is validated: numerical integration programs compared on known integrals, and an approximation of erf by numerical integration checked against `math.erf`.

## Evaluation format

One written session without a calculator, about 1 hour 30: around 12 exercises covering every competence. Pass mark 100 %.

## References

- OpenStax, *Calculus Volume 1*, chapter 5, and *Calculus Volume 2*, chapters 1 to 3 (free).
- MIT OpenCourseWare, *18.01 Single Variable Calculus* (free).
