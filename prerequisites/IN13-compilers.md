# IN13. Compilers

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 6. Advanced computer science and GPU | IN12, IN09 | none directly (used by L34) |

## Why this module

Fast deep learning frameworks compile computation graphs: they fuse operators to avoid memory traffic, plan buffers, and generate GPU kernels specialized for each shape. The LLM plan builds such a graph compiler by hand (L34). This module teaches the compiler techniques it relies on.

## Objectives

After this module, you can build a small compiler end to end: parse a language into an abstract syntax tree, lower it to an intermediate representation, analyze and optimize it, and generate C or PTX code.

## Competences evaluated

1. Describe the phases of a compiler (front end, middle end, back end) and what each produces.
2. Build abstract syntax trees from a parser and evaluate them with an interpreter.
3. Design an intermediate representation (three-address code or a graph of operations) and lower an AST to it.
4. Convert code to static single assignment form and explain why it simplifies analysis.
5. Run dataflow analyses (liveness, reaching definitions) on small programs.
6. Apply classic optimizations: constant folding, common subexpression elimination, dead code elimination.
7. Apply loop transformations (fusion, tiling, unrolling) and explain their effect on memory traffic.
8. Explain instruction scheduling and register allocation (graph coloring at the level of ideas).
9. Generate C source code or PTX text from an IR and compile it at run time.
10. Explain just-in-time compilation and caching of generated code.

## Notions, in learning order

1. **Compiler structure**: phases, representations, interpreters versus compilers.
2. **Front end**: lexing and parsing (from IN12), abstract syntax trees, semantic checks.
3. **Intermediate representations**: three-address code, control-flow graphs, dataflow graphs.
4. **SSA form**: φ functions, construction, uses.
5. **Analyses**: dataflow frameworks, liveness, reaching definitions.
6. **Optimizations**: folding, propagation, CSE, DCE, inlining.
7. **Loops**: dependences, fusion, tiling, unrolling, vectorization (first look).
8. **Back end**: instruction selection, scheduling, register allocation.
9. **Code generation**: emitting C and PTX text, calling the system compiler or a runtime compiler.
10. **JIT compilation**: compiling at run time, specialization, caching.

## Practice

- A compiler for a tiny expression language with variables and loops: parser, AST, IR, SSA, constant folding, CSE and DCE, then generation of C code compiled and loaded at run time with `ctypes`.
- A graph of tensor operations (add, multiply, exp, sum) fused into a single generated C loop, with the memory traffic saved measured.

## Evaluation format

One practical session, about 3 hours 30: extend a provided small compiler with a new analysis and a new optimization, then generate code for a new construct, plus questions on SSA and loop transformations. Pass mark 100 %.

## References

- Robert Nystrom, *Crafting Interpreters* (free online book).
- Alfred V. Aho, Monica S. Lam, Ravi Sethi and Jeffrey D. Ullman, *Compilers: Principles, Techniques, and Tools* (book, not free).
- Keith D. Cooper and Linda Torczon, *Engineering a Compiler* (book, not free).
