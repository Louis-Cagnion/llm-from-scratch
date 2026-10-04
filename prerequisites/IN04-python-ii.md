# IN04. Python II

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 2. Core mathematics and programming | IN02 | IN06, IN07, IN10 |

## Why this module

The reference implementation of the LLM plan is built from Python classes: a `Tensor` class whose operators (`+`, `*`, `@`) build a computation graph, `Module` and `Parameter` classes, data loaders written as generators, decorators for no-gradient modes. Object-oriented programming and the advanced language features are what make this possible without any library.

## Objectives

After this module, you can design programs with classes, overload operators, write iterators, generators, decorators and context managers, annotate types, and organize code into packages.

## Competences evaluated

1. Define classes with attributes and methods, and distinguish instance, class and static attributes and methods.
2. Use inheritance, method overriding and `super()`, and choose composition over inheritance when appropriate.
3. Implement special methods: representation (`__repr__`, `__str__`), comparison, arithmetic operators and their reflected versions (`__add__`, `__radd__`, `__matmul__`...), container protocols (`__len__`, `__getitem__`, `__setitem__`, `__iter__`, `__contains__`), `__call__`.
4. Use properties to control attribute access.
5. Write iterators (the iterator protocol) and generators (`yield`, `yield from`, generator expressions), and explain lazy evaluation.
6. Write closures and decorators (with and without arguments), and use `functools.wraps`.
7. Write context managers with a class (`__enter__`, `__exit__`) and explain what `with` guarantees.
8. Annotate functions and classes with type hints and use dataclasses.
9. Write recursive functions and explain the recursion limit.
10. Organize code into modules and packages, with relative imports and an `__init__.py`, and use a virtual environment.

## Notions, in learning order

1. **Classes and objects**: instances, attributes, methods, `self`, constructors.
2. **Class design**: class and static methods, encapsulation conventions, properties.
3. **Inheritance and composition**: subclassing, overriding, `super()`, abstract base classes (first look), when not to inherit.
4. **Special methods**: the data model, operator overloading, reflected operators, containers, callable objects.
5. **Iteration**: iterables versus iterators, the protocol, generators, generator expressions, `itertools` patterns.
6. **Functions as objects**: first-class functions, closures, decorators, `functools`.
7. **Context managers**: the protocol, resource management, exception handling in `__exit__`.
8. **Types**: type hints, `typing` basics, dataclasses.
9. **Recursion**: recursive thinking, base cases, the call stack and its limit.
10. **Packages**: modules, packages, imports, virtual environments.

## Practice

- A `Fraction` class with full operator overloading, comparison and hashing, tested against hand computations.
- A `Vector` class supporting `+`, `-`, scalar `*`, `@` (dot product), `abs` (norm) and indexing: a first taste of the L02 tensors.
- A generator pipeline that reads a large text file lazily, splits it into words and counts them without loading it in memory.
- A timing decorator and a context manager that changes a setting temporarily (the pattern of a no-gradient mode).

## Evaluation format

One practical session, about 2 hours 30: classes to design with operator overloading, generators, a decorator and a context manager to write, and code-reading questions on the data model. Pass mark 100 %.

## References

- The Python Tutorial (classes, iterators, generators) and the Python Language Reference, chapter *Data model* (official, free).
- Luciano Ramalho, *Fluent Python* (book, not free).
