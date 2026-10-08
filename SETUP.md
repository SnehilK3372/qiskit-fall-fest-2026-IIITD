# Setup

You need two things: a free **IBM Quantum account** with an API key, and somewhere to run Jupyter notebooks. **Google Colab** is the easiest place, and the only easy option for Track 1 on Windows.

## 1. Create your IBM Quantum account

1. Sign up at [quantum.cloud.ibm.com](https://quantum.cloud.ibm.com). The free **Open Plan** gives you up to **10 minutes of real quantum hardware time every 28 days**.
2. Create an **API key** and an **instance**, and note the instance's CRN. IBM's guide walks you through both: [Set up your IBM Cloud account](https://quantum.cloud.ibm.com/docs/en/guides/cloud-setup).

Keep your API key private. Never paste it into a notebook you share or commit to GitHub.

## 2. Save your account once

### On your own computer

Run this once, then delete the cell:

```python
from qiskit_ibm_runtime import QiskitRuntimeService

QiskitRuntimeService.save_account(
    channel="ibm_quantum_platform",
    token="<YOUR_API_KEY>",
    instance="<YOUR_INSTANCE_CRN>",
    set_as_default=True,
    overwrite=True,
)
```

After that, `QiskitRuntimeService()` and the Qubit Quest grader both find your account automatically.

### On Google Colab

Colab forgets saved accounts whenever the runtime restarts, so run the save step at the start of each session. To keep your key out of the notebook, store it in Colab's **Secrets** panel (the key icon in the left sidebar) as `IBM_QUANTUM_API_KEY` and `IBM_QUANTUM_INSTANCE`, then run:

```python
from google.colab import userdata
from qiskit_ibm_runtime import QiskitRuntimeService

QiskitRuntimeService.save_account(
    channel="ibm_quantum_platform",
    token=userdata.get("IBM_QUANTUM_API_KEY"),
    instance=userdata.get("IBM_QUANTUM_INSTANCE"),
    set_as_default=True,
    overwrite=True,
)
```

## 3. Install the packages

### Google Colab

Each notebook starts with an install cell. Uncomment it and run it first.

### Your own computer

Use Python 3.10 or newer:

```bash
git clone https://github.com/SnehilK3372/qiskit-fall-fest-2026
cd qiskit-fall-fest-2026
pip install -r requirements.txt
jupyter lab
```

`requirements.txt` pins the versions every notebook in this repo was tested with on October 7, 2026.

### Windows notes

- **Track 1 (chemistry)** needs `pyscf`, which has no Windows build. Use Google Colab or WSL for Track 1. `requirements.txt` skips `pyscf` on Windows, so everything else still installs.
- The Qubit Quest notebooks' install line uses single quotes: `qiskit'[visualization]'`. On Windows, change them to double quotes: `"qiskit[visualization]"`.

## 4. Check that everything works

```python
from qc_grader.challenges.fallfest_2026 import check_progress

check_progress()
```

If this prints a progress summary (zero passed at the start), your account and the grader are working. If it says your API key is missing, repeat step 2.

## Using real quantum hardware

- **Build and test on simulators first.** Use real hardware only for final runs.
- Pick a device with `service.least_busy(operational=True, simulator=False)` rather than naming one; devices get retired.
- Open Plan accounts can run single jobs or batches, **not sessions**. A notebook that opens a `Session` will fail on the Open Plan.
- Track your QPU time on the IBM Quantum dashboard. A team of four has up to 40 minutes between them.

Stuck? Ask in the [Discord](https://discord.gg/zZVgWYVYV).
