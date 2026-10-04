# MA17. Continuous probability and limit theorems

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 4. Multivariable mathematics, statistics and systems | MA11, MA15, MA12 | MA18, MA19, MA23, MA25 |

## Why this module

Weights are initialized from normal distributions, noise drives diffusion models, the exact GELU uses the normal cumulative distribution, evaluations average over random samples, and PPO corrects for sampling from an old policy with importance weights. This module extends probability to continuous quantities and explains why averages of many random terms behave predictably.

## Objectives

After this module, you can work with continuous random variables and random vectors, use the normal distribution fluently, apply the law of large numbers and the central limit theorem, and generate random samples from a uniform source.

## Competences evaluated

1. Use density and cumulative distribution functions; compute probabilities, expectations and variances of continuous random variables.
2. Know the uniform, exponential and normal distributions; standardize a normal variable and use Φ, including in the exact GELU and its derivative.
3. Compute joint, marginal and conditional densities, covariance and correlation; decide independence.
4. Work with Gaussian vectors: mean vector, covariance matrix, linear transformations, and the variance of a sum of many terms (the basis of initialization scaling).
5. Find the distribution of a function of a random variable (change of variables).
6. Apply Markov's, Chebyshev's and Hoeffding's inequalities to bound probabilities and sample sizes.
7. State and apply the law of large numbers and the central limit theorem, and explain their limits.
8. Generate samples by inverse transform, Box-Muller and rejection sampling.
9. Describe Markov chains (transition matrix, stationary distribution) and hidden Markov models.
10. Estimate an expectation by Monte Carlo, give its error, and use importance sampling with its weights.

## Notions, in learning order

1. **Continuous random variables**: densities, cumulative distributions, expectation, variance.
2. **Usual distributions**: uniform, exponential, normal, standardization, Φ and erf.
3. **Random vectors**: joint and marginal densities, conditional densities, independence, covariance matrices.
4. **Gaussian vectors**: definition, linear maps of Gaussians, sums of independent variables, variance propagation through a linear layer.
5. **Transformations**: distribution of g(X), change of variables in several dimensions.
6. **Inequalities**: Markov, Chebyshev, Hoeffding.
7. **Limit theorems**: law of large numbers, central limit theorem, convergence in distribution (informally).
8. **Simulation**: inverse transform, Box-Muller, rejection sampling.
9. **Markov chains**: transitions, stationary distributions, ergodicity (informally), hidden Markov models.
10. **Monte Carlo**: estimators, error decreasing as 1/√n, importance sampling and its variance.

## Practice

- Computation exercises by hand on densities and Gaussian vectors.
- Deriving why weights initialized with variance 1/n keep activations at unit variance through a linear layer.
- Once IN04 is validated: a sampler library built on a uniform generator (inverse transform, Box-Muller, rejection), histograms compared with densities, and a Monte Carlo experiment showing the 1/√n error and the effect of importance sampling.

## Evaluation format

One written session, about 2 hours 30: around 15 exercises covering every competence and one simulation result to interpret. Pass mark 100 %.

## References

- Joseph K. Blitzstein and Jessica Hwang, *Introduction to Probability* (free online book), chapters on continuous distributions, joint distributions, inequalities and limit theorems.
- Harvard *Stat 110* lectures (free).
