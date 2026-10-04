# MA26. Number theory, finite fields and elliptic curves

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 6. Advanced computer science and GPU | MA13, MA14 | IN14 |

## Why this module

The project downloads its data over HTTPS with a TLS 1.3 client written by hand. TLS rests on mathematics: AES computes in a field of 256 elements, GCM authenticates in a field of 2¹²⁸ elements, X25519 exchanges keys on an elliptic curve, and certificates are verified with RSA or ECDSA signatures. This module gives exactly the number theory and algebra these algorithms need.

## Objectives

After this module, you can compute in modular arithmetic and finite fields, explain the mathematics of RSA, Diffie-Hellman and elliptic-curve cryptography, and perform the corresponding computations by hand on small examples and by program on real sizes.

## Competences evaluated

1. Compute GCDs and modular inverses with the extended Euclidean algorithm.
2. Compute modular powers efficiently (square and multiply) and apply Fermat's little theorem and Euler's theorem.
3. Solve systems of congruences with the Chinese remainder theorem.
4. Explain and apply primality tests (Fermat, Miller-Rabin).
5. Define groups, rings and fields, and recognize them in examples (integers modulo n, polynomials).
6. Compute in prime fields GF(p), including inverses and square roots.
7. Compute in binary fields GF(2ⁿ) represented as polynomials modulo an irreducible polynomial (additions as XOR, multiplications with reduction), as in AES and GHASH.
8. Explain elliptic curves over finite fields: the group law, point addition and doubling, scalar multiplication (double and add, Montgomery ladder), in Weierstrass and Montgomery forms.
9. Explain the discrete logarithm problem and why it makes Diffie-Hellman secure, and the mathematics of RSA (key generation, encryption, signatures, why factoring matters).

## Notions, in learning order

1. **Divisibility revisited**: extended Euclid, Bézout's identity, modular inverses.
2. **Modular exponentiation**: square and multiply, Fermat and Euler theorems, Euler's totient.
3. **Chinese remainder theorem**: statement, construction, use in RSA.
4. **Primes**: distribution (informally), Fermat test, Miller-Rabin, generating large primes.
5. **Algebraic structures**: groups, subgroups, cyclic groups, generators, rings, fields.
6. **Prime fields**: arithmetic in GF(p), inverses, square roots.
7. **Binary fields**: polynomials over GF(2), irreducible polynomials, GF(2⁸) for AES, GF(2¹²⁸) for GHASH.
8. **Elliptic curves**: equations, group law, finite-field curves, scalar multiplication, constant-time ladders, Curve25519 and P-256.
9. **Hard problems**: discrete logarithm, factoring, their role in cryptography.
10. **RSA mathematics**: key generation, correctness proof, signatures.

## Practice

- Hand computations on small numbers: inverses, modular powers, CRT, a toy RSA with two-digit primes, point additions on a tiny curve.
- Once IN06 is validated: an implementation in Python, on its arbitrary-precision integers, of extended Euclid, Miller-Rabin, GF(2⁸) multiplication tables, and X25519 scalar multiplication checked against the published test vectors.

## Evaluation format

One written session, about 3 hours: around 15 exercises covering every competence, including one CRT system, one computation in GF(2⁸) and one elliptic-curve point addition by hand. Pass mark 100 %.

## References

- Victor Shoup, *A Computational Introduction to Number Theory and Algebra* (free book).
- Dan Boneh and Victor Shoup, *A Graduate Course in Applied Cryptography* (free book), mathematical background chapters.
- RFC 7748, *Elliptic Curves for Security* (free), for X25519 and its test vectors.
