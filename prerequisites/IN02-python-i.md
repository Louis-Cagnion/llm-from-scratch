# IN02. Python I

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 1. Foundations | IN01 | IN04, IN08 |

## Why this module

Python is the language of every reference implementation in the LLM plan: the math library, tensors, automatic differentiation, tokenizers, the training loop. Since no library is allowed, the core language must be mastered rather than hidden behind packages.

## Objectives

After this module, you can write, run and debug Python programs of a few hundred lines that use the core types, control flow, functions, files and exceptions, with clear structure and naming.

## Competences evaluated

1. Run Python code in the interactive interpreter and as a script, and read a traceback to locate an error.
2. Use the core types (`int`, `float`, `bool`, `str`, `None`), conversions between them, and explain integer versus float division, `//` and `%` (including with negative numbers).
3. Write conditions (`if`, `elif`, `else`), boolean logic with short-circuit evaluation, and comparisons (including chained ones).
4. Write loops (`for` over ranges and collections, `while`, `break`, `continue`, `else` on loops) and choose the right one.
5. Define functions with positional, default, keyword and variable arguments, return values, and explain local versus global scope.
6. Manipulate strings: indexing, slicing, methods, formatting with f-strings, immutability.
7. Use lists, tuples, dictionaries and sets: creation, access, mutation, iteration, membership, common methods, and their typical costs.
8. Write list, dictionary and set comprehensions.
9. Read and write text files safely with `with`, line by line and in full.
10. Raise and handle exceptions (`try`, `except`, `else`, `finally`), and choose which errors to catch.
11. Import and use standard library modules, and organize a program into functions with a `main` entry point.
12. Write readable code: naming, small functions, docstrings, comments only where needed.

## Notions, in learning order

1. **Running Python**: interpreter, scripts, the REPL, tracebacks.
2. **Values and types**: numbers, booleans, strings, `None`, dynamic typing, conversions, integer arithmetic of arbitrary size, floating-point surprises (`0.1 + 0.2`).
3. **Variables and operators**: assignment, names as references (first look), arithmetic, comparison and logical operators, precedence.
4. **Control flow**: conditions, loops, `range`, `break` and `continue`, nested loops.
5. **Functions**: definition, parameters and arguments, return, default values, `*args` and `**kwargs`, scope, recursion (first look).
6. **Strings**: indexing, slicing, methods, formatting, escape sequences, Unicode in Python strings (first look).
7. **Collections**: lists, tuples, dictionaries, sets, nesting, iteration patterns (`enumerate`, `zip`, `sorted`).
8. **Comprehensions**: list, dict and set comprehensions, conditions inside them.
9. **Files**: opening modes, `with`, reading and writing text, paths.
10. **Exceptions**: built-in exceptions, handling, raising, cleanup with `finally`.
11. **Modules**: `import`, the standard library, `if __name__ == "__main__":`.
12. **Style**: PEP 8, naming, docstrings, structuring a small program.

## Practice

- Many short exercises per notion, then small programs: a word-frequency counter for a text file, a number-guessing game, a to-do list stored in a text file, a CSV report generator written without the `csv` module.
- Re-implementing in Python the algorithms of MA01 (Euclid, prime sieve, base conversion) if MA01 is done.

## Evaluation format

One practical session, about 2 hours 30: around 10 short programming exercises covering every competence, one program of about 100 lines to write from a specification, and code-reading questions (predict the output, find the bug). Pass mark 100 %.

## References

- The Python Tutorial, docs.python.org (official, free).
- Al Sweigart, *Automate the Boring Stuff with Python* (free online book), first part.
- Allen B. Downey, *Think Python* (free online book).
