# MA21. Numerical analysis and floating point

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA07, MA10, MA18 | MA24 |

## Why this module

Models are trained in bfloat16 and served in 4-bit formats, softmax overflows if computed naively, a sum of millions of terms loses precision, and the hand-written math library must compute exp and log as accurately as the system's. Every number in the project is a floating-point number: this module explains exactly how they behave.

## Objectives

After this module, you can explain and predict floating-point behavior in every format used in deep learning, write numerically stable computations, evaluate elementary functions accurately, measure errors in ULP, and generate and test pseudo-random numbers.

## Competences evaluated

1. Represent numbers in binary and decode and encode IEEE 754 values (sign, exponent, mantissa) in float64, float32, float16 and bfloat16.
2. Describe fp8 (E4M3, E5M2) and microscaling formats (MXFP8, MXFP4, NVFP4): range, precision, shared scales.
3. Explain rounding modes, machine epsilon, ULP, subnormal numbers, infinities and NaN, and compute the ULP distance between two values.
4. Predict overflow, underflow and cancellation, and rewrite computations to avoid them (log-sum-exp, stable softmax, stable sigmoid).
5. Bound the error of a sum and use Kahan or pairwise summation.
6. Compute the condition number of a computation and distinguish an ill-conditioned problem from an unstable algorithm.
7. Evaluate an elementary function accurately: argument reduction, Taylor and minimax polynomial approximation, Horner's scheme, Newton iterations for square root and reciprocal.
8. Interpolate with linear, bilinear and bicubic interpolation.
9. Choose the step of a finite-difference derivative by balancing truncation and rounding errors.
10. Implement pseudo-random generators (linear congruential, xorshift, PCG) and test them statistically (chi-square, serial correlation).

## Notions, in learning order

1. **Binary representation**: integers, fixed point, scientific notation in base 2.
2. **IEEE 754**: formats, special values, subnormals, rounding to nearest even, exact operations.
3. **Low-precision formats**: float16 versus bfloat16, fp8 variants, block-scaled microscaling formats.
4. **Error analysis**: absolute and relative errors, machine epsilon, ULP, error propagation.
5. **Cancellation and stability**: catastrophic cancellation, stable reformulations, log-sum-exp.
6. **Summation**: error growth, pairwise and Kahan summation.
7. **Conditioning**: condition numbers of functions, backward and forward error.
8. **Function evaluation**: argument reduction, polynomial approximation (Taylor, Chebyshev and minimax ideas), Horner, Newton for √x and 1/x, error measured in ULP.
9. **Interpolation**: linear, bilinear, bicubic.
10. **Numerical differentiation**: finite differences, optimal step.
11. **Pseudo-random numbers**: generators, periods, seeds, statistical tests.

## Practice

- Decoding and encoding floats by hand in every format.
- Rewriting unstable formulas found in naive code.
- Once IN06 is validated: a program that decodes any float bit by bit with `struct`, emulates float16 and bfloat16 rounding, computes ULP distances, and an accurate `exp` and `log` with argument reduction whose error is measured in ULP against `math`; PCG and xorshift generators passing the chi-square test.

## Evaluation format

One written session, about 2 hours 30: around 15 exercises covering every competence, including one encoding by hand, one stable reformulation and one error bound. Pass mark 100 %.

## References

- David Goldberg, *What Every Computer Scientist Should Know About Floating-Point Arithmetic* (1991, free article).
- Nicholas J. Higham, *Accuracy and Stability of Numerical Algorithms* (book, not free).
- Jean-Michel Muller, *Elementary Functions: Algorithms and Implementation* (book, not free).
- Melissa E. O'Neill, *PCG: A Family of Simple Fast Space-Efficient Statistically Good Algorithms for Random Number Generation* (2014, free paper).
