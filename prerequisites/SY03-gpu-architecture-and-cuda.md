# SY03. GPU architecture and CUDA

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Systems and performance | 6. Advanced computer science and GPU | IN09, SY01, SY02 | none directly (used by L17 to L22, L31) |

## Why this module

Every serious training run happens on GPUs, and in this project every GPU kernel is written by hand: no cuBLAS, no cuDNN, no FlashAttention library. Reaching a good fraction of the RTX 3070's peak needs a precise understanding of how the GPU executes threads and moves data, down to tensor cores, asynchronous copies and the assembly the compiler produces.

## Objectives

After this module, you can install the CUDA toolkit, write correct and fast CUDA kernels, reason about the execution model and memory hierarchy, use tensor cores and asynchronous copies, read the generated assembly, and profile kernels to find their bottleneck.

## Competences evaluated

1. Install the CUDA toolkit for the development machine's driver, compile with `nvcc` for sm_86, and run and check a first kernel.
2. Explain the execution model: grids, blocks, warps, threads, streaming multiprocessors, warp scheduling and divergence.
3. Explain the memory hierarchy (registers, shared memory, L1, L2, global memory, constant memory) with orders of magnitude of size, latency and bandwidth on the RTX 3070.
4. Write kernels with coalesced global memory access, and use shared memory without bank conflicts (including swizzled layouts).
5. Compute and tune occupancy, explain register pressure, and use `__launch_bounds__`.
6. Synchronize correctly (block barriers, warp-level primitives, atomics) and write parallel reductions and scans with warp shuffles.
7. Manage host-device transfers, pinned memory, unified memory, streams and events, and overlap computation with transfers.
8. Use asynchronous copies (`cp.async`), `ldmatrix`, and tensor cores through WMMA and through `mma` instructions in inline PTX, with fp16 and bf16 inputs and fp32 accumulation.
9. Read SASS with `cuobjdump` and `nvdisasm` to check what the compiler generated.
10. Debug with `compute-sanitizer` and cuda-gdb, and profile with Nsight Compute and Nsight Systems to classify a kernel as compute-bound or memory-bound.

## Notions, in learning order

1. **Why GPUs**: throughput versus latency processors, the SIMT model.
2. **Toolkit and first kernels**: installation, `nvcc`, kernel launches, error checking.
3. **Execution model**: grids, blocks, warps, SMs, scheduling, divergence.
4. **Memory hierarchy**: registers, shared memory, caches, global and constant memory, the RTX 3070's numbers.
5. **Memory access**: coalescing, vectorized loads, shared memory banks, conflicts, swizzling.
6. **Occupancy and resources**: registers, shared memory per block, launch bounds, latency hiding.
7. **Synchronization and collectives**: barriers, atomics, warp shuffles, reductions, scans.
8. **Host and device**: transfers, pinned and unified memory, streams, events, concurrency.
9. **Ampere features**: asynchronous copies, `ldmatrix`, tensor cores (WMMA and `mma.sync`), fp16 and bf16.
10. **Low level**: inline PTX, SASS reading.
11. **Tools**: compute-sanitizer, cuda-gdb, Nsight Compute, Nsight Systems, the roofline of the RTX 3070 (from SY01).

## Practice

- A sequence of kernels of increasing difficulty, each measured against the roofline: vector addition, transpose (naive, coalesced, with shared memory, without bank conflicts), reduction (several versions), prefix scan, softmax.
- A first tiled matrix product, then the same with tensor cores through WMMA, compared in TFLOPS with the theoretical peak.
- Reading the SASS of each kernel to check vectorized loads and tensor-core instructions.

## Evaluation format

One practical session, about 4 hours: write and optimize kernels never written during learning (a different set each time), justify each optimization with profiler measurements, and answer questions on the execution model and memory hierarchy. Pass mark 100 %.

## References

- NVIDIA, *CUDA C++ Programming Guide* and *CUDA C++ Best Practices Guide* (free).
- NVIDIA, *Parallel Thread Execution ISA* documentation, sections on `mma`, `ldmatrix` and `cp.async` (free).
- Wen-mei W. Hwu, David B. Kirk and Izzat El Hajj, *Programming Massively Parallel Processors* (book, not free).
- Simon Boehm, *How to Optimize a CUDA Matmul Kernel for cuBLAS-like Performance* (free article).
