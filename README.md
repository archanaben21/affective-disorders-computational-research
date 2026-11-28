# Topological Characterisation of Resting-State Functional Brain Connectivity Using Persistent Homology

## 1. Project Overview

This project investigates the topological organisation of resting-state functional brain connectivity using **Topological Data Analysis (TDA)**, particularly Persistent Homology.

Using resting-state functional MRI (rs-fMRI) data from the Transdiagnostic Connectome Project (TCP), the study constructs functional connectivity networks and examines their structural organisation through graph theory and persistent homology.

The analysis focuses on identifying connected components and higher-dimensional topological structures (loops) across multiple filtration scales.

**Dataset:** OpenNeuro ds005237  
**Dataset version:** 1.1.3  
**Atlas:** Schaefer 2018  
**Analysis scope:** Single-participant exploratory analysis  
**Participant analysed:** 1  
**Participants reported in dataset audit:** 241

> Important: Although the dataset audit identified 241 participants, the current analysis was conducted using one pilot participant (sub-NDARINVYT858CBN). The results should not be interpreted as population-level or clinical findings.

---

## 2. Research Question

**Primary research question:**

How can Persistent Homology characterise the topological organisation of resting-state functional brain connectivity, and how does the network's structural organisation change across different filtration thresholds?

### Secondary research questions

1. What connected components and loops can be identified in resting-state functional connectivity networks?
2. How does network topology evolve across different filtration thresholds?
3. How do persistent homology features complement conventional graph-theoretical measures?
4. Can topological features provide a multiscale representation of functional brain connectivity?

### Preliminary answer

The pilot analysis identified 74 valid brain regions and constructed a functional connectivity network using Pearson correlation.

Persistent Homology identified:
- 74 H0 features representing connected components.
- 18 H1 features representing loops.

Across five network thresholds, network density and global efficiency increased as connectivity became progressively denser. Graph-based validation also confirmed that H0 Betti numbers matched the number of connected components at all five tested thresholds.

These findings demonstrate that persistent homology can be used to describe the multiscale topological organisation of the pilot participant's functional connectivity network.

---

## 3. Why Topological Data Analysis?

Traditional functional connectivity analysis generally examines pairwise relationships between brain regions, often using correlation matrices and graph-theoretical measures.

However, these approaches do not fully describe how network structures emerge, connect and disappear across different scales.

This project uses **Persistent Homology** to investigate these structural properties.

The main advantages of TDA are:

- **Multiscale analysis:** Examines network organisation across multiple distance thresholds rather than relying on one arbitrary threshold.
- **Connected components (H0):** Identifies how separate brain network components become connected.
- **Loops (H1):** Identifies circular or loop-like topological structures.
- **Persistence:** Measures how long topological features survive as the filtration threshold changes.
- **Robust structural description:** Provides a complementary representation of network organisation beyond individual connectivity strengths.

The objective is to investigate whether topological representations can provide additional information about functional brain network organisation.

---

## 4. Dataset Description

**Source:** OpenNeuro – Transdiagnostic Connectome Project

Dataset: https://openneuro.org/datasets/ds005237

| Property | Description |
|---|---|
| Dataset ID | ds005237 |
| Version | 1.1.3 |
| Reported participants | 241 |
| Participants analysed | 1 |
| Imaging modality | Functional MRI |
| Imaging type | Resting-state fMRI |
| Acquisition | restAP |
| Pilot participant | sub-NDARINVYT858CBN |
| Atlas | Schaefer 2018 |
| Requested atlas regions | 100 |
| Successfully extracted ROIs | 97 |
| Final valid ROIs | 74 |

### Imaging characteristics

| Parameter | Value |
|---|---:|
| Original image dimensions | 104 × 104 × 72 × 488 |
| Spatial resolution | 2 mm isotropic |
| Repetition time (TR) | 0.8 seconds |
| Number of volumes | 488 |
| Scan duration | 390.4 seconds |
| Temporal sampling | 0.8 seconds |

The initial dataset audit identified 241 participants. However, the subsequent local project-directory audit did not locate the participants.tsv file, phenotype folder or BOLD files. The pilot participant's previously processed data and saved analysis outputs were available.

---

## 5. Methodology

### 5.1 Dataset auditing and MRI inspection

- Audited the dataset and identified available resting-state fMRI files.
- Inspected NIfTI image dimensions and voxel resolution.
- Examined repetition time and scan duration.
- Checked image data for NaN and infinite values.

### 5.2 Preliminary fMRI preprocessing

Applied the following preprocessing operations:

- Linear detrending to remove linear temporal trends.
- Voxel-wise z-score standardisation.
- Temporal filtering between 0.01 and 0.1 Hz.
- Brain masking to identify relevant brain voxels.

The resulting standardised signal matrix contained 153,569 voxels across 488 timepoints.

**Limitation:** Motion correction, nuisance regression and susceptibility distortion correction were not performed. Therefore, preprocessing remains preliminary.

### 5.3 Regional time-series extraction

Used the Schaefer 2018 atlas to extract regional brain signals.

- Requested regions: 100
- Successfully extracted regions: 97
- Missing regions: 3
- Timepoints: 488

The resulting regional time-series matrix had dimensions of 488 × 97.

### 5.4 Functional connectivity construction

Calculated Pearson correlation coefficients between regional time series.

Removed 23 zero-variance regions, resulting in:

- 74 valid brain regions.
- 74 × 74 functional connectivity matrix.
- Finite correlation values.
- Correlations ranging from approximately -0.126 to 1.0.

### 5.5 Distance matrix construction

Converted Pearson correlation values into chord distances to represent dissimilarities between brain regions.

Validated the resulting distance matrix for:

- Finite values.
- Symmetry.
- Zero diagonal.
- Non-negative distances.

### 5.6 Persistent Homology

Applied Vietoris–Rips filtration using chord distance derived from Pearson correlation.

Calculated:

- H0: Connected components.
- H1: Loop-like topological structures.

Generated persistence diagrams and extracted persistence statistics, including:

- Feature count.
- Finite and infinite intervals.
- Mean lifetime.
- Median lifetime.
- Maximum lifetime.
- Total persistence.

### 5.7 Topological validation

Validated persistence results using graph-based connected-component analysis.

Compared H0 Betti numbers with graph connected components across five filtration thresholds.

### 5.8 Threshold sensitivity analysis

Investigated network organisation across five thresholds to examine how network structure changes with increasing connectivity.

### 5.9 Graph-theoretical analysis

Calculated:

- Network density.
- Mean degree.
- Maximum degree.
- Mean clustering coefficient.
- Global efficiency.

---

## 6. Results

### 6.1 Functional connectivity

The final functional connectivity matrix contained 74 brain regions.

| Metric | Result |
|---|---:|
| Matrix dimensions | 74 × 74 |
| Minimum correlation | -0.1263 |
| Maximum correlation | 1.0000 |
| Valid regions | 74 |
| Removed zero-variance regions | 23 |

### 6.2 Persistent Homology

| Metric | H0 | H1 |
|---|---:|---:|
| Total features | 74 | 18 |
| Finite intervals | 73 | 18 |
| Infinite intervals | 1 | 0 |
| Mean lifetime | 0.4690 | 0.0384 |
| Median lifetime | 0.4434 | 0.0333 |
| Maximum lifetime | 1.1023 | 0.0810 |
| Total persistence | 34.2377 | 0.6910 |

The analysis identified 74 H0 features and 18 H1 features.

One H0 feature had an infinite death time, corresponding to the connected component that remains when the entire network has become connected.

### 6.3 Network threshold analysis

Five filtration thresholds were examined.

| Density | Mean degree | Clustering | Global efficiency |
|---:|---:|---:|---:|
| 0.1003 | 7.32 | 0.0663 | 0.2242 |
| 0.2503 | 18.27 | 0.0333 | 0.5035 |
| 0.5002 | 36.51 | 0.0167 | 0.7009 |
| 0.7501 | 54.76 | 0.0004 | 0.8351 |
| 0.9000 | 65.70 | 0.0084 | 0.9499 |

The results indicate that network density, mean degree and global efficiency generally increased as more connections were incorporated.

The clustering coefficient varied across thresholds, showing that local network organisation also changed with network density.

### 6.4 Persistence validation

The distance matrix was validated:

- All values finite: True.
- Symmetric: True.
- Diagonal zero: True.

Persistence diagrams were validated with 74 H0 intervals and 18 H1 intervals.

Across five tested thresholds:

- H0 Betti numbers ranged from 1 to 17.
- H1 Betti numbers ranged from 0 to 2.
- H0 Betti numbers matched graph connected components at every tested threshold.

### 6.5 Overall findings

The pilot analysis demonstrates that:

1. Functional connectivity can be represented as a distance-based network.
2. Persistent Homology identifies connected components and loop-like structures.
3. Network topology changes across filtration thresholds.
4. Graph-theoretical measures provide complementary descriptions of network organisation.
5. H0 validation provides an independent consistency check for the connectivity filtration.

These findings are descriptive and exploratory. They do not establish clinical differences, diagnostic biomarkers or associations with depression or bipolar disorder.

---

## 7. Complete Research Pipeline

```text
TCP Dataset (ds005237)
          |
          v
1. Dataset Audit
          |
          v
2. MRI Inspection and Quality Checks
          |
          v
3. Preliminary fMRI Preprocessing
   - Linear detrending
   - Voxel-wise standardisation
   - Temporal filtering
          |
          v
4. Regional Time-Series Extraction
   - Schaefer 2018 Atlas
   - 97 extracted ROIs
          |
          v
5. Functional Connectivity
   - Pearson correlation
   - Remove zero-variance regions
   - Final 74 x 74 matrix
          |
          v
6. Distance Matrix Construction
   - Chord distance
          |
          v
7. Persistent Homology
   - Vietoris-Rips filtration
   - H0 and H1
   - Persistence diagrams
          |
          v
8. Topological Validation
   - Betti numbers
   - Graph connected components
          |
          v
9. Network Analysis
   - Density
   - Degree
   - Clustering
   - Global efficiency
          |
          v
    Exploratory Results
```

---

## 8. Repository Contents

The repository contains the Python analysis pipeline, intermediate outputs and final research results.

### Main outputs

| File | Description |
|---|---|
| `distance_matrix.npy` | Validated 74 × 74 distance matrix |
| `persistence_H0.npy` | H0 persistence intervals |
| `persistence_H1.npy` | H1 persistence intervals |
| `milestone8_threshold_sensitivity.csv` | Threshold sensitivity results |
| `milestone9_network_metrics.csv` | Graph-theoretical metrics |
| `milestone9_persistence_summary.csv` | Persistence statistics |

The repository also contains the dataset audit, MRI inspection, preprocessing, regional time-series extraction, connectivity construction, topological analysis and validation scripts.

### Suggested repository structure

```text
neuroscience_project/
│
├── README.md
│
├── scripts/
│   ├── 01_dataset_audit.py
│   ├── 02_mri_inspection.py
│   ├── 03_fmri_preprocessing.py
│   ├── 04_timeseries_extraction.py
│   ├── 05_functional_connectivity.py
│   ├── 06_persistent_homology.py
│   ├── 07_persistence_features.py
│   ├── 08_topological_validation.py
│   └── 09_network_analysis.py
│
├── data/
│   ├── raw/
│   └── processed/
│
├── results/
│   ├── distance_matrix.npy
│   ├── persistence_H0.npy
│   ├── persistence_H1.npy
│   ├── milestone8_threshold_sensitivity.csv
│   ├── milestone9_network_metrics.csv
│   └── milestone9_persistence_summary.csv
│
├── figures/
│
└── requirements.txt
```

*The structure above is a suggested organisation; adjust filenames to match the actual repository.*

---

## 9. Limitations and Future Work

The current analysis has several limitations:

1. Only one participant has been analysed.
2. Motion correction and nuisance regression have not been performed.
3. Susceptibility distortion correction has not been performed.
4. The BIDS JSON sidecar was unavailable during the initial inspection.
5. Three atlas regions were not extracted.
6. Twenty-three additional regions were removed because they had zero variance.
7. No clinical group comparison has been conducted.
8. The local dataset audit did not locate participant metadata or phenotype files.

### Future directions

- Complete and improve fMRI preprocessing.
- Investigate the missing atlas regions and zero-variance signals.
- Verify dataset metadata and acquisition parameters.
- Extend the analysis to multiple participants.
- Compare topological features across clinical groups, where appropriate metadata are available.
- Investigate associations between topological measures and clinical assessments.
- Evaluate the reproducibility and stability of topological features.

---

## 10. Conclusion

This project establishes an exploratory computational pipeline for investigating resting-state functional brain connectivity through Persistent Homology and graph theory.

Using one pilot participant from the TCP dataset, the analysis successfully constructed a functional connectivity matrix, calculated Vietoris–Rips persistent homology, identified H0 and H1 features, validated connected-component behaviour and examined network properties across multiple thresholds.

The findings demonstrate the feasibility of applying Topological Data Analysis to resting-state functional connectivity. Further preprocessing, multi-participant analysis and clinical validation are necessary before drawing broader neuroscientific conclusions.

---

## Technologies Used

- Python
- NumPy
- Pandas
- NiBabel
- Nilearn
- Scikit-learn
- SciPy
- NetworkX
- Ripser / Persistent Homology tools
- Matplotlib

**Research area:** Computational Neuroscience · Functional Brain Connectivity · Topological Data Analysis · Persistent Homology · Network Neuroscience
