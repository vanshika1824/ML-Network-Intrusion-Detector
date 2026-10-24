# ML Network Intrusion Detector

**IBM SkillsBuild Cyber Security BootCamp 2026 — Project**

## Overview
This educational project trains a Random Forest machine-learning model to classify labeled network-flow records as **Normal** (`BENIGN`) or **Attack** (any non-`BENIGN` label) using a public intrusion-detection dataset.

It covers data cleaning, preprocessing, model training, evaluation, and saving the trained model and metrics.

> **Important:** This is a learning prototype. It does not monitor live traffic, block attacks, or guarantee detection of malicious activity. Do not use it as a production security control.

## Dataset
- Recommended dataset: [CIC-IDS2017 — Canadian Institute for Cybersecurity](https://www.unb.ca/cic/datasets/ids-2017.html)
- Download a labeled CSV from the official dataset page.
- Place it in a `data/` folder next to the notebook, or change `DATA_PATH` in the notebook.
- Follow the dataset provider's terms and conditions.

## Setup
1. Install Python 3.10 or newer.
2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```
3. Install packages: `pip install -r requirements.txt`
4. Download a labeled CIC-IDS2017 CSV into `data/`.
5. Run `jupyter notebook`, open `Vanshika_MLNetworkIntrusionDetector.ipynb`, update `DATA_PATH`, then run cells from top to bottom.

## Outputs
The notebook creates:
- `outputs/network_intrusion_random_forest.joblib` — fitted model pipeline
- `outputs/evaluation_metrics.json` — accuracy, macro precision, macro recall, and macro F1-score
- Class distribution and confusion-matrix visualizations

Metrics must come from an actual run; no performance values are fabricated.

## Methodology
1. Load labeled CSV data.
2. Clean column names, duplicates, missing labels, and infinite values.
3. Map `BENIGN` to `Normal`; map other labels to `Attack`.
4. Split into stratified training and test sets.
5. Impute missing values and encode categorical features in a pipeline.
6. Train a class-weighted Random Forest.
7. Evaluate accuracy, precision, recall, F1-score, classification report, and confusion matrix.

## Limitations
Public dataset performance may not represent live network traffic. Random splitting can be optimistic when similar flows appear in both sets. New attack types and data distribution changes can reduce performance. This is not a live packet sensor or automated response system.

## Author
- **Student:** Vanshika Maru
- **Email:** vanshikamaru0205@gmail.com
- **Program:** IBM SkillsBuild Cyber Security BootCamp 2026
- **Project:** ML Network Intrusion Detector
