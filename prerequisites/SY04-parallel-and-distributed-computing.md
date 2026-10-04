# SY04. Parallel and distributed computing

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Systems and performance | 6. Advanced computer science and GPU | SY02, IN11 | SY05 |

## Why this module

Frontier models are trained on thousands of GPUs that constantly exchange gradients and activations. The LLM plan replaces NCCL with hand-written collectives and simulates data, tensor, pipeline and expert parallelism on one machine (L35, L36). This module teaches the principles: how to split work, how processes communicate, what communication costs, and how to survive failures.

## Objectives

After this module, you can analyze the speedup of a parallel program, choose between shared memory and message passing, implement the collective operations with the right algorithms, estimate their cost, and design fault tolerance with checkpoints.

## Competences evaluated

1. Distinguish data parallelism and task parallelism, and apply Amdahl's law and Gustafson's law to predict speedups.
2. Compare shared memory and message passing, and choose between them for a given problem.
3. Define the collective operations (broadcast, reduce, all-reduce, gather, all-gather, scatter, reduce-scatter, all-to-all) and their uses in training.
4. Implement ring all-reduce (as reduce-scatter plus all-gather) and tree algorithms between processes, and prove their correctness on small cases.
5. Estimate the time of a collective with the latency-bandwidth (α-β) model, and choose the algorithm according to message size and number of participants.
6. Describe the interconnects of a training cluster (PCIe, NVLink and NVSwitch, InfiniBand and RoCE, RDMA, GPUDirect) and their bandwidths.
7. Explain CUDA inter-process communication and peer-to-peer access between GPUs.
8. Design fault tolerance with checkpoints (frequency, cost, consistency) and explain elastic restarts.
9. Measure the scaling of a parallel program (strong and weak scaling) and explain the gap with the ideal.

## Notions, in learning order

1. **Parallel performance**: speedup, efficiency, Amdahl and Gustafson, strong and weak scaling.
2. **Models of parallelism**: data and task parallelism, shared memory, message passing, bulk synchronous parallel.
3. **Communication primitives**: point-to-point, collectives, semantics of each collective.
4. **Collective algorithms**: ring, tree, recursive doubling, bandwidth-optimal all-reduce.
5. **Cost models**: latency and bandwidth terms, α-β model, overlap of communication and computation.
6. **Hardware**: interconnects in a node and between nodes, RDMA, GPUDirect, topology.
7. **GPU communication**: CUDA IPC, peer access, staging through host memory.
8. **Fault tolerance**: failures at scale, checkpoints, coordinated checkpointing, elastic training.
9. **Measuring**: scaling experiments, profiling communication.

## Practice

- Collective operations implemented between local processes over sockets and shared memory (from SY02 and IN11), checked for correctness and timed against the α-β model.
- A data-parallel training simulation on a tiny model: gradients averaged with the hand-written all-reduce, results identical to single-process training.
- A checkpoint and restart mechanism tested by killing processes on purpose.

## Evaluation format

One session, about 3 hours: implement a collective never implemented during learning, analyze its cost with the α-β model, and answer questions on scaling laws of parallel programs, interconnects and fault tolerance. Pass mark 100 %.

## References

- Ernie Chan et al., *Collective Communication: Theory, Practice, and Experience* (2007, free paper).
- Andrew Gibiansky, *Bringing HPC Techniques to Deep Learning* (free article on ring all-reduce).
- Ananth Grama et al., *Introduction to Parallel Computing* (book, not free).
