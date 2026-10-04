# ME03. Experimental method

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Method | 5. Applied mathematics | MA18, IN10, IN08 | the LLM plan (every experiment) |

## Why this module

Most of the LLM plan is experimentation: does this kernel make training faster, does this data filter improve the model, does this optimizer reach a lower loss. Measurements are noisy, runs differ by chance, and it is easy to fool oneself by choosing the cases where a change looks good. This module teaches how to run experiments whose conclusions can be trusted.

## Objectives

After this module, you can design an experiment that answers a precise question, control noise and bias, decide with statistics whether a difference is real, keep a reproducible experiment log, and present results with honest charts.

## Competences evaluated

1. Turn a vague idea into a testable hypothesis with a measurable outcome and a decision criterion fixed in advance.
2. Choose a baseline and design an ablation that changes one thing at a time.
3. Identify sources of noise (hardware load, randomness, ordering) and reduce or measure them (repetitions, idle machine, alternating rounds, deterministic counters).
4. Recognize selection bias (choosing test cases on the failures of the baseline, keeping the best of many tries) and design evaluations that avoid it.
5. Decide whether a difference is significant with the right test (paired comparisons, sign test, bootstrap), and correct for multiple comparisons.
6. Keep an experiment log that makes every result reproducible (code version, configuration, seed, machine state, raw outputs).
7. Present results with clear charts (hand-made SVG), error bars and honest axes, and write conclusions that do not overclaim.
8. Decide when to stop an experiment that leads nowhere, based on the measurements.

## Notions, in learning order

1. **Questions and hypotheses**: from ideas to testable claims, success criteria decided before measuring.
2. **Design**: baselines, controls, ablations, one variable at a time.
3. **Noise**: sources of variance, repeated measurements, deterministic proxies (counters instead of time).
4. **Bias**: selection bias, survivorship bias, the garden of forking paths, held-out data.
5. **Statistics for experiments**: paired designs, sign test, bootstrap confidence intervals, effect sizes, multiple comparisons.
6. **Reproducibility**: logging everything needed to rerun, versioning, seeds, environment.
7. **Presentation**: chart types, error bars, axes and scales, honest wording.
8. **Stopping rules**: deciding in advance, abandoning dead ends early with numbers to back it.

## Practice

- Redesigning a flawed experiment description (missing baseline, biased test set, no repetition).
- A complete small experiment, for example comparing two implementations of the same function: hypothesis, protocol, measurements, statistical test, SVG chart, conclusion, logged so that it can be rerun.

## Evaluation format

One session, about 2 hours: critique of experiment reports never seen before, design of a protocol for a given question, and analysis of raw measurements (test, chart, conclusion). Pass mark 100 %.

## References

- The NeurIPS paper checklist, sections on reproducibility and statistical significance (free).
- Bradley Efron and Robert J. Tibshirani, *An Introduction to the Bootstrap* (book, not free).
- Andrew Gelman and Eric Loken, *The garden of forking paths* (2013, free article).
