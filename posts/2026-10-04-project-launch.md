> Draft, to publish once the rush01 Skyscraper solver is finished (one project at a time).

I'm starting the most ambitious learning project I've ever attempted: building a modern large language model entirely from scratch.

No NumPy. No PyTorch. No library at all. Every piece written by hand: the math library, tensors and autograd, tokenizers, the Transformer, CUDA kernels, distributed training, RLHF, an inference engine, and the product around it (sessions, agents, tools, skills, plug-ins, artifacts, a terminal chat and a web chat). It will read and generate images too.

The goal isn't to beat frontier labs with a laptop GPU (an RTX 3070 with 8 GB). It's to understand every component well enough that the code could follow the published frontier recipes, given the data and the compute.

So I'm starting from zero: 49 prerequisite modules (from arithmetic to matrix calculus, CUDA, compilers and TLS 1.3 cryptography), then 70 modules that build the stack, ordered so that I can chat with a first working text model before any extension.

First lesson, on day one: a model small enough to train on 8 GB can't reliably call tools, so building the agent harness means loading published open-weight models into my own engine. The code stays mine; the weights are just data.

The rule I'm most curious about: each module is validated only by an evaluation at 100 %, generated on the spot, never with an exercise I've already seen. My teacher is Claude Code, in a mode that explains and gives hints but never writes the solution.

Everything is public, plans included: https://github.com/Louis-Cagnion/llm-from-scratch

I'll post at each milestone.

#MachineLearning #LLM #DeepLearning #CUDA #LearningInPublic #FromScratch
