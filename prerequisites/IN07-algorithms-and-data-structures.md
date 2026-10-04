# IN07. Algorithms and data structures

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 3. Analysis, probability and algorithms | IN04, MA12, MA13 | IN12 |

## Why this module

The stack is full of classic algorithms that no library will provide here: a heap to pick the next BPE merge, tries for tokenizers, hash tables for deduplication, dynamic programming for edit distances and Viterbi decoding, Huffman coding for compression, priority queues for beam search, graphs for automatic differentiation. Each must be written, understood and made efficient by hand.

## Objectives

After this module, you can choose, implement and analyze the classic data structures and algorithms, and apply the main design techniques to new problems.

## Competences evaluated

1. Analyze the time and memory complexity of an algorithm, including amortized costs (dynamic arrays).
2. Implement and use dynamic arrays, linked lists, stacks and queues.
3. Implement a hash table (hashing, collisions by chaining or open addressing, resizing) and explain its expected costs.
4. Implement binary search trees and explain why balancing matters.
5. Implement a binary heap and a priority queue, and use them (top-k, merging sorted lists, scheduling).
6. Implement a trie and use it for prefix search and longest-match tokenization.
7. Implement graph algorithms: breadth-first and depth-first search, topological sort, shortest paths (Dijkstra).
8. Implement and compare sorting algorithms (merge sort, quicksort, heapsort) and binary search, including on answers.
9. Design dynamic programming algorithms (edit distance, longest common subsequence, Viterbi on a hidden Markov model given as tables).
10. Design greedy algorithms and prove their correctness on classic cases (Huffman coding).
11. Use divide and conquer and backtracking.

## Notions, in learning order

1. **Complexity analysis**: models of cost, worst and average cases, amortization.
2. **Linear structures**: dynamic arrays and their growth, linked lists, stacks, queues, deques.
3. **Hash tables**: hash functions, chaining, open addressing, load factor, resizing.
4. **Trees**: binary search trees, traversals, the idea of balanced trees.
5. **Heaps**: binary heap, sift up and down, heapify in linear time, priority queues.
6. **Tries**: insertion, search, prefix queries, longest match.
7. **Graphs**: representations, BFS, DFS, topological sort, Dijkstra.
8. **Sorting and searching**: merge sort, quicksort, heapsort, lower bound for comparison sorts, binary search.
9. **Dynamic programming**: overlapping subproblems, tables, reconstruction of solutions, edit distance, LCS, Viterbi.
10. **Greedy algorithms**: exchange arguments, Huffman coding.
11. **Divide and conquer, backtracking**: recursion trees, pruning.

## Practice

- Each structure implemented from scratch in Python with tests, then benchmarked on growing sizes to check its complexity (doubling the input and measuring).
- Small projects: a word autocompleter with a trie, a Huffman compressor and decompressor for text files, a spelling corrector with edit distance.
- Later reused directly in the LLM plan (heaps in L10, hash tables in L12, graphs in L03).

## Evaluation format

One practical session, about 3 hours: algorithmic problems never seen before to solve and implement, with a complexity analysis of each, plus questions on the structures. Pass mark 100 %.

## References

- Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest and Clifford Stein, *Introduction to Algorithms* (book, not free).
- MIT OpenCourseWare, *6.006 Introduction to Algorithms* (free lectures).
- Jeff Erickson, *Algorithms* (free online book).
