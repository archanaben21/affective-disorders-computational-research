# Multimodal Neuropsychiatry

## 1. Overview

This project investigates the relationship between brain structure, functional connectivity and clinical symptom dimensions in individuals with Major Depressive Disorder (MDD) and Bipolar Disorder (BD).

It aims to integrate clinical assessments with structural and functional magnetic resonance imaging (MRI) to explore shared and distinct patterns of brain organisation associated with psychiatric symptoms.

Rather than treating psychiatric disorders as isolated diagnostic categories, this research explores whether multimodal brain measurements can reveal meaningful dimensions of clinical variation across individuals.

The project combines computational neuroscience, statistical modelling, multimodal machine learning and topological data analysis.

## 2. Research Question

**Primary Research Question**

How are structural brain characteristics and functional connectivity associated with clinical symptom dimensions in individuals with Major Depressive Disorder and Bipolar Disorder?

**Secondary Research Questions**

1. Are there shared functional connectivity patterns between MDD and Bipolar Disorder?
2. Do structural brain characteristics explain additional variation in clinical symptom severity?
3. Can multimodal integration identify brain–symptom relationships beyond those observed using individual data modalities?
4. Can topological and network-based approaches provide additional insights into functional brain organisation?

## 3. Research Objectives

- Integrate clinical assessments and neuroimaging measurements.
- Investigate structural brain characteristics using anatomical MRI.
- Examine functional connectivity using resting-state fMRI.
- Identify relationships between clinical symptom dimensions and brain connectivity.
- Apply Canonical Correlation Analysis (CCA) for multimodal integration.
- Explore network-based and topological representations of brain connectivity.
- Evaluate the robustness and interpretability of computational findings.

## 4. Datasets

### Primary Dataset: Transdiagnostic Connectome Project (TCP)

**OpenNeuro: ds005237**

[https://openneuro.org/datasets/ds005237](https://openneuro.org/datasets/ds005237)

The TCP dataset provides a transdiagnostic research cohort containing clinical assessments and neuroimaging measurements.

Planned data modalities:

- Structural MRI (T1-weighted and T2-weighted)
- Functional MRI (resting-state and task-based)
- Clinical and behavioural assessments
- Participant-level demographic information

Clinical measures of interest include:

- Montgomery–Åsberg Depression Rating Scale (MADRS)
- Young Mania Rating Scale (YMRS)
- Other relevant clinical and behavioural questionnaires

The dataset will be inspected to establish participant eligibility, available imaging modalities, clinical variables and missing-data patterns.

### Potential Validation Datasets

**DIRECT Consortium Phase II**

[https://rfmri.org/DIRECTPhase2](https://rfmri.org/DIRECTPhase2)

A large-scale psychiatric neuroimaging resource that may support further investigation of depression-related and transdiagnostic functional connectivity patterns.

**REST-meta-MDD**

[https://rfmri.org/REST-meta-MDD](https://rfmri.org/REST-meta-MDD)

A multicentre major depressive disorder dataset that may support independent examination of depression-related functional connectivity findings.

Dataset compatibility and access conditions will be assessed before any cross-dataset analysis.

## 5. Methodology

The proposed research pipeline consists of the following stages.

### Stage 1: Data Acquisition and Quality Assessment

- Inspect BIDS dataset structure.
- Examine participant demographics and clinical metadata.
- Identify available MRI modalities.
- Assess missing values and duplicated observations.
- Evaluate imaging quality and participant eligibility.

### Stage 2: Clinical Data Processing

- Clean and standardise clinical variables.
- Examine depression and mania symptom distributions.
- Investigate missing clinical assessments.
- Perform exploratory statistical analysis.
- Assess potential demographic and clinical confounders.

### Stage 3: Structural Neuroimaging

- Inspect anatomical MRI using NIfTI tools.
- Explore regional brain measurements.
- Investigate grey matter characteristics.
- Examine cortical thickness and regional volume where supported by the processing pipeline.

### Stage 4: Functional Neuroimaging

- Examine resting-state fMRI.
- Assess head motion and imaging quality.
- Extract regional brain time series.
- Construct functional connectivity matrices.
- Investigate functional relationships between brain regions.

### Stage 5: Brain Network Analysis

- Examine network organisation.
- Calculate graph-based connectivity measures.
- Investigate regional and global network characteristics.
- Explore differences and similarities across clinical groups.

### Stage 6: Multimodal Integration

Canonical Correlation Analysis (CCA) will be explored to identify relationships between two feature spaces:

- Clinical symptom and assessment features.
- Structural and functional neuroimaging features.

The objective is to identify shared patterns of variation between clinical characteristics and brain measurements.

### Stage 7: Topological Data Analysis

Persistent homology and related topological approaches will be investigated to explore higher-order properties of brain connectivity.

These methods may help characterise connectivity structures that are not fully captured by conventional statistical or graph-based measures.

### Stage 8: Statistical Evaluation and Interpretation

- Statistical hypothesis testing.
- Multiple-comparison correction.
- Participant-level cross-validation where predictive modelling is appropriate.
- Sensitivity and robustness analysis.
- Explainable AI using SHAP where appropriate.
- Interpretation of findings in the context of existing neuroscience literature.

## 6. Technology Stack

| Area                 | Technologies                  |
| -------------------- | ----------------------------- |
| Programming          | Python                        |
| Data processing      | Pandas, NumPy                 |
| Neuroimaging         | NiBabel, Nilearn              |
| MRI preprocessing    | fMRIPrep, FreeSurfer          |
| Statistics           | SciPy, Statsmodels            |
| Machine learning     | Scikit-learn, PyTorch         |
| Brain connectivity   | NetworkX, Nilearn             |
| Multimodal analysis  | CCA                           |
| Topological analysis | Ripser, GUDHI                 |
| Explainable AI       | SHAP                          |
| Visualisation        | Matplotlib                    |
| Development          | Jupyter Notebook, Git, GitHub |

## 7. Repository Structure

```text
multimodal-neuropsychiatry/
│
├── README.md
├── requirements.txt
├── LICENSE
│
├── data/
│   ├── raw/
│   ├── derivatives/
│   └── processed/
│
├── notebooks/
│   ├── 01_dataset_exploration.ipynb
│   ├── 02_clinical_data_analysis.ipynb
│   ├── 03_structural_mri.ipynb
│   ├── 04_functional_mri.ipynb
│   ├── 05_brain_connectivity.ipynb
│   ├── 06_cca_multimodal.ipynb
│   ├── 07_topological_analysis.ipynb
│   └── 08_interpretation.ipynb
│
├── src/
│   ├── data_validation.py
│   ├── clinical_processing.py
│   ├── imaging_processing.py
│   ├── connectivity.py
│   ├── multimodal.py
│   └── evaluation.py
│
├── results/
│   ├── figures/
│   └── statistical_results/
│
└── docs/
    ├── research_question.md
    ├── data_dictionary.md
    └── methodology.md
```

## 8. Expected Outcomes

The project aims to produce:

1. A reproducible clinical and neuroimaging data-processing pipeline.
2. Exploratory structural and functional brain connectivity analyses.
3. Statistical characterisation of brain–symptom relationships.
4. Multimodal representations using CCA.
5. Exploratory topological analysis of brain connectivity.
6. Scientific visualisations and documented findings.
7. A reproducible research report suitable for further academic development.

These are intended research outputs, not established findings.

## 9. Research Considerations

The analysis will account for important methodological considerations:

- Age, sex, medication and other relevant clinical covariates.
- Scanner and acquisition-site variability.
- Functional MRI head motion.
- Missing clinical and imaging observations.
- Potential class imbalance.
- Multiple statistical comparisons.
- Data leakage during model development.
- Independent validation and reproducibility.

Predictive performance will not be interpreted as evidence of clinical diagnostic utility or causal relationships.

## 10. Data Ethics and Reproducibility

All analyses will use appropriately accessed research datasets and comply with their respective data-use conditions.

Raw neuroimaging data and participant-level clinical information will not be uploaded to this public repository.

The repository will prioritise:

- Reproducible code.
- Documented preprocessing decisions.
- Transparent analytical methods.
- Appropriate dataset attribution.
- Responsible interpretation of clinical research findings.

## 11. Current Progress

- [x] Research direction established.
- [x] Initial research question formulated.
- [x] Candidate datasets identified.
- [x] Preliminary methodology designed.
- [ ] Inspect TCP dataset metadata.
- [ ] Identify eligible participants and clinical variables.
- [ ] Establish clinical data-processing pipeline.
- [ ] Begin structural MRI analysis.
- [ ] Begin functional MRI analysis.
- [ ] Develop multimodal integration.
- [ ] Conduct statistical and topological analysis.
- [ ] Prepare research report.

## 12. References and Resources

- [Transdiagnostic Connectome Project – OpenNeuro](https://openneuro.org/datasets/ds005237)
- [DIRECT Consortium Phase II](https://rfmri.org/DIRECTPhase2)
- [REST-meta-MDD](https://rfmri.org/REST-meta-MDD)
- [BIDS Specification](https://bids-specification.readthedocs.io/)
- [Nilearn Documentation](https://nilearn.github.io/)
- [NiBabel Documentation](https://nipy.org/nibabel/)
- [fMRIPrep Documentation](https://fmriprep.org/)

---

**Project Focus:** Understanding the relationship between clinical symptom dimensions, brain structure and functional connectivity through reproducible computational neuroscience.

*This is an ongoing research project. All scientific findings will be reported only after appropriate data analysis and validation.*
