# GALVA-Q: Hybrid Quantum–Machine Learning Framework for Electroplating Slot Optimisation

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)
[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXXX) <!-- Replace with your Zenodo DOI after archiving -->

**Paper**: GALVA-Q: A Hybrid Quantum--Machine Learning Framework for Electroplating Slot Optimisation on Industrial Cylindrical Racks  
**Author**: Fabio Buffoli, Università degli Studi di Brescia  
**Email**: fabio.buffoli@unibs.it

---

## 📋 Overview

**GALVA-Q** is a hybrid quantum–machine learning framework that solves the industrial slot-assignment problem in gold electroplating on cylindrical titanium racks.  

It combines:
- A physics-informed **Quadratic Unconstrained Binary Optimisation (QUBO)** model based on Faraday’s law,
- The **Quantum Approximate Optimisation Algorithm (QAOA)** executed on the Quafu ScQ-Sim10 cloud quantum simulator (10-qubit subproblem),
- A **physics-guided XGBoost** model (ML Slot Prior) trained on 92,160 Faraday-labelled samples,
- A fast greedy placement algorithm that scales the quantum solution to the full 120-slot industrial frame.

The framework achieves near-perfect thickness uniformity (±0.02 µm tolerance), zero gold waste at optimal capacity, and dramatically outperforms both physics-only and simulated-annealing baselines.

This repository contains all code, LaTeX sources, and data generators needed to reproduce the results presented in the paper.

---

## 📁 Repository Structure

```bash
galva-q/
├── README.md
├── LICENSE
├── galvaq_paper.tex              # Full Overleaf-compatible LaTeX source
├── references.bib
├── code/
│   ├── main_pipeline.py
│   ├── qubo_builder.py
│   ├── qaoa_runner.py            # QAOA on Quafu ScQ-Sim10
│   ├── ml_slot_prior.py          # XGBoost training & inference
│   ├── faraday_model.py
│   ├── greedy_placement.py
│   ├── utils.py
│   └── requirements.txt
├── data/
│   └── generate_training_data.py # Script to reproduce the 92k dataset
├── figures/                      # All figures used in the paper (PDF/PNG)
├── results/                      # Example outputs and tables
├── galvaq_full_project_v1.0.zip  # Complete self-contained archive (recommended download)
└── .gitignore
