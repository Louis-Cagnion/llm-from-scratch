# IN10. Testing, debugging and code quality

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 4. Multivariable mathematics, statistics and systems | IN04, IN05 | ME03 |

## Why this module

A bug in a gradient does not crash: the model simply learns worse, and nobody notices for weeks. A from-scratch stack only works if every piece is tested against something trusted: hand-written derivatives against finite differences, C kernels against the Python reference, every change against the previous results. This module builds the testing and debugging discipline the whole project depends on.

## Objectives

After this module, you can write unit, property-based and numerical regression tests, work test-first, debug systematically in Python and C, keep runs reproducible, and review code against explicit quality criteria.

## Competences evaluated

1. Write unit tests with `unittest` (test cases, fixtures, assertions, test discovery) for Python code, and a minimal test runner for C code.
2. Write property-based tests by generating random inputs and checking invariants (for example A·A⁻¹ = I, decode(encode(x)) = x).
3. Practice test-driven development: write a failing test from a specification, then the code that makes it pass.
4. Write numerical tests with correct tolerances (absolute, relative, in ULP), and explain why exact equality fails for floating-point results.
5. Check gradients with finite differences inside a test suite.
6. Make runs reproducible: seeds, recorded configurations, deterministic ordering.
7. Debug systematically: reproduce, minimize the failing case, form hypotheses, bisect; use pdb and gdb.
8. Use logging levels and structured messages that name the failing element and the real cause.
9. Review code against explicit criteria (dead code, security, robustness, documentation, duplication, naming) and write useful review comments.

## Notions, in learning order

1. **Why tests**: regression, specification, confidence to change code.
2. **Unit tests**: `unittest`, structure, assertions, fixtures, running tests, a tiny test framework for C.
3. **Property-based testing**: random input generation, invariants, shrinking a failing case by hand.
4. **Test-driven development**: red, green, refactor.
5. **Numerical testing**: floating-point comparisons, tolerances, ULP distances, reference implementations, golden files.
6. **Gradient checking**: finite differences in tests, choosing inputs that reveal bugs.
7. **Reproducibility**: seeds, configuration files, logging of versions and parameters.
8. **Debugging method**: scientific debugging, minimization, `git bisect`, pdb, gdb, printing versus debuggers.
9. **Logging and errors**: levels, messages that name the element and the cause, failing loudly.
10. **Code review**: the quality criteria applied in this project, reviewing one's own code with fresh eyes.

## Practice

- Writing a test suite for the programs of earlier modules (fractions, matrices, samplers), including property-based tests.
- A test-driven implementation of a small library from its specification only.
- A debugging exercise on a deliberately broken program with a subtle numerical bug, found with a minimized failing case.

## Evaluation format

One practical session, about 2 hours 30: write tests (unit, property-based, numerical) for a given module, debug a provided program and explain the method, review a code excerpt against the criteria. Pass mark 100 %.

## References

- The Python Library Reference: `unittest`, `pdb`, `logging` (official, free).
- David J. Agans, *Debugging: The 9 Indispensable Rules* (book, not free).
- Kent Beck, *Test-Driven Development: By Example* (book, not free).
