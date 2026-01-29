# Unsupervised Anomaly Detection in CMS Dijet Events using Neural Spline Flows

This repository contains the analysis code used in the paper:

**“Exploring Isolated Dijet Event Clusters with Neural Spline Flow Density Estimation”**  
(submitted to *The European Physical Journal C*)

The analysis implements a fully unsupervised, data-driven anomaly detection strategy applied to CMS Open Data dijet events using neural spline flow (NSF) density estimation.

---

## Overview

The workflow implemented in this repository consists of:

1. Cleaning and validation of CMS Open Data dijet events  
2. Construction of a high-level feature representation (61 observables)  
3. Training of a neural spline flow density estimator  
4. Likelihood-based anomaly scoring  
5. Selection of rare events in the extreme tail of the score distribution  
6. Robustness and validation studies, including:
   - Feature-level statistical tests (KS tests)
   - Mass decorrelation and sculpting checks
   - Permutation-based control tests
   - Training stability tests across random seeds

No simulated signal samples or supervised labels are used at any stage.

---

## Repository Contents
├── anomaly_detection.ipynb

├── README.md

### `anomaly_detection.ipynb`

A single, self-contained Jupyter notebook implementing the full analysis pipeline, including:

- Data loading from preprocessed CMS Open Data ROOT files  
- Feature preprocessing and standardization  
- Neural spline flow model definition and training  
- Anomaly score computation  
- Validation plots and statistical diagnostics  

Additional exploratory analyses (e.g., bump-hunting and sideband tests) are included for transparency but are **not** used to support the main conclusions of the paper.

---

## Data

The analysis is based on **CMS Open Data dijet events**.  
Due to size constraints and licensing considerations, the raw and intermediate ROOT files are **not included** in this repository.

The notebook assumes access to:
- A cleaned CMS ROOT file containing the final event-level features
- A NumPy file containing the anomaly scores produced by the trained model

These inputs are described in the notebook and in the paper.

---

## Reproducibility Notes

- The analysis is fully unsupervised and trained on the full dataset.
- Random seeds are fixed where applicable to allow reproducibility.
- All plots shown in the paper can be reproduced from the notebook given the required input files.
- The repository is intended to provide **methodological transparency**, not a turn-key reprocessing of CMS data.

---

## Scope and Limitations

This repository supports an **exploratory physics analysis**.  
No claims of new physics or statistically significant discoveries are made.

The methods demonstrated here are intended as model-agnostic tools for studying rare and structured deviations in collider data.

---

## License

This code is released for academic and non-commercial use only.  
Users are responsible for complying with CMS Open Data usage policies when accessing the underlying datasets.

---

## Contact

For questions related to the analysis or code, please contact the corresponding author listed in the paper.
