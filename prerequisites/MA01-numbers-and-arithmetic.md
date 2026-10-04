# MA01. Numbers and arithmetic

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 1. Foundations | none | MA02, MA12, SY01 |

## Why this module

Everything in a language model is arithmetic: parameter counts in billions, training budgets written as powers of ten, memory sizes, ratios in every measurement. Integer division and remainders locate an element inside a tensor; divisibility and primes come back in hashing and cryptography. This module makes these operations exact and automatic, without a calculator.

## Objectives

After this module, you can compute exactly and mentally with integers, fractions, decimals, percentages and powers, estimate any quantity to the right order of magnitude, and reason about divisibility.

## Competences evaluated

1. Apply operator precedence and parentheses to evaluate any expression with the four operations, powers and roots.
2. Compute with negative integers (sign rules, absolute value as a distance).
3. Perform the Euclidean division of two integers, find the quotient and the remainder, and use them (for example to convert a flat index into row and column).
4. Decide divisibility with divisibility rules; list the divisors of an integer.
5. Decompose an integer into prime factors; compute a GCD and an LCM (from the decomposition and with Euclid's algorithm).
6. Simplify, compare, add, subtract, multiply and divide fractions; convert between fractions, decimals and percentages.
7. Compute percentages, percentage increases and decreases, successive changes and their combined effect, and relative error.
8. Apply the rules of integer powers (including zero and negative exponents) and of square roots; simplify expressions with them.
9. Write numbers in scientific notation, compute products and quotients in it, and convert between units and binary prefixes (kilo, mega, giga, kibi, mebi, gibi).
10. Estimate a result to its order of magnitude, round to a given precision, and judge whether a computed result is plausible.
11. Solve word problems that combine the previous competences (rates, proportions, budgets).

## Notions, in learning order

1. **Natural numbers and integers**: counting, the number line, positional decimal notation, negative numbers, sign rules, absolute value.
2. **The four operations and precedence**: properties (commutativity, associativity, distributivity), precedence of operations, parentheses, mental calculation strategies.
3. **Euclidean division**: quotient and remainder, the relation a = b × q + r with 0 ≤ r < b, the remainder of negative numbers (and why programming languages disagree on it).
4. **Divisibility**: divisors and multiples, divisibility rules (2, 3, 4, 5, 9, 10, 11), even and odd numbers.
5. **Prime numbers**: definition, the sieve of Eratosthenes, decomposition into prime factors and its uniqueness, the infinity of primes (the classic proof, read and explained).
6. **GCD and LCM**: from prime factors, Euclid's algorithm (why it works), coprime numbers, the relation GCD × LCM = a × b.
7. **Fractions**: meaning, equivalent fractions, simplification, common denominator, the four operations, mixed numbers, comparison.
8. **Decimals**: decimal notation, conversion between fractions and decimals, terminating and repeating decimals, operations.
9. **Ratios, proportions and percentages**: ratios, the rule of three, percentages of a quantity, increases and decreases, successive changes (why +10 % then −10 % is not zero), relative and absolute error.
10. **Integer powers**: definition, rules (product, quotient, power of a power, power of a product), zero and negative exponents, powers of two and of ten.
11. **Square roots**: definition, perfect squares, rules for products and quotients, simplifying √(a²b), irrational numbers (√2 is not a fraction: the proof).
12. **Scientific notation and units**: mantissa and exponent, operations in scientific notation, SI prefixes (kilo to exa, milli to nano), binary prefixes (kibi to tebi) and the difference between 10⁹ and 2³⁰.
13. **Rounding and estimation**: rounding to a number of decimals or significant figures, orders of magnitude, estimating before computing, sanity checks.

## Practice

- Daily mental calculation drills (operations, powers of two up to 2⁴⁰, fractions, percentages).
- Paper exercises on each notion, then mixed problems.
- Estimation problems in the spirit of the project: memory needed to store a given number of parameters in a given format, number of operations of a matrix product, time to process a dataset at a given rate.
- Once IN02 is validated: programs that implement Euclid's algorithm, the sieve of Eratosthenes, prime decomposition, conversions between bases and fraction arithmetic with exact integers.

## Evaluation format

One written session without a calculator, about 90 minutes: around 25 short exercises covering every competence, 3 word problems, and one proof to explain in your own words (Euclid's algorithm or the irrationality of √2). Pass mark 100 %.

## References

- OpenStax, *Prealgebra 2e* (free online textbook), chapters on whole numbers, integers, fractions, decimals and percents.
- Khan Academy, *Arithmetic* and *Pre-algebra* courses (free).
- Euclid's *Elements*, Book VII, propositions 1 and 2 (the original GCD algorithm), for curiosity.
