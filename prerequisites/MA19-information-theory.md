# MA19. Information theory

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA05, MA12, MA17 | none directly (used throughout the LLM plan) |

## Why this module

The training loss of a language model is a cross-entropy, its quality is reported as perplexity or bits per byte, preference optimization keeps the model close to a reference with a KL divergence, and distillation minimizes a KL divergence to a teacher. A model that predicts well is a model that compresses well: information theory explains why.

## Objectives

After this module, you can compute and interpret entropy, cross-entropy, KL divergence and mutual information, relate them to the losses and metrics of language models, and explain the equivalence between prediction and compression.

## Competences evaluated

1. Compute the information content of an event and the entropy of a discrete distribution, in bits and in nats.
2. Compute joint and conditional entropies and apply the chain rule of entropy.
3. Compute cross-entropy and KL divergence, prove that the KL divergence is non-negative (Gibbs' inequality, with Jensen), and explain its asymmetry with examples (forward versus reverse KL).
4. Relate the training loss of a language model to cross-entropy, and convert between loss, perplexity and bits per byte (including across tokenizers).
5. Compute mutual information and interpret it.
6. Build a Huffman code and compute its average length against the entropy (source coding theorem, statement).
7. Explain arithmetic coding and why a predictive model plus an arithmetic coder is a compressor, and decode a short message by hand.
8. Explain entropy coders used in compression formats (the idea of finite-state entropy coding).
9. Explain the maximum entropy principle and derive the softmax (Gibbs) distribution from it.

## Notions, in learning order

1. **Information content**: surprise, logarithms, bits and nats.
2. **Entropy**: definition, properties, maximum for the uniform distribution.
3. **Several variables**: joint and conditional entropy, chain rule.
4. **Cross-entropy and KL divergence**: definitions, Gibbs' inequality, asymmetry, mode seeking versus mean seeking.
5. **Language modeling metrics**: cross-entropy loss, perplexity, bits per byte, comparing models with different tokenizers.
6. **Mutual information**: definition, interpretations, link with KL.
7. **Source coding**: prefix codes, Kraft inequality, Huffman coding, the source coding theorem.
8. **Arithmetic coding**: interval subdivision, model-driven coding, prediction equals compression.
9. **Practical entropy coders**: range coding and finite-state entropy (ANS) at the level of ideas.
10. **Maximum entropy**: principle, derivation of the Gibbs distribution, temperature.

## Practice

- Entropy and KL computations by hand on small distributions, including forward and reverse KL between two given distributions.
- Converting published results between loss, perplexity and bits per byte.
- Once IN07 is validated: a Huffman compressor (from IN07) measured against the entropy of the text, and an arithmetic coder driven by a character-frequency model, compared with Huffman.

## Evaluation format

One written session, about 2 hours: around 12 exercises covering every competence, including the proof of Gibbs' inequality and one arithmetic decoding by hand. Pass mark 100 %.

## References

- David J. C. MacKay, *Information Theory, Inference, and Learning Algorithms* (free book), chapters 1 to 6.
- Thomas M. Cover and Joy A. Thomas, *Elements of Information Theory* (book, not free).
