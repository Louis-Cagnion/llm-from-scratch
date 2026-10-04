# MA12. Discrete probability

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 3. Analysis, probability and algorithms | MA01, MA03, MA07 | IN07, MA13, MA17, MA19 |

## Why this module

A language model is a probability distribution over the next token: a categorical distribution computed by softmax, sampled with temperature, top-k or top-p, and trained by maximizing the probability of real text. Probability is the language in which the model, its training and its evaluation are all expressed.

## Objectives

After this module, you can count outcomes, compute probabilities with conditioning and Bayes' rule, and work with discrete random variables, their expectation and variance, and the usual discrete distributions.

## Competences evaluated

1. Count with the product rule, permutations, arrangements and combinations, and apply the binomial theorem.
2. Model a random experiment: sample space, events, probability axioms, equally likely outcomes.
3. Compute probabilities of unions, intersections and complements (inclusion-exclusion for two or three events).
4. Compute conditional probabilities, use the law of total probability and Bayes' rule.
5. Decide whether events and random variables are independent.
6. Describe a discrete random variable by its distribution, compute its expectation and variance, and use linearity of expectation (including for non-independent variables).
7. Know the Bernoulli, binomial, geometric, Poisson, categorical and multinomial distributions: their meaning, probabilities, expectation and variance.
8. Compute the expectation of a function of a random variable, and the variance of a sum of independent variables.
9. Sample from a categorical distribution by hand from a uniform number (the cumulative method), and explain temperature as a change of the distribution.

## Notions, in learning order

1. **Counting**: product rule, permutations, arrangements, combinations, Pascal's triangle, binomial theorem.
2. **Probability spaces**: experiments, sample space, events, axioms, uniform probability.
3. **Rules**: complement, union, inclusion-exclusion.
4. **Conditioning**: conditional probability, multiplication rule, total probability, Bayes' rule (with the classic medical test example).
5. **Independence**: of events, of several events, pairwise versus mutual independence.
6. **Discrete random variables**: distribution, cumulative distribution, expectation, variance, standard deviation, linearity, functions of random variables.
7. **Usual distributions**: Bernoulli, binomial, geometric, Poisson (as a limit of binomials), categorical, multinomial.
8. **Several variables**: joint distribution of discrete variables, marginals, independence, covariance (first look), variance of sums.
9. **Sampling and temperature**: sampling a categorical distribution, effect of dividing logits by a temperature (first look, using MA05).

## Practice

- Counting and probability problems by hand, with simulations to check intuition.
- Bayes exercises written as tables of counts.
- Once IN02 is validated: a simulator of experiments (dice, cards, coins) that compares empirical frequencies with exact probabilities, and a categorical sampler with temperature applied to a small vocabulary.

## Evaluation format

One written session without a calculator, about 2 hours: around 15 exercises covering every competence and 2 modeling problems. Pass mark 100 %.

## References

- Joseph K. Blitzstein and Jessica Hwang, *Introduction to Probability* (free online book) and Harvard *Stat 110* lectures (free).
- OpenStax, *Introductory Statistics*, chapters on probability (free).
