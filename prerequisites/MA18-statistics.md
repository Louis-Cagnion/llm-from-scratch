# MA18. Statistics

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 4. Multivariable mathematics, statistics and systems | MA17 | MA21, MA25, ME02, ME03 |

## Why this module

Training a language model is maximum likelihood estimation: the cross-entropy loss is the negative log-likelihood of real text. Weight decay is a prior in disguise, the Unigram tokenizer is trained with the EM algorithm, variational autoencoders maximize an evidence lower bound, and every claim that one model beats another needs a statistical test. This module turns probability into inference from data.

## Objectives

After this module, you can build and analyze estimators, derive maximum likelihood and MAP estimators, fit latent-variable models with EM, quantify uncertainty with confidence intervals and the bootstrap, and test hypotheses correctly.

## Competences evaluated

1. Compute the bias, variance and mean squared error of an estimator.
2. Derive maximum likelihood estimators for the usual distributions, and show that minimizing cross-entropy is maximizing likelihood.
3. Derive MAP estimators and explain L2 regularization as a Gaussian prior and L1 as a Laplace prior.
4. Compute the Fisher information of simple models and explain what it measures.
5. Derive and apply the EM algorithm on a mixture of Gaussians, and explain k-means as its hard version.
6. Write the evidence lower bound (ELBO) of a latent-variable model and explain variational inference.
7. Build confidence intervals (normal approximation, bootstrap).
8. Run and interpret hypothesis tests: one- and two-sample tests, paired tests, the sign test, chi-square goodness-of-fit, p-values, and the correction for multiple comparisons.
9. Fit a linear regression by least squares (normal equations) and evaluate it.
10. Explain overfitting and the bias-variance trade-off, and why validation and test sets are separate.

## Notions, in learning order

1. **Samples and estimators**: statistics, sampling distributions, bias, variance, MSE, consistency.
2. **Maximum likelihood**: likelihood, log-likelihood, derivations for Bernoulli, categorical, normal, link with cross-entropy.
3. **Bayesian estimation**: priors, posteriors, MAP, regularization as priors.
4. **Fisher information**: definition, Cramér-Rao bound (statement), natural gradient (first look).
5. **Latent variables and EM**: mixture models, E and M steps, convergence, k-means.
6. **Variational inference**: the evidence lower bound derived with Jensen's inequality (its reading as a KL divergence comes in MA19).
7. **Uncertainty**: standard errors, confidence intervals, the bootstrap.
8. **Hypothesis testing**: null and alternative hypotheses, p-values, errors of type I and II, paired tests, sign test, chi-square tests, multiple comparisons.
9. **Linear regression**: least squares, normal equations, geometric view (projection from MA14), residuals.
10. **Generalization**: overfitting, bias-variance trade-off, train, validation and test splits, cross-validation.

## Practice

- Deriving estimators by hand for each distribution.
- Re-analyzing the measurements of an experiment (for example two solvers or two training runs) with paired tests and the bootstrap.
- Once IN04 is validated: EM for a two-component Gaussian mixture and k-means implemented from scratch on generated data, a bootstrap tool, and a chi-square test used to check a random generator.

## Evaluation format

One written session, about 3 hours: around 15 exercises covering every competence, including one derivation of an estimator, one EM step by hand and one test to run and interpret. Pass mark 100 %.

## References

- Larry Wasserman, *All of Statistics* (book, not free).
- OpenStax, *Introductory Statistics* (free), for confidence intervals and tests.
- Christopher M. Bishop, *Pattern Recognition and Machine Learning* (free PDF from Microsoft Research), chapters 1, 2 and 9.
