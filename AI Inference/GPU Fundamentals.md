---
date: 2026-05-07
tags: [ai-inference, gpu, hardware, fundamentals]
source: ""
status: fleeting
---

# GPU Fundamentals

> Empty for now. Notes go here as I read.

## Things to capture

- [x] CPU vs GPU architecture — why GPUs are good at parallel work
- [ ] Cores, warps, threads, blocks
- [ ] Memory hierarchy (HBM, L2, L1/SMEM, registers)
- [ ] Memory bandwidth vs compute (roofline thinking)
- [ ] How a GPU schedules work
- [ ] Common GPU lineups and what to know about each (consumer vs datacenter)

### CPU vs GPU architecture
CPU (Central Processing Unit) is made up of cores, a core is an independent execution unit. It can fetch, decode, execute and writeback an instruction into a pipeline. This means if there are 16 cores, you can run 16 independent programs at once. It is a general purpose processor. Each core is large and expensive, so having too many cores is not possible, so this is a bottleneck for CPUs, having limited number of cores.

Now when AI came this because a problem, training a neural network is not a complex task, its a simple task repeated multiple times. That simple task is matrix multiplication. We have a input matrix, which is multiplied with a weights matrix and we add bias matrix in the answer to get output matrix of 1 layer. If we do this same process few 100 times, we get 1 forward pass of a LLM. Operation is simple multiply and addition, but for LLMs we have to repeat this operation approx $10^{12}$ times. CPU can do this, but since we have limited CPU cores, it would take years to complete 1 training session.

So to tackle this problem, we don't need 16 smart cores, we need 16k dumb cores, which can do a trivial operation like addition and multiplication. GPU (graphics processing unit) fits the description, GPUs have limited instruction set, but large number of cores. It has blocks of cores, and every core inside a block runs same instruction, on different data. This is called SIMD (Single instruction multiple data). But GPU is still general purpose, it does graphics, AI, Physics, Crypto. Its not specifically optimized for anything.

Here comes [[TPUs]] in Picture.

Related: [[CUDA Fundamentals]], [[PyTorch Internals]]
