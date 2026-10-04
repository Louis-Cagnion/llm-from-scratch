# MA05. Exponential and logarithm

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 2. Core mathematics and programming | MA04 | MA06, MA07, MA19 |

## Why this module

The exponential and the logarithm are everywhere in a language model: softmax turns scores into probabilities with exponentials, the training loss is a logarithm of a probability, perplexity is an exponential of that loss, sigmoid and tanh are built from exponentials, and scaling laws are straight lines on log-log axes. Computing with them fluently is essential.

## Objectives

After this module, you can manipulate exponentials and logarithms in any base, solve equations with them, read logarithmic plots, and know the sigmoid, tanh and softplus functions.

## Competences evaluated

1. Apply the rules of real powers and of the exponential (product, quotient, power).
2. Apply the rules of logarithms (product, quotient, power, change of base) in bases e, 2 and 10.
3. Solve exponential and logarithmic equations and inequalities.
4. Convert between exponential growth or decay and its parameters (rate, half-life, doubling time).
5. Compare the growth of logarithms, powers and exponentials, and order expressions by growth for large values.
6. Read and use logarithmic and log-log scales; recognize that a power law is a straight line in log-log coordinates and extract its exponent.
7. Know the definitions, graphs and main properties of sigmoid, tanh and softplus, and the relations between them (tanh(x) = 2σ(2x) − 1).
8. Compute with logarithms of probabilities: turn a product of probabilities into a sum of logarithms, and explain why this avoids underflow.

## Notions, in learning order

1. **Real powers**: from integer to rational to real exponents, rules.
2. **The exponential function**: the number e (as the limit of compound interest, intuitively), graph, properties, exponential growth and decay.
3. **The natural logarithm**: inverse of the exponential, graph, rules, domain.
4. **Other bases**: log₂ (bits), log₁₀ (orders of magnitude), change of base.
5. **Equations and inequalities**: exponential and logarithmic equations, monotonicity arguments.
6. **Comparative growth**: log x ≪ x^a ≪ e^x for large x, informally.
7. **Logarithmic scales**: semi-log and log-log plots, power laws, reading slopes.
8. **Sigmoid, tanh and softplus**: definitions, graphs, symmetries, limits, relations.
9. **Log-probabilities**: products of many small numbers, sums of logarithms, the log-sum-exp form (first look).

## Practice

- Rule drills, equation solving, and estimation of logarithms without a calculator (log₂ of powers of two, log₁₀ of powers of ten).
- Reading real log-log plots (for example scaling-law figures from papers) and extracting the slope.
- Once IN02 is validated: plotting exp, log, sigmoid, tanh and softplus with the MA04 ASCII plotter; multiplying 1000 small probabilities directly and through logarithms to see underflow happen.

## Evaluation format

One written session without a calculator, about 1 hour 30: around 15 exercises covering every competence and one log-log figure to interpret. Pass mark 100 %.

## References

- OpenStax, *Precalculus 2e*, chapter on exponential and logarithmic functions (free).
- Khan Academy, *Exponential and logarithmic functions* (free).
