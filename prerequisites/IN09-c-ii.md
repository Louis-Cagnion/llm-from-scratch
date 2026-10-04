# IN09. C II

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 4. Multivariable mathematics, statistics and systems | IN05, SY01 | IN13, IN14, SY03 |

## Why this module

The fast engine of the LLM plan is a C library called from Python: tensors laid out with strides, matrix products vectorized with AVX2 and spread over threads, checked with sanitizers. This module covers the advanced C needed to write such code correctly and make it fast.

## Objectives

After this module, you can write correct, fast and portable C: control memory layout and alignment, avoid undefined behavior, debug with sanitizers and gdb, build shared libraries called from Python, use threads and atomics, and vectorize loops with SIMD intrinsics.

## Competences evaluated

1. Use function pointers (callbacks, dispatch tables) and `void *` generic code.
2. Control allocation and alignment (`aligned_alloc`, alignment of structures, padding), and explain why alignment matters for SIMD.
3. Lay out multidimensional arrays in flat memory with shapes and strides, and compute addresses of views (transpose, slice) without copying.
4. Manipulate bits (masks, shifts, popcount), and reinterpret the bits of a float safely.
5. Recognize the common undefined behaviors (signed overflow, out-of-bounds access, strict aliasing violations, uninitialized reads) and avoid them.
6. Find memory and undefined-behavior bugs with AddressSanitizer, UndefinedBehaviorSanitizer and Valgrind, and debug with gdb (breakpoints, backtraces, watchpoints).
7. Build a shared library (`.so`) and call it from Python with `ctypes`, passing buffers and structures; explain the CPython C API as the alternative.
8. Write multithreaded code with POSIX threads (creation, joining, mutexes, condition variables), split work across threads and measure the speedup.
9. Use C11 atomics and explain memory ordering at a basic level (relaxed, acquire, release).
10. Vectorize loops with SSE and AVX2 intrinsics (loads, stores, FMA, horizontal sums), and check what the compiler auto-vectorizes.
11. Optimize with measurement: compiler options (`-O2`, `-O3`, `-march`), profiling (`perf` if available, or timers), profile-guided optimization.

## Notions, in learning order

1. **Advanced pointers**: function pointers, generic code, `restrict`.
2. **Memory layout**: alignment, padding, structure of arrays versus array of structures, flat multidimensional arrays, strides and views.
3. **Bits**: operators, masks, float representation and bit reinterpretation with `memcpy`.
4. **Undefined behavior**: the list that matters, why compilers exploit it, how to avoid it.
5. **Tooling**: sanitizers, Valgrind, gdb, compiler warnings as errors.
6. **Libraries**: static and shared libraries, symbol visibility, calling C from Python with `ctypes`, the CPython C API (first look).
7. **Threads**: POSIX threads, synchronization primitives, work partitioning, false sharing (from SY01).
8. **Atomics**: C11 atomics, memory orders, lock-free counters.
9. **SIMD**: intrinsics for SSE, AVX2 and FMA, data alignment, reductions, checking auto-vectorization.
10. **Optimization method**: measure, change one thing, measure again; compiler flags; profile-guided optimization.

## Practice

- A strided tensor library in C (create, view, transpose without copy, elementwise operations, reduction), tested under sanitizers.
- A matrix product optimized step by step (loop order, blocking, AVX2 with FMA, threads), with the speedup of each step measured and compared with the roofline of SY01.
- The same library compiled as a `.so` and driven from Python with `ctypes`.

## Evaluation format

One practical session, about 3 hours: programs to write (strided views, a threaded and vectorized kernel, a `ctypes` binding), one program with hidden undefined behavior to diagnose with the tools, and questions on alignment, atomics and optimization. Pass mark 100 %.

## References

- Jens Gustedt, *Modern C* (free book), advanced levels.
- Intel Intrinsics Guide (free online reference).
- Agner Fog, *Optimizing software in C++* (free manual, applies to C).
- GCC documentation: sanitizers and optimization options (free).
