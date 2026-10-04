# MA25. Reinforcement learning foundations

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 6. Advanced computer science and GPU | MA17, MA18, MA20 | none directly (used by L54 to L58) |

## Why this module

RLHF, PPO, GRPO, reasoning models trained with verifiable rewards and agentic training are all reinforcement learning: a policy (the model) takes actions (tokens), receives rewards, and is improved with policy gradients, value functions and advantages. Without these foundations, the post-training part of the LLM plan would be formulas without meaning.

## Objectives

After this module, you can model a problem as a Markov decision process, compute and estimate value functions, derive the policy gradient theorem, and explain the actor-critic methods, advantages and KL-regularized objectives used to train language models.

## Competences evaluated

1. Solve a multi-armed bandit problem with ε-greedy, upper confidence bounds and Thompson sampling, and explain the exploration-exploitation trade-off.
2. Model a problem as a Markov decision process (states, actions, transitions, rewards, discount) and compute returns.
3. Write the Bellman equations for state and action values, and solve small problems by value iteration and policy iteration.
4. Estimate values from experience with Monte Carlo and temporal-difference methods (TD(0), TD(λ)), and compare their bias and variance.
5. Derive the policy gradient theorem and the REINFORCE estimator, and explain why it has high variance.
6. Reduce variance with baselines and advantages, and derive generalized advantage estimation.
7. Explain actor-critic methods and the role of the value function.
8. Explain off-policy learning with importance weights, and why clipping (as in PPO) keeps updates safe.
9. Write a KL-regularized objective (reward minus β times KL to a reference policy) and derive its optimal policy in closed form (the basis of DPO).
10. Map the vocabulary to language models: the model as policy, tokens as actions, a completed answer as an episode, the reward model or the verifier as the reward.

## Notions, in learning order

1. **The reinforcement learning problem**: agent, environment, reward, the difference with supervised learning.
2. **Bandits**: regret, ε-greedy, UCB, Thompson sampling.
3. **Markov decision processes**: definition, policies, returns, discounting, episodes.
4. **Value functions and Bellman equations**: state and action values, optimality equations.
5. **Dynamic programming**: policy evaluation, value iteration, policy iteration.
6. **Learning from experience**: Monte Carlo estimation, temporal-difference learning, TD(λ), Q-learning (first look).
7. **Policy gradients**: the policy gradient theorem, REINFORCE, baselines.
8. **Advantages and actor-critic**: advantage function, generalized advantage estimation, critics.
9. **Off-policy corrections**: importance sampling (from MA17), clipped objectives.
10. **Regularized objectives**: entropy bonuses, KL penalties, the closed-form optimal policy.
11. **Language models as policies**: tokens, episodes, rewards, the setting of RLHF and reasoning training.

## Practice

- Solving small grid worlds by hand with value iteration.
- Deriving the policy gradient theorem and GAE on paper.
- Once IN06 is validated: bandit algorithms compared on simulated arms, value and policy iteration on a grid world, and REINFORCE with and without a baseline on a tiny environment, with learning curves as SVG.

## Evaluation format

One written session, about 3 hours: around 12 exercises covering every competence, including the derivation of the policy gradient theorem and of the optimal policy of a KL-regularized objective. Pass mark 100 %.

## References

- Richard S. Sutton and Andrew G. Barto, *Reinforcement Learning: An Introduction*, second edition (free book).
- OpenAI, *Spinning Up in Deep RL* (free documentation), introduction and policy gradient sections.
- John Schulman et al., *High-Dimensional Continuous Control Using Generalized Advantage Estimation* (2015, free paper).
