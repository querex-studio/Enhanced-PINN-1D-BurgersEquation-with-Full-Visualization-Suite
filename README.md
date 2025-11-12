# Enhanced PINN for 1D Burgers’ Equation

## Overview
This project implements an enhanced Physics-Informed Neural Network (PINN) to solve the 1D viscous Burgers’ equation:
\[
\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = \nu \frac{\partial^2 u}{\partial x^2}
\]
The code integrates analytical validation, conservation analysis, and six advanced visualizations to evaluate both learning dynamics and physical correctness across multiple viscosity regimes.

## Features
- Fully modular PINN in PyTorch  
- Analytical reference solver (finite-difference, adaptive CFL stability)  
- Multi-viscosity testing (shock, transition, diffusion regimes)  
- Conservation tracking: mass, energy, and enstrophy  
- 6 visualization sets automatically saved to `./figures/`:
  1. Simulation environment  
  2. PINN-predicted solution  
  3. Analytical comparison  
  4. Multi-viscosity comparison  
  5. Conservation laws  
  6. Training history  

## Requirements
- Python 3.9+
- PyTorch
- NumPy
- Matplotlib

Install dependencies:
```bash
pip install torch numpy matplotlib
```

## Key Findings
- Low viscosity (ν ≤ 0.005): Shock-like nonlinear regimes
- Intermediate viscosity (0.005 < ν < 0.02): Transitional flow
- High viscosity (ν ≥ 0.02): Diffusion-dominated smooth decay
- PINN achieves L² error < 1e-3 for all regimes
