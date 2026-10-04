# IN12. Formal languages and parsing

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 6. Advanced computer science and GPU | IN07, MA13 | IN13, IN14 |

## Why this module

Without libraries, every format must be parsed by hand: the regular expressions of the tokenizer's pre-tokenization, HTML pages of the web crawl, JSON tool calls, JSON Schema for structured outputs, Markdown rendered in the chat, chat templates of open-weight models, and the certificates of TLS. Constrained decoding even turns a grammar into an automaton that masks the model's tokens. This module gives the theory and practice of languages and parsers.

## Objectives

After this module, you can describe languages with regular expressions and grammars, convert them to automata, write tokenizers and parsers by hand with the right technique, and parse the formats the project needs.

## Competences evaluated

1. Define alphabets, strings and languages, and describe languages with regular expressions.
2. Build an NFA from a regular expression (Thompson's construction), convert it to a DFA (subset construction), and minimize it.
3. Implement a regular expression matcher by simulating an NFA, and explain why backtracking matchers can be exponential.
4. Write finite-state tokenizers, including a state machine of the kind used to tokenize HTML.
5. Write context-free grammars, derive strings, draw parse trees, and detect and remove ambiguity.
6. Explain pushdown automata and the limits of regular languages (nested structures).
7. Write recursive-descent parsers, compute FIRST and FOLLOW sets for LL(1) grammars, and explain LR (shift-reduce) parsing and Earley parsing.
8. Write complete hand-made parsers for JSON (with precise error messages) and for a subset of Markdown (CommonMark block and inline structure).
9. Validate JSON values against a JSON Schema subset.
10. Implement a small template language in the style of Jinja (variables, loops, conditions) to render chat templates.

## Notions, in learning order

1. **Languages**: alphabets, strings, operations on languages.
2. **Regular expressions and automata**: syntax, NFA, DFA, Thompson construction, subset construction, minimization, equivalence.
3. **Matching**: NFA simulation, backtracking and its pathological cases, practical regex features (classes, anchors, repetitions, Unicode categories).
4. **Lexical analysis**: tokens, finite-state tokenizers, maximal munch, the HTML tokenizer as an example.
5. **Context-free grammars**: productions, derivations, parse trees, ambiguity, precedence and associativity.
6. **Pushdown automata**: definition, link with grammars, nesting.
7. **Parsing techniques**: recursive descent, LL(1), LR and shift-reduce, Earley parsing for any grammar.
8. **Real formats**: JSON (grammar, numbers, strings, escapes, errors), Markdown (blocks then inlines, the CommonMark approach).
9. **Schemas**: JSON Schema subset (types, properties, required fields, enumerations, arrays).
10. **Templates**: lexing and parsing a template language, rendering with an environment.

## Practice

- Converting regular expressions to automata by hand.
- Writing grammars for arithmetic expressions and for JSON, then their parsers.
- Once IN07 is validated: a regex engine supporting the features needed by GPT-style pre-tokenization patterns, a JSON parser and serializer with error positions, a Markdown-to-HTML converter for a CommonMark subset, a JSON Schema validator, and a template engine, each with a test suite.

## Evaluation format

One practical session, about 3 hours 30: automata constructions by hand, and a parser to write for a format never seen during learning, plus questions on grammar classes. Pass mark 100 %.

## References

- Michael Sipser, *Introduction to the Theory of Computation* (book, not free), chapters 1 and 2.
- Russ Cox, *Regular Expression Matching Can Be Simple And Fast* (free article series).
- Robert Nystrom, *Crafting Interpreters* (free online book), scanning and parsing chapters.
- The JSON specification (RFC 8259), the CommonMark specification and JSON Schema documentation (free).
