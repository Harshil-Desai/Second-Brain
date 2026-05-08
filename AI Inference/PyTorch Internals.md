---
date: 2026-05-07
tags: [ai-inference, pytorch, framework, internals]
source: ""
status: fleeting
---

# PyTorch Internals

> Empty for now. Notes go here as I read.

## Things to capture

- [ ] Tensor — storage, strides, dtype, device
- [ ] Autograd — graph, backward, leaf vs non-leaf
- [ ] Dispatcher and operator registration
- [ ] ATen and the C++ backend
- [ ] CUDA kernels in PyTorch — how a `.cuda()` call actually runs
- [ ] `torch.compile`, TorchInductor, FX graphs
- [ ] How PyTorch interacts with cuDNN/cuBLAS
- [ ] Inference vs training mode (no_grad, eval)

Related: [[GPU Fundamentals]], [[CUDA Fundamentals]]
