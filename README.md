# LLM from scratch

**Summary.** A personal project to build a modern large language model and everything around it from first principles: the mathematics, a tensor library with automatic differentiation, neural networks, tokenizers, image generation, data pipelines (down to a hand-written TLS 1.3 client and compression decoders), the Transformer and its modern variants, a C and CUDA engine with hand-written GPU kernels, an inference engine, distributed training, pre-training, post-training (instruction tuning, preference optimization, reinforcement learning for reasoning), and the harness that turns a model into a product: sessions, token accounting, context compression, effort levels, tools, agents, skills, plug-ins, artifacts, a terminal chat and a web chat. No third-party library is used anywhere: every component is written by hand, with a pure Python reference first, then a fast C and CUDA implementation. The project is split into two learning plans, followed in order: a **prerequisites** plan that starts from zero, and an **LLM** plan that builds the full stack.

## Contents

1. [Goal](#goal)
2. [From-scratch policy](#from-scratch-policy)
3. [How the project runs](#how-the-project-runs)
4. [Evaluations](#evaluations)
5. [Progress tracking, logbook and posts](#progress-tracking-logbook-and-posts)
6. [Hardware](#hardware)
7. [Legal framework](#legal-framework)
8. [Repository layout](#repository-layout)
9. [Use of AI in this project](#use-of-ai-in-this-project)
10. [Contributors](#contributors)

## Goal

Acquire every piece of technical knowledge needed to write, train and serve a modern language model from scratch, reading and generating text and images, so that the code base could, given the same volume of training data and compute, follow the published recipes of frontier models. Three honest caveats frame this goal:

- The exact recipes of closed frontier models are not public. The LLM plan covers the published state of the art; reaching frontier quality also requires thousands of GPUs and large amounts of human feedback data, which the plan accounts for in a scale-up dossier (module L69) rather than pretending a single machine can do it.
- Everything is built and validated at small scale on a single laptop GPU; the distributed parts are simulated with several processes until real hardware is available.
- Images are both an input (understanding screenshots, documents, photos) and an output (generation by diffusion and by native image tokens); audio is out of scope.

## From-scratch policy

The rule: the platform (hardware, operating system, compilers, drivers) may be used; every algorithm of the stack is written by hand. Imports are checked against an allowlist by a script written in module L00.

| Allowed | Not allowed in the project's code |
|---|---|
| Python built-ins and plumbing modules: `os`, `sys`, `io`, `time`, `struct`, `ctypes`, `mmap`, `socket`, `select`, `selectors`, `asyncio`, `threading`, `multiprocessing`, `subprocess`, `signal`, `termios`, `tty`, `argparse`, `logging`, `unittest`, `pathlib`, `shutil`, `tempfile`, `dataclasses`, `typing`, `enum`, `functools`, `itertools` | Any third-party package (NumPy, PyTorch, JAX, SciPy, tokenizer, HTTP or image libraries); and standard modules that implement an algorithm of the stack: `math`, `random`, `statistics`, `re`, `json`, `heapq`, `bisect`, `hashlib`, `hmac`, `secrets`, `base64`, `ssl`, `urllib`, `http`, `zlib`, `gzip`, `zipfile`, `sqlite3`, `unicodedata` (each one is rewritten by hand) |
| C standard library and POSIX (`malloc`, `pthread`, `mmap`, sockets) | `libm` software functions (`expf`, `logf`, ...), BLAS, LAPACK, OpenMP runtime, any third-party C library |
| Hardware instructions and the compiler intrinsics that map to them (AVX2, FMA, F16C, `sqrtss`; CUDA `__expf`, `ex2.approx`, PTX) | |
| CUDA toolkit as a platform: `nvcc`, NVRTC, runtime and driver APIs, headers that only wrap hardware types and instructions (`cuda_fp16.h`, `cuda_bf16.h`, `mma.h`, `cooperative_groups`, `cuda_pipeline`), profiling tools (Nsight, NVTX) | cuBLAS, cuDNN, CUTLASS, CUB, Thrust, libcu++, cuRAND, NCCL, Triton |
| Operating system entropy (`os.urandom`, `getrandom`), and the RDMA verbs driver interface on a real cluster | |
| HTML, CSS and JavaScript as provided by the browser | Front-end and CSS frameworks |
| Data: datasets and published open-weight models (loaded by the author's own code) | |
| External programs run as **test oracles** only, never imported or linked (for example a reference implementation that produces expected outputs once) | |

Every algorithmic component is first written in pure Python to understand it, then rewritten in C or CUDA when speed matters, and the fast version is always validated against the Python reference. Standard functions such as `math.exp` remain usable inside tests, as references for the copy-cats.

## How the project runs

- **Order**: the prerequisites plan ([prerequisites/README.md](prerequisites/README.md)) comes first and is complete only once its final evaluation is passed; the LLM plan ([llm/README.md](llm/README.md)) follows.
- **Teaching mode**: all work is done with Claude Code in `/professor` mode: explanations, questions and progressive hints, never a ready-made solution. Learning sessions happen in French; every document in this repository is in English.
- **Practice**: each module combines theory with programs to complete or to write from zero, on cases that differ from the module evaluation.
- **No assumptions about prior knowledge**: the prerequisites start from arithmetic. Any module can be skipped by passing its evaluation directly, so nothing is assumed and no time is wasted on what is already mastered.
- **Refreshers**: before each part of the LLM plan, a short check of the prerequisites it relies on; a gap sends back to the review of the module concerned.

## Evaluations

- **Module evaluation**: a module is validated only by passing its evaluation, which tests every competence listed in the module file, in the format the module defines (exercises, derivations, code, explanation).
- **Generated on the spot**: evaluation exercises are created at evaluation time in `/professor` mode, never written in advance, and checked against the exercise log.
- **Never the same exercise**: an exercise counts as already seen if it repeats an earlier statement, or if its answer could be reproduced from memory of an earlier exercise (same structure with the same values or the same context). Testing the same competence with a new context and new values, so that the answer must be worked out again, is allowed.
- **Pass mark**: 100 %. A failed evaluation leads to a targeted review, then a new evaluation made of new exercises.
- **Direct evaluation**: before starting a module, its evaluation can be taken directly; passing it validates the module. In the LLM plan it replaces the learning only, never the deliverable: the module's code must exist and pass its tests.
- **Final evaluation of the prerequisites**: one session per track (several for mathematics), testing every competence of every module at least once with new exercises, each session at 100 %. A failed session is retaken alone, with new exercises, after a review; the final evaluation is passed when every session is.

## Progress tracking, logbook and posts

- `progress/modules.md`: validated modules with their dates.
- `progress/exercises/<module>.md`: every learning and evaluation exercise of the module (date, kind, competence, structure, context and values), so that none is ever reused.
- `logbook/YYYY-MM-DD.md`: one file per working day, one section per session, for the portfolio: what was done, how, what blocked, what was decided, what was measured, what was learned. Each entry is drafted by Claude from the session, then corrected and validated by the author.
- `posts/`: LinkedIn post drafts, one per milestone (a block of modules validated, a first model trained, a measured result), written from the logbook.

## Hardware

Development machine: NVIDIA GeForce RTX 3070 Laptop GPU (Ampere, compute capability 8.6, 8 GB of memory), AMD Ryzen "Rembrandt" processor (8 cores, 16 threads, AVX2, FMA and F16C, no AVX-512), 14 GB of RAM, about 160 GB of free disk space, Linux, Python 3.12, GCC 12; the CUDA toolkit is installed in module SY03. Renting cloud GPUs is discussed in module SY05 and decided in module L38, once training costs can be estimated; until then, everything runs on this machine.

## Legal framework

The obligations of the EU AI Act (Regulation 2024/1689) for providers apply when a model or an AI system is placed on the market or put into service; a personal project that stays private is outside them, and so is work done solely for scientific research. Publishing the model or opening the chat to other people changes that: users must be told they are talking to an AI system, generated images must carry a machine-readable mark, providers of general-purpose AI models carry documentation and copyright obligations, and models trained with more than 10²⁵ floating-point operations are presumed to carry systemic risk, with further duties. Training data raises copyright, licence and GDPR questions of its own. Module L68 covers all of this in detail.

## Repository layout

| Path | Content |
|---|---|
| `prerequisites/` | Prerequisites plan: module definitions |
| `llm/` | LLM plan: module definitions |
| `progress/` | Validated modules and exercise logs |
| `logbook/` | Daily logbook for the portfolio |
| `posts/` | LinkedIn post drafts |
| `src/`, `tests/`, `tools/`, `docs/` | Code of the LLM plan, its tests, helper scripts and technical documentation (created in module L00) |

Datasets and model weights are stored outside the repository.

## Use of AI in this project

Claude Code (Anthropic) designed the two learning plans with the author (an independent review by a second Claude agent found missing topics and ordering errors, all fixed), acts as a teacher in `/professor` mode (explanations, hints, evaluations generated on the spot), and drafts logbook entries and post drafts that the author corrects and validates. All code of the model and its tools is written by the author.

## Contributors

- Louis Cagnion
