
---
topic: software
date: 2011-11-22
tags:
  - projects
---

# QuTiP - Quantum Toolbox in Python


![[../imgs/projects/qutip.png ]]

## Collaborators

QuTiP has many collaborators, including many after I had to step aside.  The project was started by myself and [Robert Johansson](https://www.linkedin.com/in/robert-johansson-996b0a3/).  However, it would not be what it is today without the help of people such as [Neill Lambert](https://www.linkedin.com/in/neill-l-b93888b/), [Eric Giguere](https://www.linkedin.com/in/eric-giguere-aa3247108/), [Jake Lishman](https://www.linkedin.com/in/jakelishman/), [Alexander Pitchford](https://www.linkedin.com/in/alexander-pitchford-47237a35/), and [Shahnawaz Ahmed](https://www.linkedin.com/in/quantshah/).  There is a host of other people who's contributions should not be ignored, but that I have not directly interacted with.

I should also give a call out to [Franco Nori](https://www.riken.jp/en/research/labs/rqc/qtm_inf_phys_theor_res/index.html) who let Robert and I work on the project when others thought it was: "pointless", "a high school project", "just an educational tool", or "does not further our understanding of quantum systems".  4000+ citations later, it seems to have proven its worth.

## Summary

At its most fundamental level, QuTiP is a library for building models of open and closed quantum systems, and numerically evaluating their time dynamics.  The scope has since been expanded to include domains such as optimal control and pulse-based quantum circuit simulation.

QuTiP is now the defacto standard for simulating quantum optical systems, and is the tool that others use to compare against.  Portions of QuTiP functionality, both big and small, have made its way into a multitude of other software projects, including those from major corporations such as IBM and Nvidia.

## Motivation

I had been using the quantum optics toolbox (`qotoolbox`) for Matlab for my PhD work, and decided that I wanted something uncoupled from paid software.  In addition, I needed an excuse to sharpen my poor programming skills.  At the same time I met Robert while visiting NTT Basic Research Labs over the summer, and he had a host of tools written in C that did much of what the `qotoolbox` did.  Also, unlike myself, he is actually a good programmer.  When I joined Franco's group in 2010, we started working on QuTiP, first as a side project and then later full time.

## Possible Extensions

There is always a host of new numerical techniques being discovered that could find a nice home in QuTiP.

## Related Links

- Source code: [github.com/qutip/qutip](https://github.com/qutip/qutip)
- Paper: [Physics Reports, **1153**, 1 (2025)](https://doi.org/10.1016/j.physrep.2025.10.001) (latest paper)
- arXiv: [arXiv:2412.04705](https://doi.org/10.48550/arXiv.2412.04705) (latest paper)
