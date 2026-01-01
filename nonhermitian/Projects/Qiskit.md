
---
topic: software
date: 2025-05-14
tags:
  - projects
---

# Qiskit

![[../imgs/projects/qiskit.png ]]

## Collaborators

There are many contributors to Qiskit.  However, the core subset that I have engaged with are:

[Matthew Treinish](https://www.linkedin.com/in/matthew-t-a0973741/), [Jake Lishman](https://www.linkedin.com/in/jakelishman/), Ali Javadi, [Chris Wood](https://www.linkedin.com/in/cjwoodphd/), [Jay Gambetta](https://www.linkedin.com/in/jay-gambetta-a274753a/), [Andrew Cross](https://www.linkedin.com/in/andrew-cross-b9a604/), and Lev Bishop

## Summary

Qiskit is an open-source quantum SDK for interfacing with quantum hardware at the level of quantum circuits.  As quantum circuits can be viewed as quantum assembly level programs, this represents the lowest-level interface that is typically offered for quantum hardware.

Qiskit's primary focus is on quantum circuit creation, manipulation, optimization / compilation, and result post-processing.  In benchmarking, such as with [[Benchpress]], it has proven to be the most performant SDK in these areas.  It has also been the most preferred by end-users, with Qiskit being the SDK of choice by a plurality of users.  In fact, Qiskit has been the SDK of choice since the [Unitary Foundation started keeping track](https://github.com/unitaryfoundation/qoss-survey) in 2022.

## Motivation

The first publicly accessible cloud computer was put online on May 4th 2016 by IBM.  At that time, the way to program it was via a simple web interface.  The first device was only five qubits, so doing everything by hand was fine.  However for larger devices, the circuits quickly become too complex to tackle by hand.  The same is true at the quality of devices improves and the complexity of circuits increases.  Tools that automated much of the circuit construction, manipulation, and optimization / transpilation workflows we needed.  To this end, work on Qiskit started in 2017. 

## Possible Extensions

It is fairly straightforward to build on top of Qiskit provided you can interface via Python.  With the core library being moved to Rust, one really needs to know Rust now to do foundational work.  There is also a C-API that wraps the Rust API.

## Related Links

- Source code: [github.com/Qiskit/qiskit](https://github.com/Qiskit/qiskit)
- arXiv: [arXiv:2405.08810](https://arxiv.org/abs/2405.08810)