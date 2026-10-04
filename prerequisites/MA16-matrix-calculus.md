# MA16. Matrix calculus

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 4. Multivariable mathematics, statistics and systems | MA14, MA15 | MA20 |

## Why this module

Backpropagation through a Transformer means differentiating matrix expressions: the gradient of a loss with respect to a weight matrix, through a softmax, a layer normalization and an attention block. Writing these gradients by hand, in compact matrix form, is what the backward rules of the LLM plan's automatic differentiation are made of.

## Objectives

After this module, you can differentiate scalar, vector and matrix expressions with respect to vectors and matrices, using differentials and consistent layout conventions, and derive the backward pass of every building block of a Transformer.

## Competences evaluated

1. Explain the numerator and denominator layout conventions and stay consistent with one.
2. Compute differentials of matrix expressions (sums, products, transposes, inverses, traces, elementwise functions).
3. Use trace identities (cyclic property, trace of products) to turn a differential into a gradient.
4. Derive the gradients of a linear layer y = Wx + b with respect to W, x and b, for a batch of inputs.
5. Derive the Jacobian of softmax and the gradient of softmax followed by cross-entropy (and why it simplifies to p − y).
6. Derive the gradients of LayerNorm and RMSNorm.
7. Derive the backward pass of scaled dot-product attention with respect to Q, K and V.
8. Handle broadcasting and reductions in gradients (sum over the broadcast dimensions).
9. Check any derived gradient numerically with finite differences and interpret the relative error.

## Notions, in learning order

1. **Layouts and shapes**: scalar-by-vector, vector-by-vector, scalar-by-matrix derivatives, conventions, shape checking as a safety net.
2. **Differentials**: rules for sums, products, transposes, inverses, determinants, elementwise functions.
3. **From differentials to gradients**: the trace trick, identification.
4. **Linear layers**: gradients for one input and for a batch, bias gradients as sums.
5. **Softmax and cross-entropy**: Jacobian of softmax, combined gradient, numerical stability.
6. **Normalization layers**: mean and variance as functions of the input, LayerNorm and RMSNorm backward.
7. **Attention**: forward computation as matrix products and a row-wise softmax, backward pass step by step.
8. **Broadcasting and reductions**: how gradients flow through them.
9. **Gradient checking**: finite differences, relative error, choosing the step, typical bugs it reveals.

## Practice

- Deriving each gradient by hand twice: once element by element, once in matrix form, and checking they agree.
- Once IN04 is validated: a gradient checker applied to hand-written forward and backward functions (linear layer, softmax with cross-entropy, LayerNorm, attention) on nested lists.

## Evaluation format

One written session, about 3 hours: derivations of gradients for blocks never derived during learning (a different combination of layers each time), plus shape and convention questions. Pass mark 100 %.

## References

- Kaare Brandt Petersen and Michael Syskind Pedersen, *The Matrix Cookbook* (free reference).
- Terence Parr and Jeremy Howard, *The Matrix Calculus You Need For Deep Learning* (free article).
- Marc Peter Deisenroth, A. Aldo Faisal and Cheng Soon Ong, *Mathematics for Machine Learning* (free book), chapter 5.
