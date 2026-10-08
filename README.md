# Qiskit Fall Fest 2026 · IIIT-Delhi

Starter material for the **hackathon** and **Qubit Quest** at the Qiskit Fall Fest 2026, organised by **Quantica**, **CQT (IIIT-Delhi)** and **IBM Quantum**, October 9–16, 2026.

This year's Fall Fest theme is *A decade of quantum on the cloud*: ten years since IBM put the first quantum computer online for anyone to use.

## Two ways to take part

| | Hackathon | Qubit Quest |
|---|---|---|
| **Who** | Teams of 2–4 | Solo |
| **What** | Pick one of three tracks: run its tutorial, then take on a challenge with three levels | Work through IBM's auto-graded Qiskit modules at your own pace |
| **Reward** | ₹10,000 for each track winner; certificates for every valid submission | Certificate when you reach 70% |
| **Deadline** | Wed Oct 14, 11:59 pm IST | Thu Oct 15, 11:59 pm IST |
| **Start here** | [`hackathon/`](hackathon/) | [`qubit-quest/`](qubit-quest/) |

No prior quantum background is needed for either.

## Key dates

All times are IST.

| When | What |
|---|---|
| Fri Oct 9, 12:00 noon | Registration closes |
| Fri Oct 9, 2:00–4:00 pm · online | Quantum & Qiskit 101 seminar with Prof. Bhavna Bose Gupta, then the hackathon briefing |
| Sat Oct 10, 10:00 am · online | Hackathon challenges released |
| Mon Oct 12, 11:59 pm | Poster abstracts due |
| Wed Oct 14, 11:59 pm | Hackathon submissions due |
| Thu Oct 15 | Judging · Qubit Quest closes at 11:59 pm |
| Fri Oct 16, 2:00–6:00 pm · IIIT-Delhi + online | Grand finale: poster session, team presentations, awards |

## Quick start

1. **Set up your IBM Quantum account** and save your API key once. Follow [SETUP.md](SETUP.md).
2. **Open a notebook.** Every notebook has an *Open in Colab* button, which is the easiest way to start, especially on Windows. To work locally instead, clone this repo and run `pip install -r requirements.txt`.
3. **Join the [Discord](https://discord.gg/zZVgWYVYV)** for announcements and help.

## What's in this repo

```
.
├── README.md                          you are here
├── SETUP.md                           account, API key, Colab and local setup
├── requirements.txt                   tested package versions
├── hackathon/
│   ├── README.md                      how the hackathon works, valid submissions, grading, finale
│   ├── SUBMISSION_TEMPLATE.md         README template for your team's repo
│   ├── track-1-quantum-chemistry/     tutorial + challenge
│   ├── track-2-quantum-optimization/  tutorial + challenge
│   └── track-3-quantum-simulation/    tutorial + challenge
└── qubit-quest/
    ├── README.md                      paths, grading and how to earn the certificate
    ├── 0-get-started/                 everyone starts here
    ├── 1-physics/                     physics path, 4 modules in order
    ├── 2-computer-science/            computer science path, 4 modules in order
    └── 3-algorithms/                  algorithms path, 4 modules in order
```

## Research poster session

Have quantum or quantum-adjacent work to show? Present a poster at the grand finale.

- Open to **any student or researcher**.
- Submit **only an abstract** through the [poster abstract form](TODO_POSTER_ABSTRACT_FORM_URL) by **Mon Oct 12, 11:59 pm IST**. No poster file is needed in advance.
- Only the **first 50** submissions are accepted.
- Poster presenters must attend the finale **in person** at IIIT-Delhi on Fri Oct 16.
- Prizes: ₹5,000 for the best poster, plus a people's-choice prize.

## Prizes and certificates

**Prizes** total ₹35,000:
- ₹10,000 for the winner of each of the three hackathon tracks
- ₹5,000 for the best poster
- a people's-choice prize at the poster session

**Certificates** go to:
- every member of a team with a [valid hackathon submission](hackathon/README.md#what-counts-as-a-valid-submission)
- every Qubit Quest participant who reaches 70%
- every poster presenter

## Help

- **Discord:** https://discord.gg/zZVgWYVYV (fastest)
- **Email:** quantica@iiitd.ac.in
- **Website:** https://qiskit-fall-fest-xi.vercel.app

Everyone taking part agrees to follow the [Qiskit Code of Conduct](https://github.com/Qiskit/qiskit/blob/main/CODE_OF_CONDUCT.md).

## Credits and licences

- **Hackathon tutorials and challenges** are adapted from the [BasQ](https://www.basquequantum.eus/) Qiskit Fall Fest 2026 hackathon. Tutorials are by Benjamin Tirado; the hackathon prompt is by Angel Rodriguez, Benjamin Tirado and Miguel Angel Jimenez. Text is under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), code under [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0). The small fixes we made are listed in each notebook's credits cell.
- **Qubit Quest modules** are IBM Quantum Learning's *Qiskit in Classrooms* modules with the Fall Fest grader. Content is under CC BY-SA 4.0, code under Apache 2.0. Four notebooks carry small code fixes, listed in [qubit-quest/README.md](qubit-quest/README.md#changes-from-ibms-version).
- Everything else in this repo was written by Quantica for this event.
