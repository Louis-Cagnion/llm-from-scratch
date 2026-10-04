# ME02. Machine learning concepts

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Method | 4. Multivariable mathematics, statistics and systems | MA18 | the LLM plan (Part II onward) |

## Why this module

Before building models by hand, the vocabulary and the logic of machine learning must be clear: what learning from data means, why a model can memorize instead of generalizing, how to measure progress honestly, and where large language models come from. This module is conceptual; the LLM plan turns each concept into code.

## Objectives

After this module, you can explain the main kinds of machine learning, the full workflow of a learning problem, the causes of overfitting and underfitting, and the history that leads to today's large language models.

## Competences evaluated

1. Distinguish supervised, unsupervised, self-supervised and reinforcement learning, and classify a task into one of them (next-token prediction included).
2. Describe the workflow of a learning problem: data, model, loss, optimization, evaluation.
3. Explain the roles of training, validation and test sets, and the dangers of leakage and contamination.
4. Explain generalization, overfitting and underfitting, and the levers against overfitting (more data, regularization, early stopping).
5. Choose a loss and a metric for a task, and explain why they can differ (cross-entropy versus accuracy, perplexity versus human preference).
6. Explain parameters versus hyperparameters, and how hyperparameters are tuned without touching the test set.
7. Describe the main families of models (linear models, trees, neural networks, Transformers) and what each is good at.
8. Summarize the history of artificial intelligence up to large language models (symbolic AI, neural networks, deep learning, Transformers, scaling, instruction tuning and RLHF).
9. Explain at a high level how a modern chat assistant is built: pre-training, fine-tuning, alignment, serving.

## Notions, in learning order

1. **What learning is**: learning from examples, generalization as the goal.
2. **Kinds of learning**: supervised, unsupervised, self-supervised, reinforcement.
3. **The workflow**: data collection, features or representations, model, loss, optimization, evaluation, deployment.
4. **Data splits**: training, validation, test, cross-validation, leakage, contamination.
5. **Generalization**: underfitting, overfitting, capacity, regularization, early stopping, double descent (first look).
6. **Losses and metrics**: regression and classification losses, accuracy, precision and recall, perplexity, human evaluation.
7. **Hyperparameters**: what they are, search strategies, the validation set's role.
8. **Model families**: overview and typical uses.
9. **History**: from the perceptron to Transformers, the scaling era, chat assistants.
10. **Anatomy of a chat assistant**: pre-training, supervised fine-tuning, preference optimization, inference and harness (the map of the LLM plan).

## Practice

- Classifying a list of tasks by kind of learning, loss and metric.
- Reading the introductions of a few landmark papers (perceptron, backpropagation, AlexNet, Transformer, GPT-3, InstructGPT) and placing them on a timeline.
- Explaining the LLM plan's map in your own words, module group by module group.

## Evaluation format

One written session, about 1 hour 30: concept questions, scenario analyses (spot the leakage, pick the metric, diagnose overfitting from curves), and a short essay on how a chat assistant is built. Pass mark 100 %.

## References

- Andrew Ng, *Machine Learning Yearning* (free book).
- Aurélien Géron, *Hands-On Machine Learning*, part I (book, not free), for concepts only.
- Stanford *CS229* lecture notes (free).
