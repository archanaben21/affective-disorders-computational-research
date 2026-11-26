# Functional Connectivity in Psychiatric Disorders
### A Reproducible Computational Neuroimaging Study

---

## Overview

This project investigates resting-state functional connectivity in psychiatric disorders using functional magnetic resonance imaging (fMRI).

The study aims to examine differences in functional brain organisation between individuals with depression, bipolar disorder and healthy comparison participants. Using neuroimaging, statistical analysis and computational methods, the research explores patterns of interregional brain connectivity and their potential associations with clinical characteristics.

The project uses publicly available neuroimaging data from the Transdiagnostic Connectome Project hosted on OpenNeuro.

## Research Question

**Do resting-state functional connectivity patterns differ between individuals with depression, bipolar disorder and healthy comparison participants?**

## Research Objectives

- Characterise resting-state functional brain activity using BOLD time series.
- Estimate functional connectivity between predefined brain regions.
- Investigate group-level differences in functional connectivity.
- Examine network organisation using graph-theoretical measures.
- Explore associations between connectivity features and clinical characteristics.
- Evaluate the potential of machine learning for identifying group-level connectivity patterns.

## Dataset

| Attribute | Description |
|---|---|
| Dataset | Transdiagnostic Connectome Project |
| Repository | OpenNeuro |
| Dataset identifier | ds005237 |
| Imaging modalities | Structural MRI and functional MRI |
| Primary imaging data | Resting-state fMRI |
| Study population | Psychiatric and healthy comparison participants |

**Data source:** [OpenNeuro – ds005237](https://openneuro.org/datasets/ds005237)

## Methodology

The research follows a structured computational workflow:

1. **Data validation:** Dataset inspection, participant identification and imaging quality assessment.
2. **Clinical characterisation:** Demographic analysis, diagnostic group identification and clinical variable exploration.
3. **Structural imaging:** Anatomical image inspection and structural feature extraction.
4. **Functional imaging:** BOLD signal extraction, quality control and functional connectivity estimation.
5. **Network analysis:** Examination of connectivity patterns and graph-theoretical properties.
6. **Statistical modelling:** Group comparisons, effect-size estimation and association analysis.
7. **Machine learning:** Exploratory predictive modelling with appropriate validation and interpretation.

## Computational Environment

| Area | Tools |
|---|---|
| Programming | Python |
| Neuroimaging | NiBabel, Nilearn |
| Data processing | NumPy, Pandas |
| Statistical analysis | SciPy, Statsmodels |
| Machine learning | Scikit-learn |
| Visualisation | Matplotlib, Seaborn |
| Development | Jupyter Notebook, Git, GitHub |

## Repository Structure

```text
functional-connectivity/
│
├── data/
│   ├── raw/
│   ├── clinical/
│   └── processed/
│
├── notebooks/
│   ├── 01_dataset_validation.ipynb
│   ├── 02_clinical_analysis.ipynb
│   ├── 03_structural_mri.ipynb
│   ├── 04_functional_connectivity.ipynb
│   ├── 05_multimodal_analysis.ipynb
│   ├── 06_statistical_ml_analysis.ipynb
│   └── 07_research_results.ipynb
│
├── figures/
├── results/
├── manuscript/
├── requirements.txt
└── README.md
```

## Research Outputs

The planned outputs include:

- Quality-controlled neuroimaging data.
- Regional BOLD time-series measurements.
- Functional connectivity matrices.
- Brain network representations.
- Statistical comparisons across diagnostic groups.
- Reproducible analytical workflows.
- A scientific manuscript for peer-reviewed publication.

These outputs are planned research deliverables; conclusions will be based on the completed analyses.

## Reproducibility and Data Ethics

The project prioritises transparent analytical procedures, documented preprocessing decisions, reproducible computational workflows and appropriate statistical validation.

All data handling will follow the dataset's access conditions, licensing requirements and applicable research ethics principles. Raw participant-level imaging data will not be redistributed through this repository.

## Researcher

**Archana Prajapati**

MSc Data Science | BSc Physics

Research interests: Computational Neuroscience, Neuroimaging, Functional Connectivity, Biomedical AI and Trustworthy Machine Learning.

- GitHub: [archanaben21](https://github.com/archanaben21)
- ORCID: [0009-0001-8353-7166](https://orcid.org/0009-0001-8353-7166)

---

*Research in progress | November 2026*
