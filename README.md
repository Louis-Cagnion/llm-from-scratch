# LLM from scratch

**Summary.** A modern language model and everything around it, built by hand from first principles: no NumPy, no PyTorch, no library at all. The journey starts from basic arithmetic and ends with a model that reads and generates text and images, trained on hand-written CUDA kernels and served through a terminal chat and a web chat with agents, tools and artifacts. Every step is learned, built and documented in public, module by module.

## Contents

1. [Goal](#goal)
2. [Features](#features)
3. [Architecture](#architecture)
4. [From-scratch policy](#from-scratch-policy)
5. [Requirements and tools](#requirements-and-tools)
6. [Getting started](#getting-started)
7. [How the project runs](#how-the-project-runs)
8. [Evaluations](#evaluations)
9. [Progress tracking, logbook and posts](#progress-tracking-logbook-and-posts)
10. [Status](#status)
11. [Legal framework](#legal-framework)
12. [Repository layout](#repository-layout)
13. [Use of AI in this project](#use-of-ai-in-this-project)
14. [Contributors](#contributors)

## Goal

Acquire every piece of technical knowledge needed to write, train and serve a modern language model from scratch, so that the code base could, given the same volume of training data and compute, follow the published recipes of frontier models. The work follows two learning plans in order: a [prerequisites plan](prerequisites/README.md) that starts from zero, and an [LLM plan](llm/README.md) that builds the full stack, from the most fundamental component to the least. Three honest caveats frame this goal:

- The exact recipes of closed frontier models are not public. The LLM plan covers the published state of the art; reaching frontier quality also requires thousands of GPUs and large amounts of human feedback data, which the plan accounts for in a scale-up dossier (module L69) rather than pretending a single machine can do it.
- Everything is built and validated at small scale on a single laptop GPU; the distributed parts are simulated with several processes until real hardware is available.
- Images are both an input (understanding screenshots, documents, photos) and an output (generation by diffusion and by native image tokens); audio is out of scope.

## Features

What the finished system does, each feature built in the LLM plan module given in brackets:

- **Model**: decoder-only Transformer with rotary embeddings, RMSNorm and SwiGLU (L14), modern attention variants, mixtures of experts, state-space layers and long context (L30 to L32), image understanding (L64) and image generation (L65, L66).
- **Training**: hand-written tensors and automatic differentiation (L02, L03), C and CUDA engine with hand-written kernels including FlashAttention (L16 to L22), mixed precision and 8 GB memory techniques (L21, L22), data, tensor, pipeline and expert parallelism with hand-written collectives (L35, L36), scaling laws (L38).
- **Data**: tokenizers (L10), compression decoders (L11), TLS 1.3 client (L39), web crawling and extraction (L40), filtering, deduplication and mixtures (L41).
- **Post-training**: supervised fine-tuning (L25, L52), reward models and RLHF (L54), direct preference optimization and constitutional AI (L55), reinforcement learning for reasoning (L56, L57), tool use (L58), safety (L59), distillation into a family of model sizes (L60).
- **Inference**: KV cache, continuous batching, paged attention and prefix caching (L26), quantization (L27), loading of published open-weight models (L28), structured outputs and speculative decoding (L29).
- **Product**: messages API with streaming and token billing (L43), sessions, history and compression of long conversations (L45), terminal chat (L46), web chat (L47), artifacts (L48), tools, agents, skills and plug-ins (L49 to L51), effort levels and model types (L61), multimodal input and output in the applications (L67).

## Architecture

The software stack, from the bottom layer up; each layer only uses the layers below it:

| Layer | Components | Modules |
|---|---|---|
| Numerical core | Math library, pseudo-random numbers, tensors, automatic differentiation, modules, optimizers | L01 to L05 |
| Engines | C engine on the CPU, CUDA kernels, GPU training backend, graph compiler | L16 to L22, L31, L34 |
| Data | Unicode and regular expressions, tokenizers, compression and data formats, TLS and HTTPS, crawling, filtering, images | L09 to L12, L39 to L42, L63 |
| Models | Transformer and its variants, mixtures of experts, state-space models, vision encoders, diffusion models | L13 to L15, L30 to L32, L64 to L66 |
| Training | Pre-training, distributed training, evaluation, post-training | L23 to L25, L35 to L38, L52 to L60 |
| Inference | Inference engine, quantization, open-weight loading, structured generation | L26 to L29 |
| Product | API server, sessions, terminal and web chat, artifacts, tools, agents, skills, plug-ins, effort levels | L43 to L51, L61, L62, L67 |

Every algorithmic component exists twice: a pure Python reference, written first to understand it, and a C or CUDA version for speed, always validated against the reference.

## From-scratch policy

The rule: the platform may be used; every algorithm of the stack is written by hand. A script written in module L00 checks every import against an allowlist.

**Allowed**

- **The platform**: hardware instructions and the intrinsics that map to them (AVX2, FMA, F16C; CUDA `__expf`, PTX), the operating system (system calls, entropy from `os.urandom`), compilers and drivers.
- **Python plumbing**: files and processes (`os`, `sys`, `io`, `pathlib`, `shutil`, `tempfile`, `subprocess`, `signal`), binary data (`struct`, `ctypes`, `mmap`), networking and concurrency (`socket`, `select`, `selectors`, `asyncio`, `threading`, `multiprocessing`), the terminal (`termios`, `tty`), tooling (`argparse`, `logging`, `unittest`, `time`), language helpers (`dataclasses`, `typing`, `enum`, `functools`, `itertools`).
- **C**: the standard library and POSIX (`malloc`, `pthread`, `mmap`, sockets).
- **CUDA toolkit**: `nvcc`, NVRTC, the runtime and driver APIs, the headers that only wrap hardware types and instructions (`cuda_fp16.h`, `cuda_bf16.h`, `mma.h`, `cooperative_groups`, `cuda_pipeline`), the profilers (Nsight, NVTX).
- **The browser**: HTML, CSS and JavaScript as it provides them.
- **Data**: datasets and published open-weight models, loaded by the author's own code; on a real cluster, the RDMA verbs driver interface.
- **Test oracles**: external programs run once to produce expected outputs, never imported or linked.

**Rewritten by hand, never imported**

- Every third-party package: NumPy, PyTorch, JAX, SciPy, tokenizer, HTTP and image libraries.
- The standard Python modules that implement an algorithm of the stack: `math`, `random`, `statistics`, `re`, `json`, `heapq`, `bisect`, `hashlib`, `hmac`, `secrets`, `base64`, `ssl`, `urllib`, `http`, `zlib`, `gzip`, `zipfile`, `sqlite3`, `unicodedata`.
- In C: the software functions of `libm` (`expf`, `logf`, ...), BLAS, LAPACK, the OpenMP runtime, any third-party library.
- On the GPU: cuBLAS, cuDNN, CUTLASS, CUB, Thrust, libcu++, cuRAND, NCCL, Triton.
- In the browser: front-end and CSS frameworks.

Standard functions such as `math.exp` remain usable inside tests, as references for the hand-written copies.

## Requirements and tools

- **Operating system**: Linux (developed on Ubuntu 24.04).
- **Languages and compilers**: Python 3.12 (standard library only), GCC 12 and Make, the NVIDIA CUDA toolkit (`nvcc`, installed in prerequisite module SY03).
- **Other tools**: Git, a web browser, and Claude Code for the `/professor` sessions.
- **Development machine**: NVIDIA GeForce RTX 3070 Laptop GPU (Ampere, compute capability 8.6, 8 GB of memory), AMD Ryzen "Rembrandt" processor (8 cores, 16 threads, AVX2, FMA and F16C, no AVX-512), 14 GB of RAM, about 160 GB of free disk space. Renting cloud GPUs is discussed in module SY05 and decided in module L38, once training costs can be estimated.

## Getting started

1. Clone the repository: `git clone git@github.com:Louis-Cagnion/llm-from-scratch.git`.
2. Read the [prerequisites plan](prerequisites/README.md): its recommended sequence gives the first modules (MA01, MA02, MA03, IN01, IN02, ME01).
3. Open Claude Code at the root of the repository and activate `/professor`: Claude reads [CLAUDE.md](CLAUDE.md) and the progress files, then offers the next module or its direct evaluation.
4. Code starts with module L00 of the [LLM plan](llm/README.md), which sets up the source layout, the test harness and the policy check; this README then documents how to run them.

## How the project runs

- **Order**: the prerequisites plan comes first and is complete only once its final evaluation is passed; the LLM plan follows, from the most fundamental module to the least, with a first working text model you can chat with at the end of its Part VI.
- **Teaching mode**: all work is done with Claude Code in `/professor` mode: explanations, questions and progressive hints, never a ready-made solution. Learning sessions happen in French; every document in this repository is in English.
- **Practice**: each module combines theory with programs to complete or to write from zero, on cases that differ from the module evaluation.
- **No assumptions about prior knowledge**: the prerequisites start from arithmetic. Any module can be skipped by passing its evaluation directly, so nothing is assumed and no time is wasted on what is already mastered.
- **Refreshers**: before each part of the LLM plan, a short check of the prerequisites it relies on; a gap sends back to the review of the module concerned.

## Evaluations

- **Module evaluation**: a module is validated only by passing its evaluation, which tests every competence listed in the module file, in the format the module defines (exercises, derivations, code, explanation). LLM modules also require their deliverable: code written by the author, tests passing, measurements reported.
- **Generated on the spot**: evaluation exercises are created at evaluation time in `/professor` mode, never written in advance, and checked against the exercise log.
- **Never the same exercise**: an exercise counts as already seen if it repeats an earlier statement, or if its answer could be reproduced from memory of an earlier exercise (same structure with the same values or the same context). Testing the same competence with a new context and new values, so that the answer must be worked out again, is allowed.
- **Pass mark**: 100 %. A failed evaluation leads to a targeted review, then a new evaluation made of new exercises.
- **Direct evaluation**: before starting a module, its evaluation can be taken directly; passing it validates the module. In the LLM plan it replaces the learning only, never the deliverable.
- **Final evaluation of the prerequisites**: one session per track (several for mathematics), testing every competence of every module at least once with new exercises, each session at 100 %. A failed session is retaken alone, with new exercises, after a review; the final evaluation is passed when every session is.

## Progress tracking, logbook and posts

- `progress/modules.md`: validated modules with their dates.
- `progress/exercises/<module>.md`: every learning and evaluation exercise of the module (date, kind, competence, structure, context and values), so that none is ever reused.
- `logbook/YYYY-MM-DD.md`: one file per working day, one section per session, for the portfolio: what was done, how, what blocked, what was decided, what was measured, what was learned. Each entry is drafted by Claude from the session, then corrected and validated by the author.
- `posts/`: LinkedIn post drafts, one per milestone (a block of modules validated, a first model trained, a measured result), written from the logbook.

## Status

Both plans are designed (49 prerequisite modules, 70 LLM modules). The detailed module files of the prerequisites are being written stage by stage; stages 1 to 5 are available. Learning starts with stage 1 of the prerequisites.

## Legal framework

- **While the project stays private**, the EU AI Act (Regulation 2024/1689) imposes nothing: its obligations apply when a model or an AI system is placed on the market or put into service, and work done solely for scientific research is excluded.
- **Once the model or the chat is opened to others**, users must be told they are talking to an AI system, generated images must carry a machine-readable mark, and providers of general-purpose AI models carry documentation and copyright obligations.
- **Beyond 10²⁵ floating-point operations of training**, a model is presumed to carry systemic risk, with further duties.
- **Training data** raises copyright, licence and GDPR questions of its own.

Module L68 covers all of this in detail.

## Repository layout

| Path | Content |
|---|---|
| `prerequisites/` | Prerequisites plan and its module files |
| `llm/` | LLM plan and its module files |
| `progress/` | Validated modules and exercise logs |
| `logbook/` | Daily logbook for the portfolio |
| `posts/` | LinkedIn post drafts |
| `src/`, `tests/`, `tools/`, `docs/` | Code of the LLM plan, its tests, helper scripts and technical documentation (created in module L00) |
| `CLAUDE.md` | Instructions for the Claude Code sessions |

Datasets and model weights are stored outside the repository.

## Use of AI in this project

Claude Code (Anthropic) designs the two learning plans with the author, with an independent Claude agent reviewing them for missing topics and ordering errors; acts as a teacher in `/professor` mode (explanations, hints, evaluations generated on the spot); and drafts logbook entries and post drafts that the author corrects and validates. All code of the model and its tools is written by the author.

## Contributors

- Louis Cagnion
