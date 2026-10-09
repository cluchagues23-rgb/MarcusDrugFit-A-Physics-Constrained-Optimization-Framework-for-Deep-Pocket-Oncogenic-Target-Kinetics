# MarcusDrugFit

> **A Physics-Constrained Optimization Framework for Parameter Identifiability in Deep-Pocket Oncogenic Target Kinetics**

[![DOI](https://zenodo.org)](https://doi.org)
[![License: MIT](https://shields.io)](https://opensource.org)

## Overview

`MarcusDrugFit` is a physics-constrained mathematical pharmacology optimization tool written in Python. The framework resolves the classical problem of **structural parameter unidentifiability** in deep-pocket drug-target binding by coupling non-adiabatic Marcus electron-transfer theory with macroscopic cellular population dose-response equations. 

By utilizing first-principles physics barriers (\(\nu_{\text{eff}}\)) and crystallographic structural constraints (\(K_d\), \(R_{\text{pocket}}\)) extracted directly from the [RCSB Protein Data Bank](https://rcsb.org), this software collapses multi-dimensional mathematical parameter degeneracies to successfully isolate and recover hidden microscopic kinetic rates (\(k_C\), \(k_{\text{off,q}}\)) out of standard, noisy macroscopic laboratory assay data.

## Features

- **Marcus Theory Integration:** Explicit continuum electrostatics engine calculating localized external reorganization energy (\(\lambda_{\text{ext}}\)) scaling as a step-function of solvent exclusion boundary changes (\(\varepsilon_{\text{local}} = 80.4 \rightarrow 2.0\)).
- **Physics-Constrained Optimization Loop:** Uses a custom curve-fitting environment anchored to the fundamental atomic transition attempt frequency (\(\nu_{\text{eff}} \approx 6.46 \times 10^{12} \text{ s}^{-1}\)).
- **Target Profiles:** Pre-parameterized baseline configurations for two high-impact oncogenic cavities:
  1. **KRAS G12C (Switch-II Pocket):** Calibrated via PDB ID `4L8G` (\(R_{\text{pocket}} = 1.5\text{ nm}\), Sotorasib baseline reference \(K_d = 1.0 \; \mu\text{M}\)).
  2. **STAT3 (SH2 Domain):** Calibrated via PDB ID `6NJS` (\(R_{\text{pocket}} = 1.4\text{ nm}\), SD-36 baseline reference \(K_d = 14\text{ nM}\)).
- **Identifiability Diagnostic:** Embedded algorithmic check using Jacobian matrix singular value decompositions to distinguish between structural and practical unidentifiability profiles under noisy conditions.

## Installation & Setup

### Prerequisites
- Python 3.10 or higher
- `pip` package manager

### Standard Installation
Clone the repository and install the verified scientific dependency manifest:

```bash
git clone https://github.com
cd marcus-drug-fit
pip install -r requirements.txt
```

## Usage Example

To run the unified diagnostic test comparison between a blind empirical pharmacology fit and the physics-constrained configuration, execute the primary source script:

```bash
python marcus_drug_fit.py
```

## Repository Architecture

- `marcus_drug_fit.py`: The complete core algorithmic architecture containing the simulation loop, noise injector, and optimization comparisons.
- `requirements.txt`: The structural dependency locks required for numerical execution.
- `README.md`: System operational reference guide.

## Citation

If you use this computational modeling tool or framework in your research, please cite our corresponding journal article:

```bibtex
@article{cluchaguesmarcus2026,
  author  = {Cluchagues Abam, L. M. and Mfabo Kameni, I. H. and Eya'ane Meva, F.},
  title   = {A Physics-Constrained Marcus-Theory Optimization Framework Resolves Parameter Unidentifiability in Deep-Pocket Oncogenic Drug Kinetics},
  journal = {In Silico Pharmacology},
  year    = {2026},
  volume  = {x},
  pages   = {xx-xx},
  doi     = {10.5281/zenodo.23250915}
}
