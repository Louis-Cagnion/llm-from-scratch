# MA13. Discrete mathematics and graphs

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 3. Analysis, probability and algorithms | MA03, MA12 | IN07, IN12, MA26 |

## Why this module

Automatic differentiation walks a directed acyclic graph of operations in topological order; tokenizers, parsers and search structures are trees and graphs; hashing powers deduplication of training data; complexity analysis says whether an algorithm survives at scale. This module gives the discrete side of the mathematics the project relies on.

## Objectives

After this module, you can solve recurrences, reason about graphs and trees, compute a topological order, analyze the complexity of algorithms, and use modular arithmetic and hashing.

## Competences evaluated

1. Solve linear recurrences and divide-and-conquer recurrences (master theorem, statement and use).
2. Prove properties of recursive structures by structural induction.
3. Model a problem as a graph (directed or not, weighted or not) and represent it by adjacency lists and adjacency matrices.
4. Reason about paths, cycles, connectivity and degrees.
5. Recognize a directed acyclic graph, compute a topological order, and explain why it is the order of backpropagation.
6. Use trees: rooted trees, binary trees, heights, the relation between nodes and edges, heaps (structure and invariant).
7. Analyze the time and memory complexity of an algorithm with O, Ω and Θ, including amortized cost.
8. Compute with modular arithmetic (congruences, operations modulo n, modular exponentiation by hand on small numbers).
9. Explain hash functions, collisions and their probability (birthday paradox), and the Jaccard similarity of sets.

## Notions, in learning order

1. **Recurrences**: linear recurrences, characteristic equation, divide-and-conquer recurrences, master theorem.
2. **Induction on structures**: lists, trees, expressions.
3. **Graphs**: vertices, edges, directed and undirected, weighted, degrees, representations.
4. **Paths and connectivity**: walks, paths, cycles, connected components, strongly connected components (definition).
5. **Directed acyclic graphs**: definition, topological sort (Kahn's algorithm and depth-first search), computation graphs.
6. **Trees**: properties, rooted and binary trees, traversals, heaps.
7. **Complexity**: asymptotic notation, worst, average and amortized cases, common complexity classes.
8. **Modular arithmetic**: congruences, modular operations, remainders of powers.
9. **Hashing**: hash functions, collisions, birthday paradox, Jaccard similarity (basis of MinHash).

## Practice

- Recurrence and induction exercises by hand.
- Drawing the computation graph of formulas and ordering it topologically by hand.
- Once IN02 is validated: a graph module (adjacency lists, depth-first and breadth-first traversal, topological sort, cycle detection) and an experiment measuring collision rates of a simple hash function against the birthday-paradox prediction.

## Evaluation format

One written session, about 2 hours: around 15 exercises covering every competence, including one induction proof and one topological sort. Pass mark 100 %.

## References

- MIT OpenCourseWare, *6.042J Mathematics for Computer Science* (free lectures and book).
- Kenneth H. Rosen, *Discrete Mathematics and Its Applications* (book, not free).
