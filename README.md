# Optimal Control of Complex Networks

Numerical experiments for **optimal control of nonlinear dynamical systems and complex networks**, including network-based control strategies, dynamic optimization, control-energy analysis, and stochastic dynamical simulations.

The project uses Python-based scientific computing tools together with **GEKKO** and the **IPOPT** nonlinear optimization solver to formulate and solve finite-time optimal-control problems on networked systems.

## Overview

Controlling a complex dynamical network requires determining where control inputs should be applied and how those inputs should evolve in time in order to steer the system toward a desired state while minimizing the required control effort.

This repository contains numerical experiments exploring these questions for nonlinear network dynamics.

The workflow includes:

- construction and visualization of complex networks;
- identification of selected control nodes and links;
- formulation of nonlinear state dynamics;
- time-dependent optimal-control variables;
- constrained dynamic optimization using GEKKO;
- numerical solution with IPOPT;
- comparison of alternative control configurations;
- calculation of control-energy costs;
- visualization of state and control trajectories;
- exploratory simulations of stochastic dynamical systems.

## Mathematical Setting

A networked dynamical system can be represented schematically as

\[
\dot{x}_i = F_i(\mathbf{x},\mathbf{u}),
\]

where \(x_i(t)\) represents the state of node \(i\) and \(\mathbf{u}(t)\) denotes the set of time-dependent control inputs.

The optimization problem is formulated by searching for control trajectories that steer the system toward a target state while penalizing excessive control effort.

A typical objective has the form

\[
J =
\Phi(\mathbf{x}(T))
+
\int_0^T
\left[
\sum_k u_k^2(t)
+
V(\mathbf{x}(t))
\right]dt,
\]

where

- \(T\) is the control horizon,
- \(u_k(t)\) are control inputs,
- \(\Phi\) penalizes deviation from the desired terminal state,
- \(V(\mathbf{x})\) describes the nonlinear state-dependent contribution to the objective.

The notebooks solve the resulting nonlinear dynamic optimization problems numerically.

## Repository Structure

```text
optimal-control/
│
├── optimal control.ipynb
├── optimal2.ipynb
├── Stochastic optimal control.ipynb
├── Nonlinear_Control_Of_Complex_Networks.pdf
└── LICENSE
```

### `optimal control.ipynb`

Main numerical experiments for optimal control of nonlinear complex networks.

The notebook includes:

- graph construction with NetworkX;
- definition of different control-node configurations;
- nonlinear network dynamics;
- time-dependent manipulated variables;
- terminal-state constraints;
- dynamic optimization with GEKKO;
- IPOPT-based numerical optimization;
- state-trajectory visualization;
- optimal-control trajectory visualization;
- control-energy calculations;
- comparison between alternative sets of controlled nodes.

### `optimal2.ipynb`

Additional network configurations and optimal-control experiments.

This notebook investigates how different choices of controlled nodes and network connectivity affect the optimal trajectories and control effort.

### `Stochastic optimal control.ipynb`

Exploratory stochastic-dynamics simulations.

It includes numerical simulation of stochastic differential equations, including a noisy damped oscillator and noise-driven dynamical trajectories.

### `Nonlinear_Control_Of_Complex_Networks.pdf`

Background material related to nonlinear control of complex networks.

## Technologies

The project is implemented primarily in Python using:

- **NumPy** — numerical computations and array operations
- **SciPy** — numerical integration
- **Matplotlib** — visualization
- **NetworkX** — network construction and analysis
- **GEKKO** — dynamic optimization and optimal-control formulation
- **IPOPT** — nonlinear optimization
- **Jupyter Notebook** — interactive numerical experiments

## Installation

Clone the repository:

```bash
git clone https://github.com/laya-laya/optimal-control.git
cd optimal-control
```

Create a virtual environment if desired:

```bash
python -m venv .venv
```

Activate it on Linux/macOS:

```bash
source .venv/bin/activate
```

or on Windows:

```bash
.venv\Scripts\activate
```

Install the main dependencies:

```bash
pip install numpy scipy matplotlib networkx gekko jupyter
```

Then start Jupyter:

```bash
jupyter notebook
```

and open one of the notebooks.

## Example Workflow

The network-control notebooks follow approximately this workflow:

```text
Network definition
        ↓
Selection of control nodes / links
        ↓
Definition of nonlinear state equations
        ↓
Definition of time-dependent control variables
        ↓
Specification of target state and objective
        ↓
Dynamic optimization with GEKKO / IPOPT
        ↓
Optimal state and control trajectories
        ↓
Control-energy analysis
```

## Control-Energy Analysis

In addition to finding feasible optimal trajectories, the notebooks calculate quantities based on the squared control amplitudes,

\[
E(t)=\sum_k u_k^2(t),
\]

and integrate them over the control interval to quantify the total control effort.

This makes it possible to compare different control configurations not only by whether they reach the desired state, but also by the energetic cost required to do so.

## Research Context

This repository was developed as part of exploratory work on **control theory, nonlinear dynamical systems, and complex-network dynamics**.

The main computational themes are:

- optimal control;
- nonlinear dynamics;
- network science;
- numerical optimization;
- dynamical-system simulation;
- stochastic processes;
- scientific computing.

## Reproducibility Note

These notebooks were developed as research and exploratory notebooks rather than as a packaged Python library. Some cells contain experiment-specific parameter choices and stored outputs, and minor modifications may be required when running them with newer versions of Python or scientific-computing libraries.

## License

This project is distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.

## Author

**Laya Parkavousi**

Computational physicist working on nonlinear dynamical systems, complex systems, scientific computing, and data-driven modeling.

GitHub: [@laya-laya](https://github.com/laya-laya)
