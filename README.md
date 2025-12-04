# Coordinated Phase Transitions: A Minimal Classical Model

This repository presents a numerical simulation of a first-order phase transition modeled using the Langevin Equation (SDE) in 1D, 2D, and 3D. The transition from a disordered, high-entropy state ("Gas") to an ordered, low-entropy state ("Crystal") is achieved through the coordinated scaling of two thermodynamic control variables: **Effective Temperature ($T$)** and **Potential Energy Strength ($V$)**.

The framework explores minimal conditions necessary for symmetry breaking in classical non-equilibrium systems.


## Model Formulation

The system's dynamics are governed by a single control parameter, **$\lambda$**, which scales the driving forces simultaneously:

- **Potential Scaling (Drift Term):** The attractive force of the potential wells scales linearly with $\lambda$.  
- **Thermal Cooling (Noise Term):** The effective temperature (noise intensity) decreases rapidly (cubically) as $\lambda$ increases.

The generalized Stochastic Differential Equation (SDE) is:

$$
d\mathbf{x} = -\lambda \nabla V(\mathbf{x}) \, dt + \sqrt{D(\lambda)} \, d\mathbf{W}_t
$$

Where:

- $V(\mathbf{x})$ is a periodic, multi-well potential (e.g., $V(\mathbf{x}) \propto \sum_i \cos(4 \pi x_i)$)  
- $D(\lambda) \propto (1 - \lambda)^3$ is the $\lambda$-dependent diffusion coefficient  
- $\lambda \in [0, 1]$ is the single, dimensionless control parameter  


## Core Scripts and Simulations

| Script | Dimension | Primary Analysis | Output File |
|--------|-----------|----------------|-------------|
| `run_1d_bifurcation.py` | 1D | Phase Space Bifurcation Map | `classical_phase_transition_1d_bifurcation.png` |
| `run_2d_analysis_dashboard.py` | 2D | Entropy / Order Parameter Sweep vs Control | `classical_phase_transition_2d_dashboard.png` |
| `run_3d_ensemble_analysis.py` | 3D | Ensemble Statistics & 3D Visualization | `classical_phase_transition_3d_ensemble.png` |
| `run_hysteresis_sweep.py` | 2D | Hysteresis Loop (First-Order Check) | `classical_phase_transition_hysteresis.png` |


### 1. 2D Analysis Dashboard (`run_2d_analysis_dashboard.py`)

Demonstrates the core thesis: the phase transition only occurs when potential strengthening and thermal cooling are coordinated.

Metrics plotted vs control parameter $\lambda$:

- **Order Parameter:** Measures spatial coherence (crystallinity)  
- **Normalized Entropy:** Measures thermodynamic disorder  

Includes a Control Group (Cooling Only, $\lambda \nabla V = 0$) to show that the entropy drop is specifically due to the potential.

<img width="1000" height="600" alt="classical_phase_transition_1d_bifurcation" src="https://github.com/user-attachments/assets/c6d354d0-d4c3-488b-aaaa-00accc04849d" />


### 2. 1D Bifurcation Plot (`run_1d_bifurcation.py`)

Visually confirms bifurcation of the particle density in phase space:

- **Low $\lambda$ (High $T$):** Particles diffuse across the domain (single branch)  
- **High $\lambda$ (Low $T$):** Particles localize into energy minima (multiple branches)  

<img width="1400" height="1000" alt="classical_phase_transition_2d_dashboard" src="https://github.com/user-attachments/assets/7d1f6d86-87fc-4481-9704-f50e48a0989c" />


### 3. 3D Ensemble Analysis (`run_3d_ensemble_analysis.py`)

Provides statistical evidence in 3D, showing the bulk shift from Gas ($\lambda=0$) to Crystal ($\lambda=1$).

Key snapshots of particle distributions:

- **$\lambda = 0.0$:** High entropy, disordered Gas  
- **$\lambda = 0.6$:** Transition zone, partial ordering  
- **$\lambda = 1.0$:** Low entropy, ordered Crystal  

<img width="1500" height="600" alt="classical_phase_transition_3d_ensemble" src="https://github.com/user-attachments/assets/9a637b8f-1da3-4dab-b269-ef03fbf1ea19" />


### 4. Hysteresis Sweep (`run_hysteresis_sweep.py`)

Sweeps the control parameter $\lambda$ up (heating) and down (cooling) to check for a separation between forward and backward paths in the Order Parameter ($M$).

- Presence of a loop confirms the system exhibits **hysteresis**, a signature of a first-order phase transition.

<img width="1400" height="600" alt="phase_transition_hysteresis" src="https://github.com/user-attachments/assets/4ab98e3f-da79-4ec4-ab2d-1447015d5c4c" />

### 5. Stress Test Suite

Performs automated robustness checks across dimensions, particle numbers, and control parameter sweeps

<img width="1800" height="600" alt="phase_transition_parameter_test_results" src="https://github.com/user-attachments/assets/af10984e-7324-43c5-8fe2-073ea42031d7" />

## Running the Simulations

### Prerequisites

- Python 3.8+  
- `numpy`, `matplotlib`, `scipy`

### Execution

Run each script independently:

```bash
# Generate the 1D bifurcation map
python run_1d_bifurcation.py

# Generate the 2D dashboard (Entropy vs Order)
python run_2d_analysis_dashboard.py

# Generate the 3D visualization and statistics
python run_3d_ensemble_analysis.py

# Generate the Hysteresis loop
python run_hysteresis_sweep.py

# Generate the Stress test suite
python run_stress_test_suite.py
