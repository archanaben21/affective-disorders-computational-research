# Persistent Homology of Resting-State Functional Connectivity

### Predicting Mood-Symptom Dimensions in Major Depression and Bipolar Disorder

**Dataset:** OpenNeuro ds005237 – Transdiagnostic Connectome Project (TCP)

**Project period:** September – December 2026

## Overview

This research investigates whether topological features of resting-state functional brain connectivity can provide additional information about depressive and manic symptom severity in individuals with Major Depressive Disorder (MDD) and Bipolar Disorder.

Using functional MRI (fMRI), functional connectivity analysis and Topological Data Analysis (TDA), the project aims to compare persistent homology features against conventional brain-network measures.

## Research Objectives

- Investigate resting-state functional connectivity across clinical and healthy comparison populations.
- Extract topological features using persistent homology.
- Characterise connected components (H0) and loops (H1).
- Examine relationships between brain-network topology and mood-symptom dimensions.
- Evaluate whether persistent homology improves prediction beyond conventional graph and minimum-spanning-tree measures.

## Dataset

**OpenNeuro: ds005237 – Transdiagnostic Connectome Project**

The dataset includes structural MRI, resting-state fMRI, task fMRI, clinical assessments, demographic information and behavioural measures.

The analysis will investigate:
- Major Depressive Disorder
- Bipolar Disorder
- Healthy comparison participants

The final sample size will be determined following participant-level data auditing, clinical data verification and MRI quality control.

## Methodology

1. Dataset discovery and participant-level audit
2. MRI preprocessing using fMRIPrep
3. Motion correction and quality control
4. Brain parcellation using Schaefer-100
5. Functional connectivity estimation
6. Persistent homology (H0 and H1)
7. Graph-theoretical and minimum-spanning-tree analysis
8. Predictive modelling and statistical validation
9. Robustness analysis and interpretation

## Novel Research Application

The central contribution is to investigate the **incremental predictive value of persistent homology** for depressive and manic symptom dimensions in a transdiagnostic mood-disorder population.

Rather than simply applying topological methods to brain connectivity, this research will test whether they capture information beyond conventional network measures.

Primary outcomes:
- MADRS – depressive symptom severity
- YMRS – manic symptom severity

Subject to availability and completeness in the dataset.

## Technologies

- Python
- PyCharm
- NumPy and Pandas
- Nilearn
- NiBabel
- fMRIPrep
- Scikit-learn
- Ripser
- Matplotlib
- SciPy

## Project Status

**Current phase:** Dataset auditing and research pipeline development.

Pilot analyses have explored MRI quality control, regional time-series extraction, functional connectivity and preliminary persistent homology.

Group-level analysis, preprocessing validation and clinical integration remain in progress.

## Expected Outcomes

- Participant-level MRI and clinical data inventory
- Functional connectivity matrices
- Persistent homology feature representations
- Conventional network feature comparisons
- Predictive modelling results
- Reproducible research pipeline
- Scientific manuscript

## Reproducibility and Data

Analysis code and derived research outputs will be organised for reproducibility. Raw participant-level imaging data will not be redistributed through this repository. Dataset access and citation will follow OpenNeuro and TCP requirements.

---

**Research focus:** Computational Neuroscience | Functional Connectivity | Topological Data Analysis | Persistent Homology | Trustworthy Machine Learning
