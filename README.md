# GSoC-2026-PyMC-Preparation
# PyMC Bayesian Survival Analysis - GSoC 2026 PoC 🚀

[![PyMC](https://img.shields.io/badge/PyMC-v5.x-blue.svg)](https://www.pymc.io/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-brightgreen.svg)](https://www.python.org/)
[![GSoC](https://img.shields.io/badge/GSoC-2026-orange.svg)](https://summerofcode.withgoogle.com/)

> **A Proof of Concept for the NumFOCUS / PyMC GSoC 2026 Project: "Bayesian Survival Models"**

This repository contains a lightweight Proof of Concept (PoC) demonstrating a declarative, high-level Python API for Bayesian survival analysis. It abstracts complex tensor operations and PyMC computational graphs away from the end-user, providing a clean, CausalPy-style interface for time-to-event modeling.

## 🎯 Motivation

Building time-to-event models in PyMC currently requires manual, low-level log-likelihood specifications to handle censoring and truncation. This PoC demonstrates a potential architectural solution: encapsulating robust `PyTensor` math inside a declarative Python class.

This repository supports my official Google Summer of Code (GSoC) 2026 proposal to build a comprehensive Survival Analysis suite for PyMC. 

## ✨ What this PoC Demonstrates

The included Jupyter Notebook (`advanced_pymc_survival_poc.ipynb`) showcases:

1. **Stable PyTensor Math:** A custom log-likelihood function (`_weibull_aft_logp`) using `pytensor.tensor.where` to cleanly branch between the Probability Density Function (observed events) and the Survival Function (right-censored events).
2. **Covariate Integration:** An Accelerated Failure Time (AFT) formulation where the Weibull scale parameter ($\lambda$) dynamically updates based on a design matrix of covariates.
3. **Declarative API:** A high-level object-oriented interface (`BayesianSurvivalModel`). The user simply passes a Pandas DataFrame and column names, completely hiding the `with pm.Model():` context manager.
4. **Visual Diagnostics:** A built-in `.plot_expected_survival()` method that automatically extracts posterior samples to plot the expected baseline survival curve with uncertainty intervals.

## 🚀 Quick Start

To run the notebook locally, clone this repository and install the required dependencies:

```bash
# Clone the repository
git clone [https://github.com/Mithil-7/pymc-survival-poc.git](https://github.com/Mithil-7/pymc-survival-poc.git)
cd pymc-survival-poc

# Install dependencies
pip install pymc pytensor numpy pandas arviz matplotlib

# Launch Jupyter
jupyter notebook

##AUTHOR
Mithilesh A

GitHub: @Mithil-7

PyMC Discourse: @mithil_a

