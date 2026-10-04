# SY01. Computer architecture

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Systems and performance | 3. Analysis, probability and algorithms | MA01, IN05 | IN09, SY02, SY03 |

## Why this module

The speed of a model depends less on the number of operations than on how data moves: a matrix product is fast only if it reuses data from caches, attention became fast when FlashAttention stopped moving it to slow memory, and the whole field reasons with arithmetic intensity and the roofline model. This module explains what happens inside the machine.

## Objectives

After this module, you can explain how numbers are represented, how a processor executes instructions, how the memory hierarchy behaves, and predict whether a computation is limited by computation or by memory bandwidth.

## Competences evaluated

1. Convert between decimal, binary and hexadecimal, and represent signed integers in two's complement, including overflow behavior.
2. Explain the role of the instruction set, registers and memory, and read simple assembly produced by the compiler.
3. Explain pipelining, branch prediction and out-of-order execution, and why branches and dependencies cost time.
4. Describe the memory hierarchy (registers, L1, L2, L3, DRAM) with orders of magnitude of size and latency, cache lines, associativity and the TLB.
5. Predict the effect of an access pattern on performance (sequential versus strided versus random access), and explain spatial and temporal locality.
6. Explain SIMD (vector instructions) and multicore execution, cache coherence and false sharing.
7. Compute the arithmetic intensity of a kernel (operations per byte moved) and place it on a roofline model to decide whether it is compute-bound or memory-bound.
8. Measure memory bandwidth and the effect of cache blocking with small benchmarks, and interpret the results.
9. Explain the role of PCIe between the processor and the GPU, and its bandwidth compared with GPU memory.

## Notions, in learning order

1. **Data representation**: bits, bytes, binary, hexadecimal, two's complement, byte order (endianness).
2. **The processor**: instruction set architectures (x86-64), registers, the fetch-decode-execute cycle, reading compiler output.
3. **Instruction-level parallelism**: pipelines, hazards, branch prediction, out-of-order and superscalar execution.
4. **The memory hierarchy**: registers, caches, DRAM, latencies and bandwidths, cache lines, associativity, replacement, TLB and pages.
5. **Locality**: access patterns, strides, loop order in a matrix product, blocking (tiling).
6. **Parallelism**: SIMD registers and instructions, multicore processors, cache coherence, false sharing, simultaneous multithreading.
7. **Performance models**: arithmetic intensity, the roofline model, compute-bound versus memory-bound kernels.
8. **Beyond the CPU**: buses, PCIe, the GPU as a separate device with its own memory (first look before SY03).

## Practice

- Representation exercises by hand (conversions, two's complement arithmetic, overflows).
- Benchmarks written in C (after IN05): sequential versus random memory access, the three loop orders of a matrix product, a blocked matrix product, measured and explained.
- Rooflines drawn for the development machine's CPU and GPU from their specifications, with the matrix product, a vector addition and softmax placed on them.

## Evaluation format

One session, about 2 hours: written exercises on representation, caches and arithmetic intensity, plus benchmark results to interpret and a roofline analysis of kernels never seen before. Pass mark 100 %.

## References

- Randal E. Bryant and David R. O'Hallaron, *Computer Systems: A Programmer's Perspective* (book, not free).
- Ulrich Drepper, *What Every Programmer Should Know About Memory* (free article).
- Samuel Williams, Andrew Waterman and David Patterson, *Roofline: An Insightful Visual Performance Model for Multicore Architectures* (2009, free paper).
