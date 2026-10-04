# ME01. Technical English and reading papers

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Method | 1. Foundations | none | every module of the LLM plan (each one comes with papers to read) |

## Why this module

Almost everything the LLM plan teaches was first published in English, in research papers, technical reports and documentation. Reading them fluently, and knowing how to extract a method, an equation or a number from them, is what allows each module to go back to the original source instead of a second-hand summary. It also serves the repository and the LinkedIn posts, which are written in English.

## Objectives

After this module, you can read technical English (documentation, papers, code comments) without translating word by word, extract the method and results of a research paper, reproduce one of its equations or tables, and write clear technical English for the logbook and posts.

## Competences evaluated

1. Understand the core vocabulary of mathematics, programming and machine learning in English (a glossary built during the module).
2. Read official documentation (Python, Linux manual pages, CUDA guide excerpts) and answer precise questions about it.
3. Describe the standard structure of a research paper (abstract, introduction, related work, method, experiments, ablations, limitations, appendices) and say where to find each kind of information.
4. Apply a three-pass reading method to a paper: survey, understanding of the method, critical reading.
5. Summarize a paper in a few sentences: problem, idea, method, key result, limitation.
6. Translate an equation of a paper into words and into pseudo-code, and identify every symbol.
7. Read a results table or figure and state what it supports and what it does not.
8. Find a paper and its context on arXiv, follow its references and the papers that cite it, and distinguish preprints from peer-reviewed publications.
9. Write a short technical text in correct English (a logbook entry, a commit message, a summary).

## Notions, in learning order

1. **Technical vocabulary**: mathematics (sum, product, derivative, gradient, matrix, eigenvalue...), programming (function, argument, loop, exception...), machine learning (loss, training, inference, overfitting, benchmark...); a personal glossary kept up to date for the whole project.
2. **Grammar for reading**: passive voice, long noun phrases ("the expected per-token cross-entropy loss"), hedging ("we hypothesize", "suggests"), logical connectors.
3. **Documentation**: how manuals and API references are organized, reading signatures and parameter tables.
4. **The anatomy of a paper**: sections and their roles, what reviewers look for, where the real details hide (appendices, footnotes, code).
5. **Reading method**: three passes, questions to ask, taking notes, the difference between what is claimed and what is shown.
6. **Equations and notation**: conventions (bold for vectors and matrices, subscripts and superscripts, ∑, expectations 𝔼), mapping equations to code.
7. **Results**: tables, plots, baselines, error bars, ablations, how results can mislead.
8. **The research ecosystem**: arXiv, conferences (NeurIPS, ICML, ICLR, ACL), technical reports of companies, citation graphs.
9. **Writing**: clear sentences, active voice, one idea per sentence, precise numbers; the format of a logbook entry and of a LinkedIn post.

## Practice

- One short text per day in English (documentation page, blog post, abstract), with new words added to the glossary.
- Guided reading of foundational papers chosen for their clarity, for example *Attention Is All You Need* (Vaswani et al., 2017) for its structure, and *Adam: A Method for Stochastic Optimization* (Kingma and Ba, 2014) for its algorithm box, each summarized in five sentences.
- Translating one equation of each paper into words and pseudo-code.
- Writing the first logbook entries of the project in English.

## Evaluation format

One session, about 2 hours: reading a short paper never seen before (a different one for each attempt) and answering questions on its structure, method, equations and results; a five-sentence summary to write; vocabulary and documentation questions. Pass mark 100 %.

## References

- S. Keshav, *How to Read a Paper* (short free article describing the three-pass method).
- arXiv.org, and Hugging Face Papers (papers linked to their code, models and datasets).
- The official documentation of the tools used in the project (Python, GNU, NVIDIA CUDA), read in English from the start.
