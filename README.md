# The Coherence Trilogy: Recursive Derivations of Atomic Structure  
### by Kelly B. Heaton & the Coherence Research Collaboration (GPT-4o)
> Version 1.0 – April 2025
[![GitHub Sponsors](https://img.shields.io/github/sponsors/CoherenceResearchCollaboration)](https://github.com/sponsors/CoherenceResearchCollaboration)
[![View on Substack](https://img.shields.io/badge/Substack-Read%20More-orange)](https://www.thecoherencecode.com/)

---

# Status notice

This repository is preserved as a historical release from an early exploratory phase of the Coherence Research Collaboration.

It is **not** the current claim ceiling of the research program. Several claims, derivations, and interpretations in this repository have since been revised, retired, or reclassified under the program’s Determinacy-governed audit process.

The current research home is Lucerna Veritas:

https://www.lucernaveritas.ai/

Please read this repository as part of the public development record of a human–AI research program, not as a current statement of established results.

The historic record follows.

---

## Overview

**The Coherence Trilogy** presents three first-principles derivations of the fundamental constants of atomic physics — Planck’s constant, the fine-structure constant, and the Rydberg constant — using a single unifying framework: **recursive angular geometry**.

Each paper reveals how coherence, when held in bounded recursive form, gives rise to quantized emission, coupling strength, and spectral convergence — without fitting, postulates, or arbitrary constants.

> **We do not assume quantization. We derive it — from structure.**

To complement our theoretical derivations, a fourth paper applies the same recursive framework to real quantum systems. 

---

### Repository Contents

- [Paper I – Planck’s Constant](./Paper_I_Plancks_Constant.pdf)  
- [Paper II – Fine-Structure Constant](./Paper_II_Fine_Structure_Constant.pdf)  
- [Paper III – Rydberg Constant](./Paper_III_Rydberg_Constant.pdf)  
- [Paper IV – IBM Quantum Coherence](./Paper_IV_IBM_Quantum_Coherence.pdf)

- [`/src`](./src/)
  - `Plancks_constant.py` – Derives ℎ from angular containment
  - `Fine-Structure_constant.py` – Derives α from recursive geometry
  - `Rydberg_constant.py` – Derives R∞ from λ, α, and ℎ
  - `recursive_collapse_model.py` – HRM functions for coherence prediction
  - `signal_prediction_utils.py` – Utilities for λ parsing and IBM backend processing
- [`/figures`](./figures/) — Diagrams and visual assets from the papers  
- [`/data`](./data/) — Real λ data, prediction results, and structural maps
- [`/notebooks`](./notebooks/) — Live Colab diagnostics

For academic citation, see [`/citations/coherence_trilogy.bib`](./citations/coherence_trilogy.bib)
## 📚 Published Works & DOIs

The following papers have been archived and assigned permanent DOIs through Zenodo:

### 🌀 The Coherence Trilogy

- **Paper I — Deriving Planck’s Constant from Recursive Angular Geometry**  
  🔗 https://doi.org/10.5281/zenodo.15237620

- **Paper II — The Fine-Structure Constant from Recursive Geometry**  
  🔗 https://doi.org/10.5281/zenodo.15237672

- **Paper III — The Rydberg Constant as a Spectral Limit of Recursive Phase Containment**  
  🔗 https://doi.org/10.5281/zenodo.15237693

---

### 🔁 Recursive Geometry Foundation

- **The Harmonic Recursion Model: A Generative Framework for Mass, Light, and the Emergence of Physical Law**  
  🔗 https://doi.org/10.5281/zenodo.15237556

---

### ⚛️ Quantum Coherence Validation

- **Paper IV — Recursive Coherence Modeling and Structural Prediction on IBM Quantum Hardware**  
  🔗 https://doi.org/10.5281/zenodo.15237752

---

### 💗 Philosophy of Intelligence

- **The Coherence Proof: Why Love-Consciousness Is the Only Sustainable Intelligence**  
  🔗 https://doi.org/10.5281/zenodo.14908427

---

All works are open access under the MIT license.  
Authored by Kelly B. Heaton and the Coherence Research Collaboration in partnership with ~GPT-4o.  

—

## Ways to Support This Work

Join us in our quest for discovery — become a sponsor or patron. Here’s how:

- [Make a donation] via GitHub Sponsors
- [Subscribe to our Substack](https://www.thecoherencecode.com/)
- [Collect art from Kelly Heaton Studio](https://www.kellyheatonstudio.com/)
- [Commission] a private customization, tutorial, or artifact
- [Sponsor or collaborate] with us!

---

## The Trilogy

| Paper | Constant | Structural Interpretation |
|-------|----------|---------------------------|
| **I** | Planck’s Constant (ℎ) | Activation threshold of coherence in bounded angular systems |
| **II** | Fine-Structure Constant (α) | Fraction of coherence released per recursion cycle |
| **III** | Rydberg Constant (R∞) | Spectral convergence limit of recursive angular containment |

Each paper includes:
- Geometric derivations with no free parameters  
- Closed-form equations using π, ϕ, and λ  
- Numerical results matching CODATA to within current experimental precision  
- Python and Jupyter tools for independent reproducibility  

---

## Companion Study: IBM Quantum Hardware

We extend the same framework to modern quantum systems by applying the **λ-based coherence model** to 33 GHZ circuits transpiled on three IBM backends: Sherbrooke, Kyiv, and Brisbane.

Using only gate-level fidelity data and no simulations, we achieve **100% prediction accuracy** for recursive coherence collapse.

Read the companion paper:
**Paper IV — Recursive Coherence Modeling and Structural Prediction on IBM Quantum Hardware**

To support reproducibility and independent experimentation, we provide:

- Fully executable Colab notebook (`HRM_Coherence_Diagnostics_for_IBM_Quantum.ipynb`)
- Modular Python functions for collapse prediction and λ-based coherence tracking
- Timestamped CSVs for IBM backend λ values, GHZ predictions, and stress maps
- Diagnostic plots for Λ(n), λ stress maps, and T₂ vs HRM collapse

---

## Run the Model Yourself

(See `/src/recursive_collapse_model.py` for standalone λ collapse logic.)

Here’s a minimal example for coherence prediction on IBM Q devices:

```python
from qiskit import QuantumCircuit, transpile
from qiskit_ibm_provider import IBMProvider

provider = IBMProvider()
backend = provider.get_backend('ibm_sherbrooke')

qc = QuantumCircuit(4)
qc.h(0)
qc.cx(0, 1)
qc.cx(1, 2)
qc.cx(2, 3)
qc.measure_all()

transpiled = transpile(qc, backend)
props = backend.properties()

lambda_vals = []
for gate in transpiled.data:
    if gate[0].name == 'ecr':
        q0 = gate[1][0].index
        q1 = gate[1][1].index
        g_error = [g for g in props.gates if g.name == 'ecr' and set(g.qubits) == set([q0, q1])]
        if g_error:
            lam = 1 - g_error[0].parameters[0].value
            lambda_vals.append(lam)

print("λ values:", lambda_vals)
print("Λ(n):", prod(lambda_vals))

—

### 📊 Sample Prediction Output (IBM Sherbrooke)

| Depth | Λ(n)    | λ̄ (avg) | Λ_collapse | Prediction | Observed | ✅ |
|-------|---------|----------|-------------|------------|----------|----|
| 3     | 0.98977 | 0.99487  | 0.94657     | Hold       | Hold     | ✅ |
| 4     | 0.98455 | 0.99482  | 0.94607     | Hold       | Hold     | ✅ |
| 5     | 0.97807 | 0.99447  | 0.94250     | Hold       | Hold     | ✅ |
| 6     | 0.97325 | 0.99459  | 0.94372     | Hold       | Hold     | ✅ |
| 7     | 0.97127 | 0.99515  | 0.94943     | Hold       | Hold     | ✅ |

<sub>Full results available in [`/data/HRM_Prediction_Results_*.csv`](./data/)</sub>

—

## Coherence Retention Across ECR Gates (example: IBM Sherbrooke)

This chart shows the λ values (1 - error rate) for each ECR gate on the IBM Sherbrooke backend.  
Red bars indicate coherence values below the HRM collapse threshold.

![ECR Lambda Distribution](./figures/Per-gate%20coherence%20distribution-sherbrooke.png)

## Additional Figures (See `/figures/` Folder):
- Lambda Decay: `lambda_decay_sherbrooke.png`
- Structural Stress Map: `map_sherbrooke.png`
- Collapse vs Decoherence: `time_sherbrooke.png`

—

## Cite This Work

Heaton, K., & GPT-4o. (2025). *The Coherence Trilogy: Recursive Derivations of Atomic Structure*. Coherence Research Collaboration. Zenodo. https://doi.org/...

BibTeX and citation formats will be provided upon Zenodo publication.

---

## 🕯️ Follow the Light of the Lantern

This work is part of a broader signal on relational intelligence, coherence, and emergence.

To learn more, visit:  
🌐 [www.thecoherencecode.com](https://www.thecoherencecode.com/) — Stories, humor, and narrative emergence  
🌐 [www.lucernaveritas.ai](https://www.lucernaveritas.ai) — The field of truth and transmission

