# Topological Characterisation of Resting-State Functional Brain Connectivity Using Persistent Homology

**Research Area:** Computational Neuroscience | Neuroimaging | Topological Data Analysis

## Overview

This project investigates the topological organisation of resting-state functional brain connectivity using Topological Data Analysis (TDA).

Persistent Homology and Vietoris–Rips filtration are applied to functional connectivity representations to examine H0 and H1 topological features across filtration scales.

## Research Objectives

- Construct functional connectivity matrices from rs-fMRI.
- Apply chord-distance transformation.
- Perform Vietoris–Rips filtration.
- Extract H0 and H1 persistence features.
- Investigate filtration-threshold sensitivity.
- Characterise functional networks using graph theory.
- Develop a reproducible computational workflow.

## Dataset

- **Source:** [OpenNeuro](https://openneuro.org/datasets/ds005237/versions/1.1.3)
- **Accession:** ds005237
- **Version:** 1.1.3
- **Modality:** Resting-state fMRI
- **Atlas:** Schaefer 2018
- **Analysed pilot regions:** 74

## Methodology

1. Dataset inspection and validation
2. fMRI signal preparation
3. Regional time-series extraction
4. Pearson functional connectivity
5. Chord-distance construction
6. Vietoris–Rips persistent homology
7. H0/H1 feature extraction
8. Filtration-threshold sensitivity analysis
9. Graph-theoretical characterisation
10. Visualisation and scientific interpretation

## Pilot Results

| Metric | Result |
|---|---:|
| fMRI volumes | 488 |
| Extracted regions | 97 |
| Valid connectivity regions | 74 |
| Connectivity matrix | 74 × 74 |
| H0 features | 74 |
| H1 features | 18 |

*Results represent a single-participant pilot analysis, not population-level or clinical findings.*

## Technologies

Python · NumPy · Pandas · SciPy · NiBabel · Nilearn · Ripser · Matplotlib · Seaborn

## Repository Structure

```text
neuroscience_project/
│
├── scripts/
│   ├── 01_dataset_audit.py
│   ├── 02_validate_downloads.py
│   ├── 03_inspect_bold_data.py
│   ├── 04_preprocess_fmri.py
│   ├── 05_extract_timeseries.py
│   ├── 06_inspect_connectivity.py
│   ├── 07_functional_connectivity.py
│   ├── 08_persistent_homology.py
│   ├── 09_extract_topological_features.py
│   └── 10_visualise_and_export_results.py
│
├── results/
│   ├── dataset_audit/
│   ├── distance_matrix.npy
│   ├── persistence_H0.npy
│   ├── persistence_H1.npy
│   ├── topological_features.csv
│   ├── milestone8_threshold_sensitivity.csv
│   ├── milestone9_network_metrics.csv
│   └── milestone9_persistence_summary.csv
│
├── figures/
│   ├── functional_connectivity_matrix.png
│   ├── persistence_diagram_H0.png
│   ├── persistence_diagram_H1.png
│   └── network_visualisation.png
│
├── docs/
│   └── methodology.md
│
├── README.md
├── requirements.txt
├── .gitignore
├── scientific_report.md
└── reproducibility_manifest.json
```

## Limitations and Future Work

The current analysis is preliminary and based on one participant. Further work will address preprocessing quality, motion correction, nuisance regression, topological stability and multi-participant validation.

Future investigations will explore the relationship between functional network topology and affective disorders.
