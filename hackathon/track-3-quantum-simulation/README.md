# Track 3 · Quantum Simulation: *Dynamics Under Noise*

Simulate how a chain of tiny magnets evolves over time, then correct for noise on real hardware.

*Inspired by IBM's 2023 "utility" experiment, a large kicked-Ising simulation with error mitigation ([Kim et al., Nature 618, 500–505](https://www.nature.com/articles/s41586-023-06096-3)).*

## The model

Picture a row of tiny magnets (spins) that pull on their neighbours while a sideways magnetic field tries to flip them. This is the **transverse-field Ising model**:

```math
H = -J \sum_{i} Z_i Z_{i+1} \;-\; h \sum_{i} X_i
```

Simulating how such a chain evolves gets hard for classical computers as it grows.

## Start here

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026-IIITD/blob/main/hackathon/track-3-quantum-simulation/challenge_3_tutorial.ipynb)

[`challenge_3_tutorial.ipynb`](challenge_3_tutorial.ipynb) is a solved example. It evolves a 4-spin chain with first-order Trotter steps, tracks the magnetization over time and compares it with the exact answer. It runs in a few seconds.

> ⚠️ Keep `.decompose(reps=2)` (or transpile) on every Trotter circuit before you simulate it, as the tutorial does. Otherwise Qiskit applies the evolution exactly and you will see zero Trotter error.

## The challenge

Each level builds on the one before. **Beginner is required** for a valid submission; Intermediate and Advanced raise the maximum score (see [grading](../README.md#grading)).

### 🟢 Beginner: get the simulation right (8 spins)

- Use **8 spins with J = h = 1**, start in $|00000000\rangle$ and evolve to **t = 2**. Compare against the exact answer from `scipy.linalg.expm`.
- Plot:
  - the magnetization $M_z(t)$, the average of $\langle Z_i \rangle$;
  - the sideways magnetization $M_x(t)$, the average of $\langle X_i \rangle$;
  - the correlation $\langle Z_0 Z_r \rangle$ at $t = 2$ against the distance $r$.
- For the first-order (`LieTrotter`) and second-order (`SuzukiTrotter`) formulas, find the **largest time step that keeps the error below 0.01 over the whole run**, for $M_z$ and for $M_x$. Report the two-qubit gate count at that step.
- Which formula is cheaper, and why does the answer depend on what you measure?

### 🟠 Intermediate: recover the physics that noise hides

- Go to **12 or more spins**, or longer times, and add realistic noise: a noisy simulator built from a fake backend such as `FakeFez` (from `qiskit_ibm_runtime.fake_provider`), or a real QPU.
- Apply error mitigation (readout correction, zero-noise extrapolation, Pauli twirling, dynamical decoupling) and tricks that cut circuit depth.
- Show noisy, mitigated and exact curves on one plot. A noiseless simulation with a small time step makes a good "exact" reference up to about 20 spins.

### 🔴 Advanced: where classical checking gets hard

- Simulate a **kicked (Floquet) Ising chain of 50 or more spins** on an IBM QPU with error mitigation, as in the 2023 utility experiment.
- You can no longer compute the exact answer. Argue that your results are right using limiting cases with known answers, small-size checks, and consistency across step sizes and mitigation settings.
- Report the largest system and longest time you can defend as trustworthy, and budget your QPU minutes (10 per account every 28 days).

## Hardware (optional, any level)

Run your Beginner or Intermediate circuit on an IBM QPU and compare it with your noisy simulation.

## Resources

- [Quantum real-time evolution using Trotterization](https://qiskit-community.github.io/qiskit-algorithms/tutorials/13_trotterQRTE.html)
- [`PauliEvolutionGate`](https://quantum.cloud.ibm.com/docs/api/qiskit/qiskit.circuit.library.PauliEvolutionGate), [`LieTrotter`](https://quantum.cloud.ibm.com/docs/api/qiskit/qiskit.synthesis.LieTrotter) and [`SuzukiTrotter`](https://quantum.cloud.ibm.com/docs/api/qiskit/qiskit.synthesis.SuzukiTrotter) reference pages
- [Error mitigation and suppression techniques](https://quantum.cloud.ibm.com/docs/guides/error-mitigation-and-suppression-techniques)
- [Combine error mitigation options with the Estimator](https://quantum.cloud.ibm.com/docs/tutorials/combine-error-mitigation-techniques)
- [Smith et al., *Simulating quantum many-body dynamics on a current digital quantum computer* (2019)](https://www.nature.com/articles/s41534-019-0217-0)

## Credits

Tutorial by Benjamin Tirado; challenge adapted from the BasQ Qiskit Fall Fest 2026 hackathon prompt by Angel Rodriguez, Benjamin Tirado and Miguel Angel Jimenez. Text under CC BY 4.0, code under Apache 2.0. Our changes to the notebook are listed in its credits cell.
