# MA23. Ordinary and stochastic differential equations

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA10, MA11, MA14, MA17 | none directly (used by L30, L65) |

## Why this module

State-space models such as Mamba start from a continuous linear differential equation that is then discretized; diffusion models add noise through a stochastic differential equation and generate images by running it backward, and their fast samplers are numerical solvers of an equivalent ordinary differential equation. This module gives the continuous-time mathematics behind both.

## Objectives

After this module, you can solve linear differential equations and systems, compute matrix exponentials, discretize continuous systems, and work with Brownian motion and stochastic differential equations at the level needed for diffusion models.

## Competences evaluated

1. Solve first-order linear differential equations (homogeneous and with a source term).
2. Solve linear systems x' = Ax with constant coefficients through diagonalization and the matrix exponential.
3. Decide the stability of a linear system from its eigenvalues.
4. Discretize a continuous system with Euler's method and with the zero-order hold, and compare their accuracy and stability.
5. Write a continuous-time linear state-space model (A, B, C, D), discretize it, and run it as a recurrence and as a convolution.
6. Simulate a random walk and explain Brownian motion and its properties (independent Gaussian increments, variance growing linearly with time).
7. Write a stochastic differential equation, simulate it with the Euler-Maruyama scheme, and recognize the Ornstein-Uhlenbeck process.
8. Explain the Fokker-Planck equation at the level of intuition (how a density evolves) and the score function ∇ log p.
9. Explain the probability-flow ordinary differential equation and why deterministic samplers can replace stochastic ones in diffusion models.

## Notions, in learning order

1. **Differential equations**: definitions, initial value problems, existence and uniqueness (statement).
2. **First-order linear equations**: integrating factor, exponential solutions.
3. **Linear systems**: matrix form, eigenvalue method, the matrix exponential, stability.
4. **Numerical solution**: Euler, Heun and Runge-Kutta methods (first look), error and stability.
5. **Discretization of linear systems**: zero-order hold, bilinear transform (first look).
6. **State-space models**: continuous form, discrete recurrence, equivalent convolution kernel (link with MA22).
7. **Randomness in time**: random walks, Brownian motion and its properties.
8. **Stochastic differential equations**: drift and diffusion terms, Euler-Maruyama, the Ornstein-Uhlenbeck process.
9. **Densities in time**: Fokker-Planck intuition, score functions.
10. **From stochastic to deterministic**: the probability-flow ODE, the reverse-time SDE (statement), link with diffusion samplers.

## Practice

- Solving linear equations and 2 × 2 systems by hand, including one with complex eigenvalues (oscillations).
- Discretizing a small state-space model by hand with both methods.
- Once IN06 is validated: simulations of a discretized state-space model (recurrence versus convolution give the same output), Brownian paths, and an Ornstein-Uhlenbeck process with Euler-Maruyama whose empirical distribution is compared with the theory.

## Evaluation format

One written session, about 2 hours 30: around 12 exercises covering every competence, including one matrix exponential and one discretization. Pass mark 100 %.

## References

- MIT OpenCourseWare, *18.03 Differential Equations* (free).
- Bernt Øksendal, *Stochastic Differential Equations* (book, not free), first chapters.
- Yang Song et al., *Score-Based Generative Modeling through Stochastic Differential Equations* (2021, free paper), sections 1 to 4.
- Albert Gu and Tri Dao, *Mamba: Linear-Time Sequence Modeling with Selective State Spaces* (2023, free paper), section 2.
