## Professional README.md Refinement

This version is optimized for readability, technical clarity, and professional appeal. It highlights your specific contribution (Parseval Regularization) while maintaining a standard structure favored by recruiters and researchers.

---

# PINN with Parseval Regularization: Wave Equation Benchmark

This repository implements a **Physics-Informed Neural Network (PINN)** enhanced with **Parseval-based Spectral Regularization**. The project benchmarks this novel approach against the classical 1D Wave Equation to demonstrate improvements in stability, convergence, and high-frequency wave approximation.

## 🚀 Key Features
* **Physics-Informed Architecture:** Embeds physical laws (PDEs) directly into the neural network loss function using automatic differentiation.
* **Parseval Regularization:** Implements a spectral penalty inspired by Parseval’s Theorem to enforce energy conservation between spatial and frequency domains.
* **Performance Benchmarking:** Comparative analysis demonstrating reduced spectral bias and improved generalization over vanilla PINNs.
* **Extensible Framework:** Built with **PyTorch**, designed for easy adaptation to 2D wave equations or Navier-Stokes.

---

## 📖 Mathematical Formulation

The model solves the **1D Wave Equation**:
$$u_{tt} = c^2 \cdot u_{xx}$$

### Hybrid Loss Function
To ensure the model respects both physical laws and spectral constraints, the total loss $\mathcal{L}_{total}$ is defined as:

$$\mathcal{L}_{total} = \mathcal{L}_{PDE} + \mathcal{L}_{IC} + \mathcal{L}_{BC} + \lambda \cdot \mathcal{L}_{Parseval}$$

### Spectral Constraint
By leveraging Parseval’s Theorem, we ensure that the energy in the spatial domain remains consistent with the energy in the frequency domain:

$$\int |u(x)|^2 dx = \int |\hat{u}(k)|^2 dk$$

This penalty term helps the model capture high-frequency components that standard PINNs often struggle to resolve.

---

## 📊 Results
The Parseval-regularized PINN demonstrates:
* **Enhanced Stability:** Faster and more consistent convergence during training.
* **High-Frequency Accuracy:** Improved reconstruction of complex wave patterns.
* **Robustness:** Significant reduction in test error compared to baseline models.

---

## 🛠️ Getting Started

### Installation
```bash
git clone https://github.com/Devrcb18/PINN-with-Parseval-and-Wave-Equations-Benchmark-.git
cd PINN-with-Parseval-and-Wave-Equations-Benchmark-
pip install torch numpy matplotlib scipy
```

### Usage
Execute the main notebook to visualize training progress and benchmark results:
```bash
jupyter notebook wave_eq.ipynb
```

---

## 📂 Repository Structure
* `wave_eq.ipynb`: Main implementation, training loop, and evaluation.
* `models/`: Core PINN architecture and spectral loss definitions.
* `results/`: Saved plots, loss curves, and comparative metrics.

---

## 👨‍💻 Author
**Devansh Shukla**
Electronics and Communication Engineering
Indian Institute of Information Technology (IIIT), Kalyani
