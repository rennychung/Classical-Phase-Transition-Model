# Classical Phase Transition Model

A minimal, reproducible simulation framework for first-order phase transitions in classical systems using a coordinated Langevin (SDE) approach. Supports 1D, 2D, and 3D models with robust diagnostics and visualization tools.

---

## Project Overview

This repository numerically investigates phase transitions and symmetry breaking in non-equilibrium classical systems.  
For complete methodology, theory, and results, see [Paper.md](./Paper.md).

---

## Generated Models and Outputs

Each core script below is paired with its primary output plot/model.  
**Drag and drop these images into your repo root (or an `images/` folder and update paths if preferred).**

---

### 1. 1D Bifurcation Analysis

**Script:** `run_1d_bifurcation.py`  
**Output:** Phase Space Bifurcation Map

![1D Bifurcation](classical_phase_transition_1d_bifurcation.png)

---

### 2. 2D Entropy/Order Dashboard

**Script:** `run_2d_dashboard.py`  
**Output:** Entropy vs Order Parameter Dashboard

![2D Dashboard](classical_phase_transition_2d_dashboard.png)

---

### 3. 3D Ensemble Statistics & Visualization

**Script:** `run_3d_ensemble.py`  
**Output:** 3D Particle Distribution and Ensemble Statistics

![3D Ensemble](classical_phase_transition_3d_ensemble.png)

---

### 4. Hysteresis Loop (First-Order Transition Test)

**Script:** `run_hysteresis_sweep.py`  
**Output:** Hysteresis Curve

![Hysteresis Loop](phase_transition_hysteresis.png)

---

### 5. Parameter Sweep & Robustness Test

**Script:** `stress_test_suite.py`  
**Output:** Parameter Test Results

![Parameter Test Results](phase_transition_parameter_test_results.png)

---

## Features

- Simulates first-order phase transitions via SDE in 1D, 2D, and 3D.
- Demonstrates the necessity of coordinated control of temperature and potential strength for symmetry breaking.
- Visualizes order parameters, entropy, bifurcation, and hysteresis.
- Includes automated stress testing and reproducibility scripts.

---

## Installation

**Requirements:**
- Python 3.8+
- numpy
- matplotlib
- scipy

Install dependencies with:

bash pip install numpy matplotlib scipy


---

## Usage

Each script can be run independently from the command line:

bash python run1dbifurcation.py python run2ddashboard.py python run3densemble.py python runhysteresissweep.py python stresstestsuite.py


---

## Scripts Overview

| Script                | Dimension | Main Analysis                      | Output File                                 |
|-----------------------|-----------|------------------------------------|---------------------------------------------|
| run_1d_bifurcation.py | 1D        | Phase Space Bifurcation Map        | classical_phase_transition_1d_bifurcation.png |
| run_2d_dashboard.py   | 2D        | Entropy/Order Parameter Dashboard  | classical_phase_transition_2d_dashboard.png   |
| run_3d_ensemble.py    | 3D        | Ensemble Statistics & Visualization| classical_phase_transition_3d_ensemble.png    |
| run_hysteresis_sweep.py| 2D       | Hysteresis Loop Check              | phase_transition_hysteresis.png               |
| stress_test_suite.py  | 1D/2D/3D  | Parameter Sweep & Robustness Test  | phase_transition_parameter_test_results.png   |

---

## Outputs

- Phase diagrams
- Order parameter and entropy plots
- Hysteresis curves
- Bifurcation maps
- 3D particle distribution snapshots

---

## Reproducibility

All simulation parameters are specified inside each script.  
For detailed scientific documentation, see [Paper.md](./Paper.md).

---

## License

[MIT License](LICENSE)

---

## Citation

If you use this code, please cite:  
Chung, R. et al., “Coordinated Phase Transitions: A Minimal Classical Model”, 2024.  
(Preprint and full citation info coming soon.)

---

**Questions or contributions?**  
Open an Issue or Pull Request on GitHub!
