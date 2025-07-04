# Methane Combustion Modeling using ChemNODE

This repository contains an implementation of **Neural Ordinary Differential Equations (Neural ODEs)** for modeling the time evolution of thermochemical scalars in a methane combustion process. The project draws inspiration from the [ChemNODE framework](https://doi.org/10.1016/j.egyai.2021.100118), which proposes an efficient data-driven approach to chemical kinetics using deep learning.

---

## 🚀 Project Overview

Traditional combustion solvers rely on stiff ODE solvers to capture the complex dynamics of chemical species. In this work, we replace the stiff solver with a **Neural ODE**, where the source terms are learned using shallow feedforward neural networks.

We apply the method to methane combustion using data generated from the **GRI-Mech v3.0** mechanism, and integrate neural predictions over time to reconstruct the thermochemical state.

---

## 📁 Contents

- `notebook.ipynb`: Main Jupyter notebook containing data loading, model training, and evaluation.
- `training_data.csv`: Generated time-series data for training (species concentrations and temperature).
- `testing_data.csv`: Separate time-series data used for evaluation.
- `models/`: Saved PyTorch models for each species.

---

## 🔍 Methodology

- Data generated using Cantera and GRI-Mech 3.0 mechanism for various initial conditions.
- Forward-mode sensitivity analysis used for training stability.
- A separate neural network is trained for each major species.
- Training loss is calculated based on the discrepancy between the integrated NeuralODE solution and ground-truth thermochemical evolution.

---

## 📊 Results

- The model accurately reproduces the temperature and species evolution.
- Computational efficiency is improved by avoiding re-evaluation of full source terms.
- The framework generalizes across a range of equivalence ratios and temperatures.

---

## 🔧 Dependencies

Make sure the following libraries are installed:

```bash
torch
numpy
matplotlib
scipy
pandas
