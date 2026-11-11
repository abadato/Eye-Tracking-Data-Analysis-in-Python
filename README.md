# Eye-Tracking Data Analysis in Python

### A Python-based data processing and visualization pipeline for high-frequency eye-tracking data

This project implements a multi-stage Python workflow for processing, transforming, aggregating, and visualizing experimental eye-tracking data collected using the **Visual World Paradigm (VWP)**.

The pipeline processes approximately **200 MB of raw experimental data across 16 Excel files**, integrating gaze coordinates, timestamps, participant and trial information, and experimental conditions to investigate real-time language comprehension.

The project demonstrates practical skills in **data preprocessing, quality control, temporal data alignment, feature engineering, statistical analysis, and reproducible analytical workflows**.

---

## 1. Research Objective

The Visual World Paradigm is an experimental method used in psycholinguistics to investigate how listeners interpret spoken language by tracking their eye movements toward objects or referents in a visual scene.

**Research question:**

How do word order (SVO vs. OVS) and pronoun type influence real-time referential resolution, as reflected in gaze allocation toward subject and object antecedents?

**Primary analytical measure:**

Log-ratio of gaze proportions toward subject and object antecedents, calculated across 20-ms time bins.

Positive log-ratio values indicate relatively more looks toward the subject antecedent; negative values indicate relatively more looks toward the object antecedent.

---

## 2. Dataset

The original dataset consists of:

- **16 Excel files**, totaling approximately **200 MB**
- High-frequency eye-tracking observations
- Gaze coordinates (`GazePointX`, `GazePointY`)
- Timestamps and trial information
- Participant identifiers and experimental conditions
- Subject and object areas of interest (AOIs)

### Data Availability

The original experimental datasets are not included in this public repository. Raw, intermediate, and processed research data are excluded to protect participant information and comply with applicable data-sharing restrictions.

The notebooks and generated visualizations are publicly available for code review.

A representative sample dataset may be provided upon request, subject to applicable data-sharing permissions.

**Reproducibility limitation:** Running the complete pipeline requires access to data with the expected input structure.

---

## 3. Data Processing and Analysis Pipeline

The analysis is organized into six sequential Jupyter notebooks.

| Stage | Description |
|---|---|
| **01 — Data Import and Cleaning** | Batch import of Excel files, initial data inspection, missing-value handling, and quality control |
| **02–04 — Data Transformation** | Timestamp standardization, trial alignment, temporal binning, and preparation of analysis-ready data |
| **05 — Statistical Transformation** | Calculation of subject/object gaze proportions and log-ratio measures, including handling of zero-gaze cases |
| **06 — Visualization** | Visualization of gaze time courses across word-order and pronoun conditions, with confidence intervals |

### Key Processing Steps

**Data ingestion and validation**

Raw experimental files are imported and combined into a structured analytical dataset. The workflow includes inspecting variable types, handling missing gaze coordinates, and preparing the observations for subsequent transformations.

**Temporal alignment and aggregation**

Eye-tracking observations are aligned to the experimental timeline and aggregated into **20-ms intervals**, enabling comparisons of gaze behavior across participants and experimental conditions.

**Statistical transformation**

Gaze allocation toward subject and object antecedents is summarized using log-ratio transformations to characterize relative viewing preferences over time.

**Visualization**

Time-course plots are generated using `matplotlib` and `seaborn`, allowing visual comparison of gaze patterns across word-order conditions and pronoun types.

---

## 4. Visualization and Results

The analysis produces time-course visualizations of subject-versus-object gaze preferences across experimental conditions.

**Figure 1.** Time course of the log-ratio of gaze proportions toward subject and object antecedents, grouped by pronoun type and word order (SVO and OVS).

Positive values indicate a relative preference for the subject antecedent, while negative values indicate a relative preference for the object antecedent. Lines represent aggregated gaze patterns, with shaded regions indicating 95% confidence intervals.

The visualization includes a pronoun-onset reference marker at **1,000 ms**.

The plots support exploratory comparisons of gaze allocation before and after pronoun onset and across experimental conditions.

---

## 5. Technologies and Tools

| Category | Technologies |
|---|---|
| Programming | Python |
| Data manipulation | pandas, NumPy |
| Data visualization | Matplotlib, Seaborn |
| Excel file processing | openpyxl |
| Development environment | Jupyter notebooks, VS Code / JupyterLab |
| Version control | Git, GitHub |

---

## 6. Installation and Usage

### Clone the repository

```bash
git clone https://github.com/abadato/Eye-Tracking-Data-Analysis-in-Python.git
cd Eye-Tracking-Data-Analysis-in-Python
```

### Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

For Windows, use the appropriate virtual environment activation command.

### Install dependencies

```bash
pip install -r requirements.txt
```

The project dependencies are listed in `requirements.txt`.

To execute the notebooks interactively, use a Jupyter environment such as JupyterLab or VS Code with the Jupyter extension.

### Run the analysis

Open the `notebooks/` directory and execute the numbered notebooks sequentially, beginning with Notebook 01.

**Note:** The original datasets are not included. Before executing the pipeline, the required input files must be placed in the expected local directories, and their paths must match the notebook configuration.

---

## 7. Project Scope and Limitations

This repository presents a research-oriented data analysis workflow developed for experimental eye-tracking data.

The current implementation demonstrates:

- Processing of multiple experimental data files
- Cleaning and transformation of high-frequency observational data
- Temporal alignment and aggregation
- Calculation of derived analytical measures
- Visualization of time-dependent experimental outcomes

The pipeline was developed for a specific experimental dataset. Applying it to new datasets may require adjustments to input schemas, metadata, and file paths.

Because the original research data is not publicly distributed, the complete analysis cannot currently be reproduced using only the repository contents.

---

## 8. Author

**Dato Abashidze, PhD**

Researcher in psycholinguistics and experimental data analysis, with experience in quantitative research, statistical modeling, and Python-based data processing.

GitHub: https://github.com/abadato
