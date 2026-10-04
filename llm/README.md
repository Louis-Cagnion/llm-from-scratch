# LLM plan

**Summary.** Builds a modern language model that reads and generates text and images, and its whole ecosystem, from scratch, once the [prerequisites](../prerequisites/README.md) are validated. The plan goes from the most fundamental to the least: first the shortest path to a **working text model** you can chat with (numerical foundations, classic machine learning, text data, the Transformer, a C and CUDA engine with hand-written kernels, pre-training, evaluation, supervised fine-tuning), then every extension, each one using only what precedes it: an inference engine able to run published open-weight models, modern architectures, scaling out and web-scale data (down to a hand-written TLS 1.3 client), serving and the harness (sessions, token accounting, context compression, terminal chat, web chat, artifacts, tools, agents, skills, plug-ins), advanced post-training (preferences, reinforcement learning for reasoning, tool use, safety, distillation, effort levels and model types), and finally multimodality (image understanding, then image generation). 70 modules in fourteen parts, ending with a complete model served by the author's own stack and a dossier for training it at frontier scale.

## Contents

1. [How to follow this plan](#how-to-follow-this-plan)
2. [Part 0: project setup](#part-0-project-setup)
3. [Part I: numerical foundations in pure Python](#part-i-numerical-foundations-in-pure-python)
4. [Part II: classic machine learning](#part-ii-classic-machine-learning)
5. [Part III: text and data basics](#part-iii-text-and-data-basics)
6. [Part IV: the text Transformer](#part-iv-the-text-transformer)
7. [Part V: fast engine in C and CUDA](#part-v-fast-engine-in-c-and-cuda)
8. [Part VI: a first working text model](#part-vi-a-first-working-text-model)
9. [Part VII: inference and open-weight models](#part-vii-inference-and-open-weight-models)
10. [Part VIII: modern architectures](#part-viii-modern-architectures)
11. [Part IX: scaling out and web-scale data](#part-ix-scaling-out-and-web-scale-data)
12. [Part X: serving, harness and applications](#part-x-serving-harness-and-applications)
13. [Part XI: advanced post-training](#part-xi-advanced-post-training)
14. [Part XII: multimodality](#part-xii-multimodality)
15. [Part XIII: framework and synthesis](#part-xiii-framework-and-synthesis)

## How to follow this plan

- Parts and modules follow each other in order, from the most fundamental to the least: each module only uses what the modules before it built. Each module will get its own file (`llm/L13-attention.md`) with objectives, the competences its evaluation tests, notions, the program to build, references (papers to read) and its validation.
- A module is validated by its deliverable (code written by the author, tests passing, measurements reported) and by an understanding evaluation that follows the protocol of the [main README](../README.md#evaluations). Direct evaluation replaces the learning, never the deliverable.
- Before each part, a short refresher checks the prerequisites the part relies on.
- Every component exists first in pure Python (reference), then in C or CUDA where speed matters, validated against the reference: bit-exact where the order of operations is fixed, within a measured ULP tolerance where SIMD, threads or atomics reorder them.
- Part IV runs at toy scale in pure Python; its model is retrained at a useful scale once the GPU backend exists (L20).
- Capabilities a small home-trained model cannot provide (following complex instructions, calling tools reliably, judging answers, generating synthetic data, teaching a student model) come from a published open-weight model loaded by the author's own engine (L28), treated as data.
- Every milestone feeds the logbook and, when it is a highlight, a LinkedIn post. The end of Part VI (first chat with one's own model) is the first major one.

## Part 0: project setup

- **L00. Project setup**: repository layout (`src/`, `tests/`, `tools/`, `docs/`, data and weights outside the repository), import allowlist and policy check script, test harness, Git hooks running the tests and the policy check before each commit, experiment log, hand-made plotting (SVG and terminal charts), external test oracles, coding conventions.

## Part I: numerical foundations in pure Python

- **L01. Math library**: hand-written exp, log, sqrt, pow, sin, cos, tanh, erf, sigmoid, exact and approximate GELU, accuracy measured in ULP against `math`; pseudo-random generator (PCG), uniform, normal and categorical sampling checked with chi-square tests, random permutations.
- **L02. Tensors**: flat storage, shape, strides, zero-copy views (reshape, transpose, permute, slicing), broadcasting, element-wise operations, reductions, matrix product, emulated float32, float16 and bfloat16 (rounding), serialization.
- **L03. Automatic differentiation**: computation graph, reverse mode, topological sort, backward rule of every operation (broadcasting and reductions included), gradient accumulation, no-grad mode, finite-difference checking, recomputation (activation checkpointing), forward mode (Jacobian-vector products) for comparison.
- **L04. Modules, parameters and initialization**: Module and Parameter abstractions, registration, state saving, a weight file format (JSON header and raw binary, loaded through `mmap`), initialization schemes (Xavier, He, depth-scaled) derived from variance propagation.
- **L05. Optimizers and the training loop**: SGD, momentum, Adam, AdamW, gradient clipping, learning-rate schedules (warmup, cosine, warmup-stable-decay), gradient accumulation, data loader (batching, shuffling), training and evaluation loops, checkpoints and exact resumption.

## Part II: classic machine learning

- **L06. Linear models and unsupervised basics**: linear regression, logistic regression, softmax regression, cross-entropy derived from maximum likelihood, regularization, metrics, train, validation and test protocol, k-means, principal component analysis.
- **L07. Neural networks**: multilayer perceptron, activations (ReLU, GELU, SiLU), universal approximation, backpropagation derived by hand, vanishing and exploding gradients, normalization (BatchNorm, LayerNorm, RMSNorm), dropout, residual connections, MNIST read from its raw IDX files.
- **L08. Language models before Transformers**: n-grams, smoothing (Laplace, Kneser-Ney), perplexity, Bengio's neural language model, word embeddings (word2vec, negative sampling), RNN, LSTM, GRU, backpropagation through time, sequence-to-sequence with Bahdanau attention.

## Part III: text and data basics

- **L09. Unicode and regular expressions**: code points, UTF-8 encoded and decoded by hand, normalization forms (tables built from the Unicode data files), a hand-written regular expression engine (Thompson construction) sufficient for pre-tokenization.
- **L10. Tokenization**: byte-level BPE (efficient training and encoding with a hand-written heap), WordPiece, Unigram (EM algorithm), special tokens, chat templates, vocabulary size trade-offs, a fast C implementation, round-trip tests.
- **L11. Compression and data formats**: CRC32 and Adler-32, DEFLATE (decoder and encoder), gzip and zlib containers, Zstandard decoder (FSE and Huffman entropy coding), Snappy, Parquet (Thrift compact protocol, column chunks, pages), JSONL; enough to read published datasets.
- **L12. Data preparation basics**: a published text dataset downloaded by hand, exact deduplication (hashing), quality heuristics, benchmark decontamination, train and validation splits, tokenization into binary token shards read through `mmap`.

## Part IV: the text Transformer

- **L13. Attention**: scaled dot-product attention (and why 1/√d), causal mask, multi-head attention, backward pass by hand, quadratic cost.
- **L14. Decoder-only Transformer**: embeddings, position encodings (sinusoidal, learned, rotary derived from complex rotations, ALiBi), pre-normalization, RMSNorm, SwiGLU feed-forward, residual stream, tied input and output embeddings, sequence packing with intra-document attention masks, parameter and FLOP counts (6ND), memory budget; a small GPT trained on a small corpus.
- **L15. Generation and KV cache basics**: greedy decoding, temperature, top-k, top-p, min-p, beam search, repetition penalties, stop sequences, log-probabilities, sampling several answers (pass@k), a simple KV cache and the computation of its size.

## Part V: fast engine in C and CUDA

- **L16. C engine on the CPU**: storage and strided kernels, optimized matrix product (blocking, AVX2 and FMA, threads), fused kernels, caching allocator, Python bindings through `ctypes`, validation against the Python reference.
- **L17. CUDA I, basic kernels**: element-wise kernels, reductions (warp shuffles), online softmax, LayerNorm and RMSNorm (forward and backward), fused cross-entropy, embeddings, fused AdamW, GPU memory management.
- **L18. CUDA II, matrix product**: naive kernel, shared-memory tiling, register blocking, vectorized loads, asynchronous copies and double buffering, tensor cores (WMMA, then `ldmatrix` and `mma.sync` in PTX), fp32 accumulation, autotuning, percentage of the RTX 3070's theoretical peak.
- **L19. CUDA III, fast attention**: FlashAttention forward and backward (tiling, online softmax, recomputation), grouped-query and sliding-window variants.
- **L20. GPU training backend**: device tensors, dispatch of automatic differentiation to the CUDA kernels, kernel launch overhead from Python, memory pool, end-to-end GPT training on the GPU matched against the Python reference, retraining the Part IV model at a useful scale.
- **L21. Mixed-precision training**: fp16 and bf16 training with fp32 master weights, loss scaling, stochastic rounding, numerical failure modes.
- **L22. Training throughput and memory**: activation recomputation, gradient accumulation, 8-bit optimizer states, optimizer state offloading to the CPU, overlapping computation and transfers with streams, profiling (Nsight), model FLOPs utilization, fitting a training run into 8 GB.

## Part VI: a first working text model

- **L23. End-to-end pre-training**: a complete small text model trained on the development machine (tokenizer, data, training, loss curves, gradient norms), ablations, recovery after an incident.
- **L24. Evaluation basics**: perplexity, a hand-written evaluation harness, knowledge, reasoning, mathematics and code benchmarks suited to small models (code run in a sandbox), contamination, confidence intervals.
- **L25. Supervised fine-tuning and a first chat**: conversation format (roles, special tokens, system prompt), loss masking on answers, packing, public instruction datasets, LoRA and QLoRA, and a minimal terminal loop to chat with one's own model (first major milestone).

## Part VII: inference and open-weight models

- **L26. Inference engine**: prefill and decode, continuous batching, chunked prefill, paged KV cache and its attention kernel, prefix caching (prompt caching), CPU inference, metrics (time to first token, throughput).
- **L27. Quantization for inference**: int8 and int4 weights (absmax, zero-point, group-wise), GPTQ, AWQ, rotation-based quantization, KV cache quantization, quantized matrix-vector kernels, weight and KV cache offloading beyond 8 GB.
- **L28. Loading open-weight models**: safetensors parsing, tokenizer files (`tokenizer.json`, BPE ranks), chat templates rendered by the IN12 template engine, mapping a published architecture onto the engine, quantization to fit 8 GB, validation of logits against reference outputs produced once by an external implementation used as a test oracle.
- **L29. Structured generation and speculative decoding**: constrained decoding (grammars, JSON Schema) with the IN12 parsers, structured outputs, speculative decoding with a draft model (a small home-trained model or a smaller open model sharing the tokenizer), multi-head drafting principles (Medusa, EAGLE).

## Part VIII: modern architectures

- **L30. Modern variants**: multi-query, grouped-query and multi-head latent attention, sliding windows, QK-norm, z-loss and logit soft-capping, parallel blocks, maximal update parametrization (μP), mixture of experts (top-k router, load balancing with and without auxiliary loss, capacity, fine-grained and shared experts), multi-token prediction, alternatives (linear attention, state-space models such as Mamba with their 1D convolutions, hybrid architectures).
- **L31. CUDA IV, mixture-of-experts and state-space kernels**: token dispatch, grouped matrix products and combine; selective scan for Mamba; parallel associative scans; mixture-of-experts inference.
- **L32. Long context**: extending rotary embeddings (position interpolation, NTK-aware scaling, YaRN), progressive length training, attention sinks, KV cache compression, evaluation (needle in a haystack).
- **L33. Modern optimizers and low-precision formats**: Lion, Adafactor, Muon (Newton-Schulz orthogonalization), Shampoo and SOAP, simulated fp8 and microscaling formats (the RTX 3070 has no fp8 tensor cores).
- **L34. Graph compilation**: intermediate representation, operator fusion, memory planning, CUDA kernel generation from the graph (through NVRTC), autotuning, CUDA graphs.

## Part IX: scaling out and web-scale data

- **L35. Hand-written collective communication**: ring and tree all-reduce, all-gather, reduce-scatter, all-to-all between processes over sockets and shared memory (replaces NCCL), GPU-aware transfers (CUDA IPC, peer access), measured against the cost model.
- **L36. Parallelism strategies**: data parallelism (DDP, gradient buckets, overlap), ZeRO stages 1 to 3 and FSDP, tensor parallelism (Megatron column and row splits), sequence and context parallelism (ring attention), pipeline parallelism (GPipe, 1F1B, interleaved), expert parallelism (all-to-all), 3D and 4D combinations, choosing a layout for a given budget.
- **L37. Training infrastructure**: sharded checkpoints, elastic restart, loss spikes (detection, rollback), monitoring, determinism, cluster schedulers (Slurm principles), storage throughput, interconnects on a real cluster (NVLink, InfiniBand, RDMA through the verbs interface, GPUDirect), cost and energy.
- **L38. Scaling laws**: Kaplan and Chinchilla (compute-optimal parameters and tokens, derivation, parametric fit with L-BFGS and a Huber loss), fitting one's own laws on small models, extrapolation, critical batch size and gradient noise scale, hyperparameter transfer (μP), estimating the budget of a frontier model, and the informed decision on renting cloud GPUs (with SY05).
- **L39. TLS 1.3 client and HTTPS**: a TLS 1.3 client built on the IN14 primitives (X25519, AES-GCM, SHA-256, HKDF, RSA and ECDSA verification, certificate chain validation against the system trust store, SNI, ALPN), the HTTP/1.1 client running over it (redirects, chunked transfer, range requests and resumption), a robust downloader (retries, rate limits, checksums).
- **L40. Web data collection and extraction**: web formats (WARC, WET), a hand-written HTML parser (tokenizer state machine and tree building), text extraction, robots.txt, language identification (hand-written classifier), code, mathematics, books, multilingual data, published datasets stored as Parquet.
- **L41. Filtering, deduplication and mixtures at scale**: quality classifier, near-duplicate detection (MinHash, LSH), personal data removal, toxicity filtering, decontamination at scale, mixture proportions and their search with small proxy models (DoReMi and RegMix style), curriculum.
- **L42. Pre-training recipe at scale**: the full data pipeline feeding a larger run, mid-training and annealing on high-quality data, synthetic rephrased data generated with the open-weight model, ablations at scale.

## Part X: serving, harness and applications

- **L43. API server**: a messages API (roles, system prompt, tools, files) on the hand-written HTTP server, SSE streaming, API keys, rate limiting, token counting and billing (input, output, cached), request queue, routing between models, serving several LoRA adapters, timeouts, moderation hooks, logs with secret redaction, errors.
- **L44. Prompts and context**: system prompt, context assembly, examples, templates, token budgets, interaction with prompt caching, context engineering.
- **L45. Sessions and conversations**: message format, persistence (JSONL, session identifiers, resuming), history and search, branching, editing and regenerating, export, token counts per session, context window management, compression of long sessions (hierarchical summaries, compaction), memory across conversations.
- **L46. Terminal chat**: raw terminal mode (`termios`), line editing and history, Unicode display width, window resizing (`SIGWINCH`), Markdown rendered with ANSI sequences and syntax highlighting, streamed display, slash commands, model selection, token and cost display, clean interruption.
- **L47. Web chat application**: HTTP and SSE server, HTML, CSS and JavaScript interface without frameworks, safe Markdown rendering (XSS), code blocks, conversation list, branching and regeneration, file attachments (multipart uploads, text files, a hand-written PDF text extractor), settings, loading and error states, export.
- **L48. Artifacts**: standalone content produced by the model (HTML and JavaScript pages and small applications, SVG, documents, code, charts and diagrams rendered by hand-written renderers) displayed in a side panel of the web application, artifact format in the model's output (or as a tool call), sandboxed rendering (iframe sandbox, Content Security Policy, separate origin, `postMessage`), versions and updates by targeted edits, persistence and sharing through stable URLs on the hand-written server, a runtime offered to artifacts (persistent storage, calling the model from inside an artifact), fallback in the terminal (saved to a file, opened in the browser).
- **L49. Tools in the harness**: tool definitions (JSON Schema), call parsing, execution loop, parallel calls, error handling, file reading and editing tools (Myers diff and patch), permissions, execution sandbox, human approval.
- **L50. Agents**: agent loop (ReAct, plan then execute), short- and long-term memory, retrieval (hand-trained text embedding model with contrastive learning, exhaustive vector index, HNSW, IVF and product quantization with k-means, inverted index and BM25, hybrid search), retrieval-augmented generation (chunking, reranking, citations), subagents and orchestration, context isolation, stopping criteria, cost control, agent evaluation, safety (injections coming from tool results).
- **L51. Skills, plug-ins and the tool protocol**: skill format (instructions and resources loaded on demand), skill selection, plug-in architecture (manifest, loading, event hooks, isolation, versions), an MCP-like protocol (JSON-RPC over stdio and HTTP, client and server), permission model.

## Part XI: advanced post-training

- **L52. Synthetic data and advanced fine-tuning**: instruction and conversation data generated with the open-weight model (including tool calls and the creation and update of artifacts), quality filtering of synthetic data, continued pre-training and domain adaptation, model merging (including Fisher-weighted merging).
- **L53. Chat evaluation**: the open-weight model as a judge, its biases, pairwise comparisons, Elo ratings, human preference collection.
- **L54. Reward models and RLHF**: preference data (hand-written annotation tool), Bradley-Terry reward model, policy gradient (REINFORCE derived), PPO (clipped objective, generalized advantage estimation, value function, KL penalty), fitting PPO's four models into 8 GB (shared backbone, LoRA, offloading), stability.
- **L55. Direct preference optimization and constitutional AI**: DPO derived from the RLHF objective, IPO, KTO, ORPO, SimPO, offline versus online preference optimization, AI feedback (RLAIF) from the open-weight model, critique and revision against a constitution.
- **L56. Reinforcement learning infrastructure**: rollout workers on the L26 inference engine, weight synchronization between trainer and generator, off-policy corrections, rejection sampling and best-of-N fine-tuning, reward hacking and over-optimization (detection, mitigation).
- **L57. Reasoning**: chain of thought, test-time compute, reinforcement learning with verifiable rewards (math and code checkers), GRPO and its variants (DAPO, Dr GRPO), process and outcome reward models, self-consistency, extended thinking with a token budget.
- **L58. Tools and agents in training**: function-calling data in the L49 format, JSON Schema adherence, design of reinforcement learning environments from the L50 agents, agentic reinforcement learning, computer use (principles).
- **L59. Safety and alignment**: intended behavior (constitution), calibrated refusals, red teaming, robustness to jailbreaks and prompt injection, input and output moderation classifiers, honesty and calibration, dangerous capability evaluations, interpretability (probes, sparse autoencoders), text watermarking, model card.
- **L60. Distillation and model families**: logit distillation from the open-weight teacher, a family of sizes (small and fast, large and capable), pruning, draft models for speculative decoding.
- **L61. Effort levels and model types**: effort as a thinking budget (from L57), adaptive thinking, routing between the model sizes of L60, cost, latency and quality trade-offs, fallback, their integration in the API, the terminal chat and the web chat.
- **L62. Observability and the product loop**: traces of agent runs, cost tracking, user feedback (ratings, preferences) fed back into training, A/B tests.

## Part XII: multimodality

- **L63. Images: decoding and encoding**: PNG decoder and encoder (on the L11 DEFLATE), JPEG decoder and encoder (Huffman coding, DCT and inverse DCT, quantization), resizing (interpolation and resampling filters), normalization, augmentations, image-text pair datasets.
- **L64. Image understanding**: convolutions (2D, im2col, pooling) and convolutional networks, vision Transformer (patches), CLIP-style contrastive training (InfoNCE), connecting an image encoder to the language model (projector, image tokens), high resolution through tiling, multimodal training stages and instruction data, multimodal evaluation.
- **L65. Image generation: autoencoders, diffusion and flow matching**: variational autoencoders (ELBO), denoising diffusion (forward noising, noise-prediction objective derived, DDPM), score matching and the stochastic differential equation view, deterministic samplers (DDIM, Euler, Heun, DPM-Solver), flow matching and rectified flow, U-Net and Diffusion Transformer (DiT) denoisers, conditioning on classes and on text (cross-attention), classifier-free guidance, latent diffusion, first at toy scale then on the GPU.
- **L66. Image generation at scale and native image output**: training a small text-to-image latent diffusion model, discrete image tokens (VQ-VAE codebooks) and native image generation by the language model itself (early fusion, unified models), image editing and inpainting, evaluation (FID with a hand-trained feature network, CLIP score with the L64 model, human preference).
- **L67. Multimodality in the applications**: image input and generated images in the API, the web chat (uploads, display) and artifacts, terminal fallback (files opened in the browser), filtering of generated images, provenance marking (C2PA) and invisible watermarks.

## Part XIII: framework and synthesis

- **L68. Legal framework and responsibility**: EU AI Act (risk levels, obligations of general-purpose model providers, systemic-risk threshold of 10²⁵ FLOPs, research exclusion, chatbot transparency, machine-readable marking of synthetic images and disclosure of deepfakes), copyright and text and data mining (EU exception, rights-holder opt-outs), GDPR (training data, stored conversations), licences of datasets, weights and code, and what changes between publishing code only and publishing weights.
- **L69. Final project**: a complete model reading and generating text and images, trained with the whole stack (tokenizer, pre-training, supervised fine-tuning, preference optimization, small-scale reasoning, tools, image understanding and generation), served by the author's inference engine and used from the terminal and the web application with agents, skills, plug-ins and artifacts; plus the scale-up dossier (compute, data, parallelism layout, budget, schedule, risks) extrapolated from the author's own scaling laws.
