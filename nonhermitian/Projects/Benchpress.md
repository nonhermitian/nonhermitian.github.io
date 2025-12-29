
---
topic: software
tags:
  - projects
---

# Benchpress

![[../imgs/projects/benchpress.png | 600]]

## Collaborators

[Abdullah Ash Saki](https://www.linkedin.com/in/ashsaki/), [Sebastian Brandhofer](https://www.linkedin.com/in/sebastian-brandhofer/), [Luciano Bello](https://www.linkedin.com/in/1ucian0/), [Shelly Garion](https://www.linkedin.com/in/shelly-garion-16351296/), [Matthew Treinish](https://www.linkedin.com/in/matthew-t-a0973741/) , and Ali Javadi

## Summary

Benchpress is a framework for evaluating the performance of quantum computing software in the areas of quantum circuit construction, manipulation, and optimization (compilation).  We created a test suite of over 1000 tests, both from ourselves and other open-source tools, and ran them over 7 different software frameworks to determine which has the best overall performance in terms of output circuit quality (number of 2Q gates and depth) and run time (wall-clock time).

In short, Qiskit was the winner in terms of both quality and run time by a fair amount, followed by [Tket](https://github.com/Quantinuum/tket) from Quantinuum.  However, since our initial work, [qpanda3](https://qcloud.originqc.com.cn/document/qpanda-3/index.html) from OriginQC has become the closest competitor to Qiskit.

## Motivation

Several groups (including ourselves) were claiming that their SDK was the most performant choice.  However, no one really bothered to do a meaningful head-to-head comparison.  Such benchmarks are complicated by the fact that there are disparate feature sets amongst SDKs, and some tests require re-coding in each language.  We later found that many SDKs also fail tests, sometimes in ways that are difficult to capture, e.g. a test that seemingly runs forever, or tests that eat all available memory.  With Benchpress we tackled these issues head on, and created a testing framework that allows for (almost) straightforward testing of quantum software.

## Possible extensions

Currently, Benchpress does not test SDKs that use functions to represent quantum circuits.  Examples include [cudaq](https://github.com/NVIDIA/cuda-quantum) from Nvidia and [PennyLane](https://github.com/PennyLaneAI/pennylane) from Xanadu.  Unlike SDKs that represent quantum circuits as objects, it is not straightforward to extract the needed data from these workflows.

## Related Links

- Source code: [github.com/Qiskit/benchpress](https://github.com/Qiskit/benchpress)
- Paper: [Nat. Comput. Sci., **5**, 427 (2025)](https://doi.org/10.1038/s43588-025-00792-y)
- ArXiv: [arXiv:2409.08844](https://doi.org/10.48550/arXiv.2409.08844)
