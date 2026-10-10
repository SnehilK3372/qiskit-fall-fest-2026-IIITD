# Hackathon

Teams of 2–4 pick **one track**. Every track starts with a solved tutorial and then a challenge with three levels, so first-timers and researchers can compete in the same track.

| Track | The challenge in one line | Folder |
|---|---|---|
| 1 · Quantum Chemistry: *From Bonds to Qubits* | Map how a molecule's energy changes as its bond stretches, then do it with fewer quantum resources | [`track-1-quantum-chemistry/`](track-1-quantum-chemistry/) |
| 2 · Quantum Optimization: *Smarter Choices at Scale* | Pick the best set of stocks with QAOA, then scale the problem up | [`track-2-quantum-optimization/`](track-2-quantum-optimization/) |
| 3 · Quantum Simulation: *Dynamics Under Noise* | Simulate a chain of tiny magnets over time, then fight hardware noise | [`track-3-quantum-simulation/`](track-3-quantum-simulation/) |

## How it works

1. **Run your track's tutorial.** It is a solved, simplified version of the Beginner level that shows the Qiskit workflow step by step.
2. **Complete the Beginner level.** This is required for a valid submission.
3. **Climb as far as you can.** Intermediate and Advanced are optional; each one raises the maximum score you can get. Every level is open-ended: choosing and defending your method matters more than ticking every box.
4. **Submit** by **Wed Oct 14, 11:59 pm IST**.

## Timeline

All times are IST.

| When | What |
|---|---|
| Fri Oct 9, 12:00 noon | Registration closes (every team member must be registered) |
| Fri Oct 9, 2:00–4:00 pm | Online seminar and hackathon briefing |
| Sat Oct 10, 10:00 am | Challenges released, hacking starts |
| Wed Oct 14, 11:59 pm | **Submissions close** |
| Thu Oct 15 | Judging |
| Fri Oct 16, 2:00–6:00 pm | Grand finale at IIIT-Delhi and online |

## Compute and hardware

- **Develop on simulators.** Every tutorial runs in seconds on a laptop or in Colab.
- **Use real hardware for final runs only.** Each Open Plan account gets 10 QPU minutes every 28 days, so a team of four has up to 40 minutes between them.
- Pick a device with `service.least_busy(operational=True, simulator=False)`. Run single jobs or batches; Open Plan accounts cannot use sessions.
- Hardware is optional, but comparing ideal simulation, noisy simulation and real-device results earns credit at every level.
- Write down the backend name, job IDs and QPU seconds you used.

## What counts as a valid submission

Only valid submissions are judged and earn certificates. A submission is valid when **all five** of these hold:

1. **On time.** Submitted through the hackathon submission form (link will be live on 11 Oct) by **Wed Oct 14, 11:59 pm IST**. The last commit before the deadline is the one judged.
2. **From a registered team.** 2–4 members, all registered by 12 noon on Oct 9, working on one track.
3. **A public GitHub repo** that contains:
   - a Jupyter notebook that runs top to bottom and reproduces the results you report;
   - a `README.md` following [SUBMISSION_TEMPLATE.md](SUBMISSION_TEMPLATE.md): team, track, level reached, approach, results and how to run it;
   - a slides PDF of up to 8 slides.
4. **The track is complete.** At least the Beginner level is done, and your results are checked against an exact or classical reference.
5. **Your own work.** Keep the tutorial's credits, and name any other code, papers or AI tools you used. Copying another team's work makes a submission invalid.

## Grading

Every track is graded on the same 100-point rubric, taken from the BasQ Qiskit Fall Fest 2026 hackathon. Judges first decide the **level your team reached**. That level caps the first four criteria.

| Criterion | Score | Beginner (×0.6) | Intermediate (×0.85) | Advanced (×1) | What judges look for |
|---|---:|---:|---:|---:|---|
| Technical complexity | 30 | 18 | 25.5 | 30 | How far the team pushes beyond the basic workflow and the suggested system sizes |
| Validation of the algorithm | 20 | 12 | 17 | 20 | How rigorously results are checked against a classical reference, and how noiseless, noisy and real-hardware runs compare |
| Hardware awareness | 20 | 12 | 17 | 20 | Engagement with real-device constraints: initial layout, depth from routing, error suppression and mitigation |
| Analysis of performance and limitations | 10 | 6 | 8.5 | 10 | How well the team studies where its method works and where it stops working |
| Presentation | 20 | 20 | 20 | 20 | Clarity and structure of the presentation, reproducibility and guidance of the notebook |
| **Maximum** | **100** | **68** | **88** | **100** | |

## Grand finale

**Fri Oct 16, 2:00–6:00 pm, IIIT-Delhi and online.**

- After judging, the top **5 teams in each track (15 teams in all)** are invited to present.
- Each team gets **10 minutes**.
- Invited teams are welcome on campus, and can present online instead.
- The winner of each track receives **₹10,000**.

## Getting help

Ask in the [Discord](https://discord.gg/zZVgWYVYV), or email quantica@iiitd.ac.in.
