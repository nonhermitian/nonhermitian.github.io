
---
topic:  software
tags:
  - projects
---

# Mapomatic

![[../imgs/projects/mapomatic.png | 600]]

## Collaborators

[Matthew Treinish](https://www.linkedin.com/in/matthew-t-a0973741/)

## Summary

Dealing with the noise inherent in today’s nascent quantum computers is a very lively area of research. A large body of this work has centered on the suppression of errors through circuit-rewriting optimizations such as gate simplification, Pauli twirling, and dynamical decoupling, as well as scalable gate and measurement error-mitigation methods that allow for possible demonstrations of quantum advantage; the point at which executing one or more tasks on a quantum computer provides tangible benefits over classical computational methods. However, much less attention has been given to optimizing work flows for variations in qubit and gate quality across a quantum system. With processor sizes in the range of hundreds of qubits, these performance fluctuations can be nontrivial, with marked differences across the quantum processor. To date, addressing these circuit-layout issues is typically done at the beginning of a circuit-compilation work flow, when the final circuit structure is not yet determined, and where premature layout optimization can hinder later qubit-routing optimization; the final circuit output fidelity can be made worse.

Here, we take a different approach: remapping quantum circuits post-compilation to low-noise sections of the processor based on error estimates (cost functions) derived from system calibration data. This method relies on the ability to quickly (relative to other compilation run times) compute subgraphs of a quantum processor that match the entangling-gate topology of input circuits. The estimated error associated with executing the circuit on each subgraph is computed and the circuit is remapped to the lowest error layout for execution on hardware. Using common test circuits, we show that this technique is able to recover, on average, nearly 40% of the fidelity that is missing when executing circuits without remapping. This advantage persists across different families of circuits, showing the generality of our method. We take this a step further and consider circuit mapping across multiple quantum processors where additional improvements in output fidelity can be gained by relaxing _a priori_ device selection.

## Motivation

A [benchmarking paper](https://arxiv.org/abs/2110.03137) from the QED-C had come out that showed sub-par performance on IBM Quantum systems.  In investigating the issue, it turned out that using standard tooling, there was no way to get better performance, i.e. our devices did not perform as expected.  In short, the reason for this was the variability of performance across the devices.  This is an issue on platforms with manufactured qubits, such as the superconducting devices used by IBM and others.  We did not recognize this internally because people were always hand-mapping their circuits.  In contrast, most users were using Qiskit to find a set of qubits for them, and that was being done at random.  This project was the initial attempt to fix that issue and cheaply, but effectively, remap quantum circuits to the best performing part of one or more quantum processors.

## Possible Extensions

Here we used calibration data that is automatically generated one a day or so by the devices.  This works good in most cases, but does lead to bad performance occasionally.  The reason is because devices can drift between calibrations, leading to erroneous qubit selection.  Creating a cheap heuristic set of calibration data that users (or perhaps HW vendors) can run more frequently would likely lead to better results in some cases.

While the core components of this tool are now written in Rust and incorporated into the Qiskit SDK, better implementation of the stand alone version would likely be beneficial as many people still use it for its flexibility.
## Related Links

- Source code: [github.com/qiskit-community/mapomatic](https://github.com/qiskit-community/mapomatic)
- Paper: [PRX Quantum **4**, 010327 (2023)](https://doi.org/10.1103/PRXQuantum.4.010327)
- ArXiv: [arXiv:2209.15512](https://doi.org/10.48550/arXiv.2209.15512)