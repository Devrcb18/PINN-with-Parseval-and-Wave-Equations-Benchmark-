---

# PINN with Parseval Regularization – Wave Equation Benchmark

This repository implements a **Physics-Informed Neural Network (PINN)** enhanced with **Parseval-based regularization** and benchmarks it on the classical **Wave Equation**.

The goal of this project is to improve stability and generalization of PINNs by incorporating spectral energy constraints inspired by Parseval’s theorem.

---

## @ Overview

Physics-Informed Neural Networks (PINNs) solve partial differential equations (PDEs) by embedding physical laws directly into the loss function. However, traditional PINNs can suffer from:

* Spectral bias
* Training instability
* Poor high-frequency approximation

This project introduces:

*  - Parseval-based spectral regularization
* - Wave equation benchmark implementation
* - Comparative analysis of baseline PINN vs Regularized PINN

---

## 📖 Problem Statement

We solve the **1D Wave Equation**:

[
u_{tt} = c^2 u_{xx}
]

Where:

* ( u(x,t) ) is the wave function
* ( c ) is the wave speed

The model enforces:

* PDE residual loss
* Initial condition loss
* Boundary condition loss
* Parseval energy regularization term

---


### Standard PINN Loss

[
\mathcal{L} = \mathcal{L}*{PDE} + \mathcal{L}*{IC} + \mathcal{L}_{BC}
]

###  Parseval Regularization

Using Parseval’s theorem, the total energy in spatial domain equals the energy in frequency domain:

[
\int |u(x)|^2 dx = \int |\hat{u}(k)|^2 dk
]

We introduce a spectral penalty to improve frequency learning behavior.

### Final Loss Function

[
\mathcal{L}*{total} = \mathcal{L}*{PINN} + \lambda \mathcal{L}_{Parseval}
]

Where:

* ( \lambda ) controls spectral regularization strength

---

## Implementation Details

* Framework: **PyTorch**
* Automatic differentiation for PDE residuals
* Fully connected neural network
* Fourier transform for spectral regularization
* Benchmark comparison against vanilla PINN

---

## Results

The Parseval-regularized PINN demonstrates:

* Better high-frequency reconstruction
* Improved convergence stability
* Reduced overfitting
* Lower test error compared to baseline

(You can add plots here if available.)

---

## 📂 Repository Structure

```
.
├── wave_eq.ipynb        # Main implementation notebook
├── models/              # Model definitions (if applicable)
├── utils/               # Utility functions
├── results/             # Plots and saved outputs
└── README.md
```

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/Devrcb18/PINN-with-Parseval-and-Wave-Equations-Benchmark-.git
cd PINN-with-Parseval-and-Wave-Equations-Benchmark-
```

2. Install dependencies:

```bash
pip install torch numpy matplotlib scipy
```

3. Run the notebook:

```bash
jupyter notebook wave_eq.ipynb
```

---

## Future Improvements -

* Extend to 2D wave equation
* Apply to Burgers’ equation and Navier–Stokes
* Adaptive frequency weighting
* Compare with Fourier Neural Operators (FNO)

---

##  Motivation

This project explores the intersection of:

* Physics-informed machine learning
* Spectral analysis
* PDE-constrained optimization

It is designed as both a research exploration and a benchmark implementation.

---

##  Author -

**Devansh Shukla**
Sophomore, IIIT Kalyani

---




