Eye-Tracking Data Analysis Pipeline (Visual World Paradigm)

A reproducible, professional Python pipeline for processing, transforming, and visualizing high-frequency eye-tracking data using the Visual World Paradigm (VWP). This project investigates real-time language comprehension, focusing on how listeners resolve pronoun referents across different word-order conditions.

📌 Project Overview & Research Question

In psycholinguistics, the Visual World Paradigm allows researchers to track real-time spoken language comprehension by monitoring eye movements as participants view a visual scene.

Research Question: How do word-order constraints (SVO vs. OVS) and pronoun types modulate real-time referential resolution (Subject vs. Object gaze allocation) following pronoun onset?
Core Metric: Log-ratio of Subject-to-Object gaze proportions, calculated over 20 ms time bins to capture granular temporal dynamics.
📊 Dataset

Raw Data: 16 raw Excel files (~200 MB total) capturing continuous gaze coordinates (GazePointX, GazePointY), timestamps, trial details, and experimental conditions.
Note on Accessibility: Raw, interim, and processed data directories are excluded from this public repository via .gitignore to adhere to data privacy standards. The pipeline scripts are structured to process local datasets seamlessly.
⚙️ Analysis Workflow & Pipeline Structure

The analysis is organized into a modular, multi-step Jupyter Notebook workflow:

Data Ingestion & Cleaning (Notebook 01): Batch-loading raw Excel files, handling missing coordinates, and filtering fixations.
Preprocessing & Binning (Notebookes 02–04): Standardizing timestamps, applying consistent 20 ms flooring bins, and aligning trials to the experimental timeline.
Log-Ratio Transformation (Notebook 05): Computing gaze proportions for Subject and Object antecedents, handling zero-gaze edge cases, and calculating log-ratios.
Statistical Visualization & Plotting (Notebook 06): Generating publication-grade multi-facet line plots with 95% confidence intervals and pronoun-onset annotations.
📈 Key Findings & Visualization

Figure 1. Time course of the log ratio of gaze proportions to the subject and object antecedents following target pronoun onset, by pronoun type and word order condition (SVO and OVS). Positive values indicate a higher subject-to-object gaze proportion, whereas negative values indicate a higher object-to-subject gaze proportion. Solid lines represent participant means, and shaded bands indicate 95% confidence intervals.

Pronoun Onset Marker: Highlighted at the 1000 ms mark to distinguish baseline viewing behavior from post-onset disambiguation.
Word-Order Modulation: Reveals clear differences in real-time looks between SVO and OVS structures, visualized via Seaborn’s relplot facet grid.
🧰 Tech Stack & Tools

Language: Python 3.x
Data Manipulation: pandas, numpy
Data Visualization: seaborn, matplotlib
Environment: JupyterLab, Anaconda
🚀 How to Run the Project

To set up the environment and run the notebooks locally, follow these steps:

1. Clone the repository

git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
