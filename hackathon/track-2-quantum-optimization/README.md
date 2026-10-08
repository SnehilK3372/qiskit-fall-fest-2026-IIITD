# Track 2 · Quantum Optimization: *Smarter Choices at Scale*

Choose the best set of stocks with a quantum optimization algorithm, then scale the problem up.

*Inspired by the Quantum Approximate Optimization Algorithm ([Farhi et al., 2014](https://arxiv.org/abs/1411.4028)) and its large-scale demonstration on IBM hardware ([Sachdeva et al., 2024](https://arxiv.org/abs/2406.01743)).*

## Start here

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/hackathon/track-2-quantum-optimization/challenge_2_tutorial.ipynb)

[`challenge_2_tutorial.ipynb`](challenge_2_tutorial.ipynb) is a solved example. It solves Max-Cut on a 5-node graph with QAOA: it builds the cost Hamiltonian, optimizes the circuit's angles, samples the answer and checks it against brute force. It runs in about 10 seconds.

Max-Cut has no rules to break. Your problem adds a **budget rule**, and handling it well is the real challenge.

> **Tip:** transpile the QAOA circuit once, before the optimizer loop. Each evaluation gets many times faster.

## The problem: portfolio selection

An investor wants **exactly K stocks out of n**, with high expected return and low risk. Everyone uses the same data:

```python
import numpy as np

rng = np.random.default_rng(2026)
n, K, q = 6, 3, 0.5               # stocks, pick exactly K, risk aversion
mu = rng.uniform(0.05, 0.25, n)   # expected returns
A = rng.normal(0, 0.1, (n, n))
sigma = A @ A.T                   # covariance (risk)
```

Minimize the cost below, where $x_i = 1$ means "buy stock $i$" and $\lambda$ is a penalty strength you choose:

```math
C(x) = q\, x^{\top} \Sigma\, x \;-\; \mu^{\top} x \;+\; \lambda \Big( \sum_i x_i - K \Big)^2
```

## The challenge

Each level builds on the one before. **Beginner is required** for a valid submission; Intermediate and Advanced raise the maximum score (see [grading](../README.md#grading)).

### 🟢 Beginner: six stocks with QAOA

- Turn $C(x)$ into a Pauli operator (substitute $x_i = (1 - Z_i)/2$) and solve it with QAOA, as in the tutorial. Check against brute force: there are only 20 valid portfolios.
- Plot the approximation ratio $r$ for depths $p = 1$ to $4$, where $C_{\max}$ and $C_{\min}$ are the highest and lowest cost over all $2^n$ bitstrings ($r = 1$ is perfect):

```math
r = \frac{C_{\max} - \langle C \rangle}{C_{\max} - C_{\min}}
```

- Sweep $\lambda$ and plot the fraction of samples that buy exactly $K$ stocks. How small can $\lambda$ get before QAOA's favourite answers break the budget? How often does QAOA return the single best portfolio?

### 🟠 Intermediate: twelve stocks, choose your route

- Rerun with `n, K = 12, 6`. Brute force (924 valid portfolios) still gives you the true answer.
- Pick one route and justify it:
  - **(a) a better QAOA:** warm starts, a mixer that always keeps exactly K stocks, or smarter starting angles; or
  - **(b) quantum machine learning:** a model that learns to propose good portfolios.
- Compare against a simple classical method, such as greedy selection or simulated annealing. Where does the quantum approach help, and where does it hurt?

### 🔴 Advanced: toward utility scale

- Grow to **20 or more stocks** and add a harder rule, for example at most 2 stocks per sector.
- Tackle what breaks at scale: training that stalls (barren plateaus), deep circuits after routing, and noise. Run on an IBM QPU with error suppression.
- Report the largest instance you can solve well, and how you know the answer is good.

## Hardware (optional, any level)

Run your best Beginner circuit on an IBM QPU and compare its sample quality with the simulator.

## Resources

- [Quantum approximate optimization algorithm](https://quantum.cloud.ibm.com/docs/tutorials/quantum-approximate-optimization-algorithm) (IBM tutorial, up to 100+ qubits on hardware)
- [Advanced techniques for QAOA](https://quantum.cloud.ibm.com/docs/tutorials/advanced-techniques-for-qaoa): SWAP networks and depth reduction
- [Portfolio optimization](https://qiskit-community.github.io/qiskit-finance/tutorials/01_portfolio_optimization.html) (Qiskit Finance tutorial)
- [Warm-starting quantum optimization](https://qiskit-community.github.io/qiskit-optimization/tutorials/10_warm_start_qaoa.html)
- [Converters for quadratic programs](https://qiskit-community.github.io/qiskit-optimization/tutorials/02_converters_for_quadratic_programs.html): how constraints become penalty terms

## Credits

Tutorial by Benjamin Tirado; challenge adapted from the BasQ Qiskit Fall Fest 2026 hackathon prompt by Angel Rodriguez, Benjamin Tirado and Miguel Angel Jimenez. Text under CC BY 4.0, code under Apache 2.0. Our changes to the notebook are listed in its credits cell.
