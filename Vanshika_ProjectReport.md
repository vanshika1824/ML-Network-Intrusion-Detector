# ML Network Intrusion Detector — Project Report

**IBM SkillsBuild Cyber Security BootCamp 2026**  
**Submitted by:** Vanshika Maru  
**Email:** vanshikamaru0205@gmail.com

## 1. Abstract
This project demonstrates a machine-learning approach to classifying network-flow records as normal or potentially malicious. A Random Forest classifier is trained on a labeled public intrusion-detection dataset, with CIC-IDS2017 recommended. The workflow covers data loading, cleaning, feature preprocessing, model training, and evaluation. This is an educational prototype, not a replacement for a production network intrusion detection system.

## 2. Problem Statement
Network environments generate large volumes of traffic records. Reviewing every record manually is difficult. A supervised model can learn patterns from labeled examples and provide a baseline classification of network flows. The goal is to separate records labeled `BENIGN` from records labeled as attacks.

## 3. Objectives
- Use a public labeled network intrusion dataset.
- Clean and prepare network-flow features.
- Train a Random Forest classifier.
- Evaluate with several metrics rather than accuracy alone.
- Save the trained pipeline and evaluation metrics.

## 4. Dataset
The recommended source is [CIC-IDS2017](https://www.unb.ca/cic/datasets/ids-2017.html), published by the Canadian Institute for Cybersecurity. Use a manageable labeled CSV or subset for a laptop-friendly run. Map `BENIGN` to **Normal** and all other labels to **Attack**. Record the file used and row count after running the notebook.

## 5. Tools and Technologies
Python; Pandas and NumPy; scikit-learn; Matplotlib; Joblib; and Jupyter Notebook.

## 6. Methodology
1. Read the labeled CSV into a Pandas DataFrame.
2. Trim column names, remove duplicate records, replace infinite values, and drop rows without labels.
3. Convert labels into Normal and Attack classes.
4. Remove selected identifier-like and constant columns.
5. Split the data into stratified training and test subsets.
6. Impute missing numeric values and encode categorical values within a pipeline.
7. Train a class-weighted Random Forest classifier.
8. Evaluate predictions using accuracy, macro precision, macro recall, macro F1-score, a classification report, and a confusion matrix.
9. Save the fitted model pipeline and evaluation metrics.

## 7. Evaluation Results
**Run the notebook before submission and fill this table from the actual output. Do not invent scores.**

| Metric | Result from actual run |
|---|---|
| Accuracy | Fill in from notebook output |
| Macro precision | Fill in from notebook output |
| Macro recall | Fill in from notebook output |
| Macro F1-score | Fill in from notebook output |
| Training / test rows | Fill in from notebook output |

## 8. Expected Deliverables
- `Vanshika_MLNetworkIntrusionDetector.ipynb` — notebook and analysis.
- `requirements.txt` — Python dependencies.
- `Vanshika_ProjectReport.docx` — formatted project report.
- `README.md` — setup, dataset, and run instructions.
- Generated model and metrics files after a successful run.

## 9. Limitations and Ethical Considerations
This is a learning prototype, not a production security product. Random train/test splitting can overstate performance when similar flows appear in both sets; capture-based or time-based validation is stronger. The model may fail on new attack types or changed traffic patterns. False negatives can be serious, so class-specific recall and errors should be reviewed. Only use datasets and systems that you are authorized to access. This project does not scan or interfere with live systems.

## 10. Future Scope
Compare Random Forest with other classifiers, use capture-based holdout validation, test on another public dataset, tune hyperparameters, and build a small interface for CSV upload and prediction review.

## 11. Conclusion
The project provides a reproducible baseline for network-flow classification using supervised learning. The final conclusion about performance must be written only after running the notebook and reviewing the actual test-set metrics. Further validation is required before operational use.

## 12. References
- Canadian Institute for Cybersecurity, [CIC-IDS2017 Dataset](https://www.unb.ca/cic/datasets/ids-2017.html)
- [scikit-learn documentation](https://scikit-learn.org/stable/)
- [Pandas documentation](https://pandas.pydata.org/docs/)
- [Matplotlib documentation](https://matplotlib.org/stable/)

**Submission note:** Run the notebook, replace all result placeholders with actual metrics, and include screenshots or output files if required by the bootcamp.
