
---
topic: software
date: 2026-03-30
tags:
  - projects
---

# Fulqrum

![[../imgs/projects/fulqrum.png]]

## Collaborators

[Abdullah Ash Saki](https://www.linkedin.com/in/ashsaki/), [Hwajung Kang](https://www.linkedin.com/in/hwajung-kang-ph-d-b564733b0/)

## Summary

Fulqrum is a numerical framework for computing the action of a Hamiltonian defined in a subspace on a vector.  To put it another way, it performs matrix-vector operations for quantum mechanical calculations where the problem of interest is confined to a polynomial-sized subspace of the full exponential Hamiltonian in which the Hamiltonian lives.  Such a tool is needed, for example, for solving eigenvalue equations in quantum chemistry and many-body physics.

## Motivation

When working as the Technical Assistant (TA) to Jay Gambetta, I was thinking about ground state methods like VQE and how much of the computation is classical, and really doesn't need to care about computing amplitudes directly from samples generated on a quantum computer; one can offload much of the computation to classical solvers using only the observed bit-strings.  As with any good idea it turns out others already had thought of it, particularly  in the quantum chemistry space, e.g. [Kanno et. al.](https://arxiv.org/abs/2302.11320).  IBM later extended this idea by adding post-processing techniques that later became known as [Sample-based Quantum Diagonalization (SQD)](https://arxiv.org/abs/2405.05068), and the package that performs these calculations was released as the [SQD qiskit-addon](https://github.com/qiskit/qiskit-addon-sqd).   

The issue that caught by eye is that these techniques use different solution methods depending on whether the Hamiltonian is fermionic or spin-based.  Fermionic problems, usually coming from quantum chemistry, use a variety of packages like [PySCF](https://github.com/pyscf/pyscf)  and[DICE](https://github.com/sanshar/Dice), whereas spin-based systems are solved using different techniques like those in the SQD qiskit-addon.  This means people have to learn different packages depending on the problem Hamiltonian when it should be possible to solve any operator-based Hamiltonian using the same tools.  Fulqrum's goal is to provide a single tool / framework to solve arbitrary Hamiltonian subspace problems, regardless of operator statistics, whilst maintaining or besting performance of current methods in terms of runtime, memory consumption, or both.

The project turned out to be much larger than I originally thought, and there are many interesting aspects to this work.  We came up with several novel operator methods, and devised a technique based on perturbation theory to greatly reduce the size of subspaces needed to achieve the same target accuracy.

## Possible Extensions

We are currently exploring how best to utilize our subspace refinement methods in workflows, and also exploring GPU acceleration.  Saki already has extremely performant examples of the latter for fermionic Hamiltonians.

## Related Links

- Source code: [github.com/qiskit-community/fulqrum](https://github.com/qiskit-community/fulqrum)
- arXiv: [arXiv:2603.18731](https://doi.org/10.48550/arXiv.2603.18731)