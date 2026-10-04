# MA07. Sequences and series

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 2. Core mathematics and programming | MA03, MA05 | MA09, MA12, MA21, MA22 |

## Why this module

Training is a sequence of parameter updates whose convergence is the whole question; Adam keeps exponential moving averages, which are recurrences; learning-rate schedules are sequences; and the hand-written math library of the LLM plan computes exp, log, sin and cos with series. This module builds the notion of limit on sequences, where it is most concrete.

## Objectives

After this module, you can study sequences defined explicitly or by recurrence, decide convergence, compute classic sums and series, and approximate functions with power series.

## Competences evaluated

1. Recognize arithmetic and geometric sequences, give their general term and the sum of their first terms.
2. Study a sequence defined by a recurrence: compute terms, guess and prove a closed form by induction, study monotonicity and bounds.
3. Use the definition of the limit of a sequence (with ε) to prove a simple convergence, and the limit theorems (sums, products, comparison, squeeze).
4. Use the monotone convergence theorem (a monotone bounded sequence converges) and find the limit of a recurrence as a fixed point.
5. Decide the convergence of a series with the standard tests (geometric series, comparison, ratio test, alternating series), and compute geometric and telescoping sums.
6. Compute and interpret an exponential moving average m_t = β·m_(t−1) + (1 − β)·x_t, including its bias at the start and its correction.
7. Find the radius of convergence of a power series.
8. Use the Taylor series of exp, ln(1 + x), sin, cos and 1/(1 − x), and bound the error made by truncating them.

## Notions, in learning order

1. **Sequences**: explicit and recursive definitions, arithmetic and geometric sequences, closed forms.
2. **Behavior**: monotonicity, bounds, induction proofs on sequences.
3. **Limits of sequences**: definition with ε and N, uniqueness, limit theorems, squeeze theorem, divergence to infinity.
4. **Monotone convergence and fixed points**: monotone bounded sequences, recurrences u_(n+1) = f(u_n), fixed points, convergence speed (first look).
5. **Linear recurrences**: first order (including the exponential moving average and its bias correction), second order (Fibonacci, characteristic equation).
6. **Series**: partial sums, convergence, geometric series, harmonic series (diverges), telescoping series.
7. **Convergence tests**: comparison, ratio test, alternating series test, absolute convergence.
8. **Power series**: radius of convergence, the geometric series as a power series.
9. **Taylor series of usual functions**: exp, ln(1 + x), sin, cos, error bounds of truncated series, why argument reduction matters (first look).

## Practice

- Recurrence studies by hand, including a proof by induction for each.
- Simulating an exponential moving average by hand on a short sequence, with and without bias correction.
- Once IN02 is validated: programs that compute the terms of recurrences and plot them, sums of series with a stopping criterion, and a first version of exp and sin computed with their Taylor series, compared with `math.exp` and `math.sin` (the seed of the L01 math library).

## Evaluation format

One written session, about 2 hours: around 15 exercises covering every competence, including one convergence proof with ε and one recurrence study. Pass mark 100 %.

## References

- OpenStax, *Calculus Volume 2*, chapters on sequences, series and power series (free).
- Khan Academy, *Series* units of AP Calculus BC (free).
