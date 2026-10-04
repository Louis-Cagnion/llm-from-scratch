# MA06. Trigonometry and complex numbers

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 2. Core mathematics and programming | MA04, MA05 | MA10, MA22 |

## Why this module

Position encodings of Transformers are built from sines and cosines, and rotary position embeddings (RoPE) are rotations best understood as multiplication by complex numbers of modulus one. The Fourier transform, used in signal processing and image compression, rests on the same ideas. This module gives the geometric and algebraic tools behind them.

## Objectives

After this module, you can work with angles, trigonometric functions and identities, and compute with complex numbers in all their forms, seeing multiplication as rotation and scaling.

## Competences evaluated

1. Convert between degrees and radians and place angles on the unit circle.
2. Give exact values of sin, cos and tan for the standard angles, and use the unit circle to find others (symmetries, periodicity).
3. Know the graphs of sin, cos and tan (period, amplitude, phase, frequency) and transform them.
4. Apply the fundamental identities (sin² + cos² = 1, addition formulas, double-angle formulas) to simplify and prove identities.
5. Solve trigonometric equations on an interval.
6. Compute with complex numbers in algebraic form (sum, product, conjugate, quotient, modulus).
7. Convert between algebraic, trigonometric and exponential forms, and use Euler's formula e^(iθ) = cos θ + i sin θ.
8. Interpret multiplication by a complex number as a rotation and a scaling of the plane, and use it to rotate 2D vectors.
9. Compute powers and roots of complex numbers (de Moivre's formula, nth roots of unity) and place them on the circle.

## Notions, in learning order

1. **Angles**: degrees, radians, arc length, the unit circle.
2. **Trigonometric functions**: sine, cosine, tangent on the unit circle, exact values, signs by quadrant.
3. **Graphs**: periodicity, amplitude, frequency, phase shift, wavelength.
4. **Identities**: Pythagorean identity, addition and subtraction formulas, double angle, product-to-sum (first look).
5. **Equations**: solving sin x = a, cos x = a, tan x = a on intervals.
6. **Complex numbers**: the imaginary unit, algebraic form, operations, conjugate, modulus, the complex plane.
7. **Polar and exponential forms**: argument, trigonometric form, Euler's formula, multiplication of moduli and addition of arguments.
8. **Rotations**: multiplication by e^(iθ), 2D rotation matrices (first look), rotating a pair of coordinates (the idea behind RoPE).
9. **Powers and roots**: de Moivre, roots of unity, regular polygons on the circle.

## Practice

- Unit-circle drills until exact values are automatic.
- Proving identities with the addition formulas, then re-deriving the addition formulas from Euler's formula.
- Once IN02 is validated: a small complex-number class written by hand (without Python's `complex` type) with multiplication, modulus and polar conversion, used to rotate points and to draw the roots of unity with the ASCII plotter.

## Evaluation format

One written session without a calculator, about 1 hour 30: around 15 exercises covering every competence, including one identity to prove. Pass mark 100 %.

## References

- OpenStax, *Precalculus 2e*, chapters on trigonometric functions, identities and complex numbers (free).
- 3Blue1Brown, videos on Euler's formula and complex multiplication (free).
