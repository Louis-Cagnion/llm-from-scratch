# Prerequisites plan

**Summary.** Everything needed before building a language model by hand, starting from zero: mathematics, programming, systems and research method. 49 modules in four tracks, followed in seven stages from the most fundamental to the least; each module is validated by its own evaluation, and a final evaluation covers them all ([evaluation rules](../README.md#evaluations)).

## Contents

1. [How to follow this plan](#how-to-follow-this-plan)
2. [Track MA: mathematics](#track-ma-mathematics)
3. [Track IN: programming](#track-in-programming)
4. [Track SY: systems and performance](#track-sy-systems-and-performance)
5. [Track ME: method](#track-me-method)
6. [Final evaluation](#final-evaluation)

## How to follow this plan

- Modules are identified by track and number (`MA07`); each one lists the modules it depends on. A module can start once its dependencies are validated, so the mathematics and programming tracks progress in parallel.
- Each module starts by offering its evaluation directly; passing it validates the module without following it.
- Each module has its own file with objectives, the competences its evaluation tests, notions, practice programs and references; each title below links to it.
- Recommended sequence, from the most fundamental to the least: seven stages, each one using only what the previous ones taught; inside a stage, modules are listed in their order of dependency.

1. **Foundations**: MA01, MA02, MA03, IN01, IN02, ME01.
2. **Core mathematics and programming**: MA04, MA05, MA06, MA07, MA08, IN03, IN04, IN05.
3. **Analysis, probability and algorithms**: MA09, MA10, MA11, MA12, MA13, IN06, IN07, IN08, SY01.
4. **Multivariable mathematics, statistics and systems**: MA14, MA15, MA16, MA17, MA18, IN09, IN10, SY02, ME02.
5. **Applied mathematics**: MA19, MA20, MA21, MA22, MA23, MA24, ME03.
6. **Advanced computer science and GPU**: MA25, MA26, IN11, IN12, IN13, SY03, SY04.
7. **Cryptography, security and cloud**: IN14, IN15, SY05.

## Track MA: mathematics

- **[MA01. Numbers and arithmetic](MA01-numbers-and-arithmetic.md)** (depends on: none): integers, fractions, percentages, powers, primes and orders of magnitude.
- **[MA02. Elementary algebra](MA02-elementary-algebra.md)** (MA01): expressions, equations, inequalities and small linear systems.
- **[MA03. Logic, sets and proofs](MA03-logic-sets-and-proofs.md)** (MA02): logic, sets, sums, functions between sets and the main proof techniques.
- **[MA04. Real functions](MA04-real-functions.md)** (MA02, MA03): the usual functions, their graphs, compositions and inverses.
- **[MA05. Exponential and logarithm](MA05-exponential-and-logarithm.md)** (MA04): exp, log, log-log plots, sigmoid and tanh.
- **[MA06. Trigonometry and complex numbers](MA06-trigonometry-and-complex-numbers.md)** (MA04, MA05): angles, sines and cosines, complex numbers as rotations.
- **[MA07. Sequences and series](MA07-sequences-and-series.md)** (MA03, MA05): limits of sequences, series, moving averages and Taylor series.
- **[MA08. Linear algebra I](MA08-linear-algebra-i.md)** (MA02, MA03): vectors, matrices, dot products, Gaussian elimination, determinants.
- **[MA09. Limits and continuity](MA09-limits-and-continuity.md)** (MA07): limits of functions, continuity and asymptotic notation.
- **[MA10. Differentiation](MA10-differentiation.md)** (MA06, MA09): derivatives, the chain rule (heart of backpropagation), Taylor expansions, Newton's method.
- **[MA11. Integration](MA11-integration.md)** (MA10): integrals, improper integrals, the Gaussian integral, numerical integration.
- **[MA12. Discrete probability](MA12-discrete-probability.md)** (MA01, MA03, MA07): counting, conditional probability, Bayes, discrete distributions.
- **[MA13. Discrete mathematics and graphs](MA13-discrete-mathematics-and-graphs.md)** (MA03, MA12): recurrences, graphs, topological sort, complexity, hashing.
- **[MA14. Linear algebra II](MA14-linear-algebra-ii.md)** (MA08): vector spaces, eigenvalues, the SVD and low-rank approximation, tensors and einsum.
- **[MA15. Multivariable calculus](MA15-multivariable-calculus.md)** (MA10, MA11, MA08): gradients, Jacobians, Hessians, extrema and Lagrange multipliers.
- **[MA16. Matrix calculus](MA16-matrix-calculus.md)** (MA14, MA15): gradients of matrix expressions: linear layers, softmax, normalization, attention.
- **[MA17. Continuous probability and limit theorems](MA17-continuous-probability-and-limit-theorems.md)** (MA11, MA15, MA12): densities, Gaussian vectors, limit theorems, sampling, Monte Carlo.
- **[MA18. Statistics](MA18-statistics.md)** (MA17): maximum likelihood, MAP, EM, the ELBO, confidence intervals and tests.
- **[MA19. Information theory](MA19-information-theory.md)** (MA05, MA12, MA17): entropy, cross-entropy, KL divergence, perplexity, compression.
- **[MA20. Optimization](MA20-optimization.md)** (MA15, MA16): gradient descent, momentum, Adam, quasi-Newton methods, constraints.
- **[MA21. Numerical analysis and floating point](MA21-numerical-analysis-and-floating-point.md)** (MA07, MA10, MA18): IEEE 754 and low-precision formats, stability, function evaluation, random generators.
- **[MA22. Signal processing](MA22-signal-processing.md)** (MA06, MA07, MA11, MA08): Fourier transforms, the DCT, convolutions, sampling and aliasing.
- **[MA23. Ordinary and stochastic differential equations](MA23-ordinary-and-stochastic-differential-equations.md)** (MA10, MA11, MA14, MA17): linear differential equations, state-space models, stochastic differential equations.
- **[MA24. Numerical linear algebra](MA24-numerical-linear-algebra.md)** (MA14, MA21): LU, Cholesky, eigenvalue algorithms, SVD, Newton-Schulz, PCA.
- **[MA25. Reinforcement learning foundations](MA25-reinforcement-learning-foundations.md)** (MA17, MA18, MA20): bandits, MDPs, Bellman equations, policy gradients, advantages, KL-regularized objectives.
- **[MA26. Number theory, finite fields and elliptic curves](MA26-number-theory-finite-fields-and-elliptic-curves.md)** (MA13, MA14): modular arithmetic, finite fields and elliptic curves behind TLS.

## Track IN: programming

- **[IN01. Linux and the terminal](IN01-linux-and-the-terminal.md)** (none): files, pipes, scripts, processes, resources and SSH.
- **[IN02. Python I](IN02-python-i.md)** (IN01): the core language: types, control flow, functions, collections, files, exceptions.
- **[IN03. Git](IN03-git.md)** (IN01): commits, history, branches, conflicts, remotes and hooks.
- **[IN04. Python II](IN04-python-ii.md)** (IN02): classes, operator overloading, generators, decorators, context managers.
- **[IN05. C I](IN05-c-i.md)** (IN01): pointers, arrays, strings, structures, dynamic memory, multi-file programs.
- **[IN06. Python III](IN06-python-iii.md)** (IN04): memory model, binary data, mmap, concurrency, profiling.
- **[IN07. Algorithms and data structures](IN07-algorithms-and-data-structures.md)** (IN04, MA12, MA13): hash tables, heaps, tries, graphs, sorting, dynamic programming, greedy algorithms.
- **[IN08. The client side of the web](IN08-the-client-side-of-the-web.md)** (IN02): HTML, CSS, JavaScript, streamed requests and SVG charts.
- **[IN09. C II](IN09-c-ii.md)** (IN05, SY01): strides, undefined behavior, sanitizers, ctypes, threads, atomics, SIMD.
- **[IN10. Testing, debugging and code quality](IN10-testing-debugging-and-code-quality.md)** (IN04, IN05): unit, property-based and numerical tests, debugging method, code review.
- **[IN11. Networking and the server side of the web](IN11-networking-and-the-server-side-of-the-web.md)** (IN06): TCP, HTTP/1.1 written by hand, streaming, uploads, JSON-RPC.
- **[IN12. Formal languages and parsing](IN12-formal-languages-and-parsing.md)** (IN07, MA13): automata, regular expressions, grammars, parsers for JSON, Markdown and templates.
- **[IN13. Compilers](IN13-compilers.md)** (IN12, IN09): ASTs, intermediate representations, SSA, optimizations, code generation.
- **[IN14. Cryptography and TLS](IN14-cryptography-and-tls.md)** (MA26, IN09, IN12): SHA, HMAC, AES-GCM, X25519, signatures, X.509 and the TLS 1.3 protocol.
- **[IN15. Application security](IN15-application-security.md)** (IN11, IN08, IN14, SY02): injections, XSS, browser isolation, authentication, secrets, sandboxing.

## Track SY: systems and performance

- **[SY01. Computer architecture](SY01-computer-architecture.md)** (MA01, IN05): number representation, caches, SIMD, arithmetic intensity and the roofline model.
- **[SY02. Operating systems](SY02-operating-systems.md)** (IN05, SY01): processes, virtual memory and mmap, IPC, synchronization, resource limits.
- **[SY03. GPU architecture and CUDA](SY03-gpu-architecture-and-cuda.md)** (IN09, SY01, SY02): the CUDA execution model, memory hierarchy, tensor cores, profiling.
- **[SY04. Parallel and distributed computing](SY04-parallel-and-distributed-computing.md)** (SY02, IN11): speedups, collective operations, the α-β cost model, interconnects, fault tolerance.
- **[SY05. The cloud](SY05-the-cloud.md)** (IN01, SY04): cloud building blocks, pricing, cost of a run, security, cost control.

## Track ME: method

- **[ME01. Technical English and reading papers](ME01-technical-english-and-reading-papers.md)** (none): technical vocabulary, documentation, and a method to read research papers.
- **[ME02. Machine learning concepts](ME02-machine-learning-concepts.md)** (MA18): kinds of learning, generalization, losses and metrics, history up to LLMs.
- **[ME03. Experimental method](ME03-experimental-method.md)** (MA18, IN10, IN08): hypotheses, baselines, noise, bias, significance, reproducibility.

## Final evaluation

Taken once all 49 modules are validated.

- **Sessions**: one per track, several for mathematics.
- **Coverage**: every competence of every module is tested at least once, with exercises never seen before (neither in learning nor in a module evaluation): calculations and proofs, programs in Python, C and CUDA, explanations.
- **Pass mark**: 100 % in each session. A failed session is retaken alone, with new exercises, after a review of the modules concerned.
- **Success**: the final evaluation is passed when every session is.
