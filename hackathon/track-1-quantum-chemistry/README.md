# Track 1 · Quantum Chemistry: *From Bonds to Qubits*

Compute how a molecule's energy changes as its bond stretches, then do it again using fewer quantum resources.

*Inspired by IBM Quantum's 2017 demonstration of a hardware-efficient variational quantum eigensolver for small molecules ([Kandala et al., Nature 549, 242–246](https://www.nature.com/articles/nature23879)).*

## Start here

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026-IIITD/blob/main/hackathon/track-1-quantum-chemistry/challenge_1_tutorial.ipynb)

[`challenge_1_tutorial.ipynb`](challenge_1_tutorial.ipynb) is a solved example. It computes the ground-state energy of H₂ with VQE, using a Jordan-Wigner mapping and a UCCSD ansatz on a Hartree-Fock state, and checks the result against an exact solver. It runs in a few seconds on a simulator.

> **Windows users:** the chemistry package `pyscf` has no Windows build. Use Google Colab (button above) or WSL.
> **In Colab**, uncomment and run the install cell near the top of the notebook first.

## The challenge

Each level builds on the one before. **Beginner is required** for a valid submission; Intermediate and Advanced raise the maximum score (see [grading](../README.md#grading)).

### 🟢 Beginner: the energy curve of HeH⁺

- Compute the ground-state energy of **HeH⁺** (charge +1, spin 0, STO-3G basis) at **10 or more He–H distances between 0.5 and 3.0 Å**, with VQE **and** the exact solver.
- Plot both curves, mark the **equilibrium bond length**, and report the energy needed to pull the atoms apart (energy at 3.0 Å minus energy at equilibrium).
- Explain your choice of ansatz, mapping, optimizer and basis set.

> ⚠️ HeH⁺ is an ion. Keep the electron-number filter on the exact solver, which the tutorial already includes:
> `numpy_solver.filter_criterion = problem.get_default_filter_criterion()`.
> Without it, the solver returns the energy of a molecule with the wrong number of electrons.

### 🟠 Intermediate: do more with less

- Move to a larger molecule: **LiH at 1.6 Å** (STO-3G; the full mapping needs 12 qubits), or BeH₂.
- Cut qubits, circuit size or measurements while staying within **chemical accuracy (1.6 mHa = 0.0016 Ha)** of the full exact energy. Levers to try:
  - freeze the core orbitals or choose an active space;
  - use a parity mapping with two-qubit reduction, or symmetry tapering;
  - group commuting measurements.
- Report one table showing qubits, two-qubit gates, measurement groups and error against the exact energy after each step. Which combination works best under a fixed budget?

### 🔴 Advanced: beyond a single ansatz

- Use **sample-based quantum diagonalization (SQD)**: sample electron configurations from a circuit, then diagonalize classically inside that smaller space.
- Pick a molecule where plain UCCSD struggles (**stretched N₂** is a good choice) and show your approach does better.
- Explain how you know the answer is trustworthy once exact diagonalization is out of reach.
- Start from IBM's [SQD tutorial](https://quantum.cloud.ibm.com/docs/tutorials/sample-based-quantum-diagonalization) and the [qiskit-addon-sqd docs](https://qiskit.github.io/qiskit-addon-sqd/) (`pip install qiskit-addon-sqd`).

## Hardware (optional, any level)

Run at least one energy point on an IBM QPU with the Estimator and error mitigation, and compare it with your simulator result.

## Resources

- [Qiskit Nature documentation](https://qiskit-community.github.io/qiskit-nature/)
- [Ground-state solvers tutorial](https://qiskit-community.github.io/qiskit-nature/tutorials/03_ground_state_solvers.html), closest to the tutorial notebook
- [Qubit mappers tutorial](https://qiskit-community.github.io/qiskit-nature/tutorials/06_qubit_mappers.html): Jordan-Wigner, parity, Bravyi-Kitaev and tapering (useful for Intermediate)
- [AdaptVQE how-to](https://qiskit-community.github.io/qiskit-nature/howtos/adapt_vqe.html)
- [Error mitigation and suppression techniques](https://quantum.cloud.ibm.com/docs/guides/error-mitigation-and-suppression-techniques)
- [Combine error mitigation options with the Estimator](https://quantum.cloud.ibm.com/docs/tutorials/combine-error-mitigation-techniques)

## Credits

Tutorial by Benjamin Tirado; challenge adapted from the BasQ Qiskit Fall Fest 2026 hackathon prompt by Angel Rodriguez, Benjamin Tirado and Miguel Angel Jimenez. Text under CC BY 4.0, code under Apache 2.0. Our changes to the notebook are listed in its credits cell.
