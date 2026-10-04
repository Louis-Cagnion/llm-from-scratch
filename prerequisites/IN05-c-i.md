# IN05. C I

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 2. Core mathematics and programming | IN01 | IN09, IN10, SY01, SY02 |

## Why this module

Speed in the LLM plan comes from C and CUDA: the CPU engine, the tokenizer's fast path and every GPU kernel are written in C or its CUDA dialect. C also shows what the machine really does with memory, which explains why some layouts are fast and others slow.

## Objectives

After this module, you can write, compile and debug multi-file C programs that use pointers, arrays, strings, structures and dynamic memory correctly, without leaks or undefined behavior in the common cases.

## Competences evaluated

1. Explain the compilation chain (preprocessor, compiler, assembler, linker) and compile a multi-file program with `cc` and a Makefile.
2. Use the basic types, their sizes and limits, integer and floating-point arithmetic, conversions and their pitfalls (overflow, truncation).
3. Write control flow and functions, and explain pass-by-value.
4. Explain and use pointers: addresses, dereferencing, pointer arithmetic, pointers to pointers, `NULL`.
5. Use arrays and their relation to pointers, including two-dimensional arrays.
6. Manipulate C strings (null termination) and write string functions by hand.
7. Define and use structures, unions and enumerations, and `typedef`.
8. Allocate and free memory dynamically (`malloc`, `calloc`, `realloc`, `free`), check every allocation, and avoid leaks, double frees and use after free.
9. Read and write files and standard streams (`fopen`, `fread`, `fwrite`, `fprintf`, `fgets`), checking errors.
10. Organize a program into headers and source files, with include guards and `static` functions.
11. Find and fix a crash with the compiler's warnings (`-Wall -Wextra`) and a debugger.

## Notions, in learning order

1. **From source to executable**: preprocessor, compilation, linking, `cc`, warnings, Makefiles.
2. **Types and operators**: integer types and sizes, `float` and `double`, `sizeof`, arithmetic, conversions, overflow.
3. **Control flow and functions**: conditions, loops, functions, prototypes, pass-by-value, recursion.
4. **Pointers**: memory as an array of bytes, addresses, dereferencing, pointer arithmetic, `NULL`, pointers as parameters.
5. **Arrays**: static arrays, decay to pointers, multidimensional arrays, passing arrays to functions.
6. **Strings**: character arrays, null terminator, writing `strlen`, `strcpy`, `strcmp` by hand, buffer overflows.
7. **Composite types**: structures, nested structures, pointers to structures, unions, enumerations, `typedef`.
8. **Dynamic memory**: the heap, allocation functions, ownership, leaks, dangling pointers, double free.
9. **Input and output**: standard streams, files, binary and text modes, error checking.
10. **Program organization**: headers, include guards, `static`, `extern`, separate compilation.
11. **Debugging basics**: reading compiler warnings, `printf` debugging, gdb (first look), Valgrind (first look).

## Practice

- The classic exercises written by hand: string functions, number conversions, a dynamic array that grows, a linked list, a matrix stored in a flat array with row and column indexing.
- A program that reads a binary file of floats, computes statistics and writes a report, with every error checked.
- Each program compiled with `-Wall -Wextra -Werror` and run under Valgrind until it is clean.

## Evaluation format

One practical session, about 3 hours: several programs to write and compile (pointers, strings, structures, dynamic memory, files), one buggy program to fix, and code-reading questions (what does this pointer code print, where is the leak). Pass mark 100 %.

## References

- Brian W. Kernighan and Dennis M. Ritchie, *The C Programming Language* (book, not free).
- Jens Gustedt, *Modern C* (free book).
- Beej's Guide to C Programming (free).
