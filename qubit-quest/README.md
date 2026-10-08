# Qubit Quest

Learn quantum computing at your own pace, solo, with IBM Quantum's **Qiskit in Classrooms** modules. Each module mixes short explanations, Qiskit code you run, and questions that are **graded automatically** the moment you submit an answer. There is no team, no competition and no prize: just a certificate when you finish.

## How to earn your certificate

1. Complete **Get Started with Qiskit** ([`0-get-started/`](0-get-started/)).
2. Pick **one path** and work through its four modules in order. Each path has its own numbered folder.
3. Pass **at least 70% of the graded exercises** across those five modules by **Thu Oct 15, 11:59 pm IST**.
4. Run `check_progress()` and send its output through the [Qubit Quest form](TODO_QUBIT_QUEST_FORM_URL).

| Path | Folder | Modules after Get Started | Graded exercises (incl. Get Started) | Pass at least |
|---|---|---|---:|---:|
| **Physics** | [`1-physics/`](1-physics/) | Stern-Gerlach → Superposition → Uncertainty → Bell's inequality | 62 | 44 |
| **Computer science** | [`2-computer-science/`](2-computer-science/) | Teleportation → Quantum key distribution → Deutsch-Jozsa → Grover's algorithm | 49 | 35 |
| **Algorithms** | [`3-algorithms/`](3-algorithms/) | Deutsch-Jozsa → QFT & phase estimation → Shor's algorithm → VQE | 56 | 40 |

You can do more modules than your path needs; only your path's five count toward the certificate.

## Which path should I pick?

- **New to quantum?** Pick **Physics** or **Computer science**. Both start from the basics.
- **Seen some quantum computing or enjoy maths?** **Algorithms** is the most mathematical path: modular arithmetic, phase estimation and a chemistry problem.
- **What you need:** a little Python and school-level maths. Comfort with 2×2 matrices helps.
- **How long it takes:** each module takes about 1–2 hours, so plan 5–10 hours for a whole path.
- **What the questions look like:** most are true/false or multiple choice. A few ask for a short written answer, and a handful ask for values you read off your own results.

## Before you start

Follow [SETUP.md](../SETUP.md) once: create your IBM Quantum account, save your API key, and check that `check_progress()` works. The grader sends your answers to IBM's server, so it cannot score you without a saved account.

## The modules

Open a module in Google Colab with its **Colab** link, or open the file from its folder on your own computer. Work through each path in the numbered order: later modules build on earlier ones.

### Start here

| # | Module | Graded exercises | Real-hardware time | Open |
|---|---|---:|---|---|
| 0 | [Get Started with Qiskit](0-get-started/get-started-with-qiskit_fallfest.ipynb) | 14 | ~2 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/0-get-started/get-started-with-qiskit_fallfest.ipynb) |

### Physics path · [`1-physics/`](1-physics/)

| # | Module | Graded exercises | Real-hardware time | Open |
|---|---|---:|---|---|
| 1 | [Stern-Gerlach](1-physics/1-stern-gerlach-measurements-with-qiskit_fallfest.ipynb) | 11 | ~2 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/1-physics/1-stern-gerlach-measurements-with-qiskit_fallfest.ipynb) |
| 2 | [Superposition](1-physics/2-superposition-with-qiskit_fallfest.ipynb) | 8 | ~47 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/1-physics/2-superposition-with-qiskit_fallfest.ipynb) |
| 3 | [Uncertainty](1-physics/3-exploring-uncertainty-with-qiskit_fallfest.ipynb) | 11 | ~8 min, **use the simulator** | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/1-physics/3-exploring-uncertainty-with-qiskit_fallfest.ipynb) |
| 4 | [Bell's inequality](1-physics/4-bells-inequality-with-qiskit_fallfest.ipynb) | 18 | ~12 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/1-physics/4-bells-inequality-with-qiskit_fallfest.ipynb) |

### Computer science path · [`2-computer-science/`](2-computer-science/)

| # | Module | Graded exercises | Real-hardware time | Open |
|---|---|---:|---|---|
| 1 | [Quantum teleportation](2-computer-science/1-quantum-teleportation_fallfest.ipynb) | 9 | ~14 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/2-computer-science/1-quantum-teleportation_fallfest.ipynb) |
| 2 | [Quantum key distribution](2-computer-science/2-quantum-key-distribution_fallfest.ipynb) | 9 | ~5 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/2-computer-science/2-quantum-key-distribution_fallfest.ipynb) |
| 3 | [Deutsch-Jozsa](2-computer-science/3-deutsch-jozsa_fallfest.ipynb) | 9 | ~4 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/2-computer-science/3-deutsch-jozsa_fallfest.ipynb) |
| 4 | [Grover's algorithm](2-computer-science/4-grovers_fallfest.ipynb) | 8 | ~12 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/2-computer-science/4-grovers_fallfest.ipynb) |

### Algorithms path · [`3-algorithms/`](3-algorithms/)

| # | Module | Graded exercises | Real-hardware time | Open |
|---|---|---:|---|---|
| 1 | [Deutsch-Jozsa](3-algorithms/1-deutsch-jozsa_fallfest.ipynb) | 9 | ~4 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/3-algorithms/1-deutsch-jozsa_fallfest.ipynb) |
| 2 | [QFT & phase estimation](3-algorithms/2-qft_fallfest.ipynb) | 11 | ~13 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/3-algorithms/2-qft_fallfest.ipynb) |
| 3 | [Shor's algorithm](3-algorithms/3-shors-algorithm_fallfest.ipynb) | 10 | ~3 s | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/3-algorithms/3-shors-algorithm_fallfest.ipynb) |
| 4 | [VQE](3-algorithms/4-vqe_fallfest.ipynb) | 12 | ~8 min, **use the simulator** | [Colab](https://colab.research.google.com/github/SnehilK3372/qiskit-fall-fest-2026/blob/main/qubit-quest/3-algorithms/4-vqe_fallfest.ipynb) |

**Deutsch-Jozsa** appears in both the Computer science and Algorithms paths. It is the same module with the same grading, so if you have done it once, it counts for either path.

Real-hardware times are IBM's estimates. Your free account has 10 minutes every 28 days, so run Uncertainty and VQE on the simulator.

## How grading works

- Each question ends with a cell like `grade_qkd_ex4(answer)`. Set `answer`, run the cell, and the result appears straight away. Wrong? Change your answer and run it again. You can retry as often as you like.
- `check_progress()` prints everything you have passed so far. `check_progress("qkd")` shows one module. The module names are `intro`, `sg`, `superposition`, `uncertainty`, `bell`, `teleport`, `qkd`, `dj`, `grovers`, `qft`, `shors` and `vqe`.
- Written-answer questions are graded too. Answer them in your own words.

## Tips

- **Run cells in order.** Later cells use variables defined earlier.
- **Simulators are slower than they look.** On a laptop, the VQE module can take 20 minutes or more on the simulator, and one Stern-Gerlach cell takes a few minutes.
- **Quantum key distribution:** Experiment 3 uses 127 qubits and only runs on real hardware (about 5 seconds). Everything before it runs on the simulator.
- **Grover's algorithm** has a partner activity where you swap circuit files. Working alone? Save your own circuit and load it back, using a simple file name such as `my_circuit.qpy` in place of the placeholder path.
- **Windows:** the install line at the top of each module uses single quotes (`qiskit'[visualization]'`). Change them to double quotes (`"qiskit[visualization]"`) or use Colab.

## Changes from IBM's version

We made small code fixes to four modules so they run on today's IBM devices and the free Open Plan. Each changed notebook says so in a note right below its title. We also added a number to each file name so the modules sort in path order.

| Module | Change |
|---|---|
| Quantum key distribution | Picks the least busy device with at least 127 qubits instead of `ibm_brisbane`, which IBM retired in November 2025 |
| Shor's algorithm | Picks the least busy device instead of always using `ibm_marrakesh` |
| Quantum teleportation | Adds the `if_else` instruction only when the device does not already list it; current devices do, so the original cell stopped with an error |
| Stern-Gerlach | Runs jobs in job mode instead of a session, because Open Plan accounts cannot open sessions; this also lets a later cell reuse the sampler |

## Credits

These modules are IBM Quantum Learning's [Qiskit in Classrooms](https://quantum.cloud.ibm.com/learning/modules/quantum-mechanics) modules, with the Qiskit Fall Fest 2026 grader. Content is under CC BY-SA 4.0 and code under Apache 2.0.
