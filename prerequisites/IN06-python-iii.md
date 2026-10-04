# IN06. Python III

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 3. Analysis, probability and algorithms | IN04 | IN11 |

## Why this module

Without NumPy, the reference engine must handle memory and binary data itself: tensors stored in flat `array` buffers, weights saved as raw bytes and loaded with `mmap`, data loaders running in parallel processes, a chat server streaming tokens with `asyncio`. This module covers the parts of Python that touch memory, bytes, concurrency and performance.

## Objectives

After this module, you can reason about Python's memory model, manipulate binary data efficiently, run work concurrently with threads, processes or asyncio, write command-line tools, and measure performance before optimizing.

## Competences evaluated

1. Explain names, references, mutability, aliasing, shallow and deep copies, reference counting and garbage collection, and predict the effect of mutating shared objects.
2. Manipulate binary data with `bytes`, `bytearray`, `memoryview`, `struct` (formats, endianness, alignment) and `array`.
3. Read and write binary files, and map a file into memory with `mmap`.
4. Explain why `pickle` is unsafe on untrusted data, and design a simple safe binary format (header plus raw data).
5. Explain the GIL and choose between threads, processes and asyncio for a given workload (I/O-bound or CPU-bound).
6. Use `threading` (threads, locks, queues), `multiprocessing` (pools, shared memory) and `asyncio` (coroutines, tasks, event loop) correctly.
7. Open TCP connections with `socket` (client and server, first look) and run external programs with `subprocess`.
8. Build command-line tools with `argparse` and log with `logging` (levels, handlers, formats).
9. Measure performance with `time.perf_counter`, `timeit` and `cProfile`, find the hot spot of a program and compare two versions fairly.
10. Explain the cost of Python-level loops compared with operations on contiguous buffers, and why a compiled engine is needed for tensors.

## Notions, in learning order

1. **Memory model**: objects, identity, references, mutability, aliasing, copies, reference counting, cycles and the garbage collector.
2. **Binary data**: bytes and bytearray, memoryview, the `struct` module, endianness, the `array` module.
3. **Binary files**: modes, seeking, `mmap`, designing a file format.
4. **Serialization**: text formats, why `pickle` executes code, safe alternatives.
5. **Concurrency models**: the GIL, threads, processes, asynchronous I/O.
6. **Threads and processes**: `threading`, locks, queues, `multiprocessing`, pools, shared memory, pitfalls (deadlocks, races).
7. **asyncio**: coroutines, `await`, tasks, the event loop, streams.
8. **System interfaces**: `socket` basics, `subprocess`, `selectors`.
9. **Tools**: `argparse`, `logging`.
10. **Performance**: measuring correctly, profiling, interpreter overhead, contiguous buffers.

## Practice

- A program that writes a million floats to a binary file in a hand-designed format (JSON header plus raw data) and reads them back with `mmap`, compared with a text format in size and speed.
- A parallel word counter over many files, written with threads, then processes, then asyncio, with measured speedups explained.
- A small echo server and client with `socket`, then the same with `asyncio`.
- Profiling a slow program, finding its hot spot and fixing it, with measurements before and after.

## Evaluation format

One practical session, about 3 hours: programming tasks on binary data, `mmap`, concurrency and profiling, and questions on the memory model and the GIL. Pass mark 100 %.

## References

- The Python Library Reference: `struct`, `array`, `mmap`, `threading`, `multiprocessing`, `asyncio`, `socket`, `subprocess`, `argparse`, `logging`, `cProfile` (official, free).
- The Python Language Reference, *Data model* (official, free).
