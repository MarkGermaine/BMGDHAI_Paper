# BMJ DHAI_Paper

# Early Prediction of Gestational Diabetes Mellitus using Machine Learning

This repository contains the code and resources for the research paper titled: **"Evaluation of Machine Learning Models for Early Prediction of Gestational Diabetes Using Retrospective Electronic Health Records from Current and Previous Pregnancies"**. 

This work focuses on the development and evaluation of machine learning models to predict Gestational Diabetes Mellitus (GDM) early in pregnancy using electronic health record (EHR) data. We explore the predictive power of data from the first antenatal visit and assess the improvement in model performance when incorporating data from previous pregnancies.

## Abstract (abridged)

**Objective** Assess whether a compact set of routinely collected variables can predict gestational diabetes mellitus (GDM) at the first antenatal visit, and quantify the added value of previous-pregnancy information.

**Methods** In 27 561 pregnancies (GDM 11.6 %) we trained logistic-regression (LR), random-forest (RF), XGBoost (XGB) and explainable-boosting (EBM) models in four cohorts:  
*First-trimester* (9 variables), *Nulliparous* (7 variables), *Multiparous* (8 variables, first-trimester + previous pregnancy) and *Past-pregnancy* (6 variables, pre-conception).  
Performance was estimated with 5-fold nested cross-validation; discrimination (AUROC ± 95 % CI), calibration and decision-curve net benefit were reported.

**Results** First-trimester models showed AUROC ~0.82 with good calibration.  Multiparous models achieved AUROC 0.88–0.89 after adding previous-pregnancy features.  Past-pregnancy models alone still reached AUROC ~0.86.  All parsimonious models out-performed a dummy baseline and provided positive net benefit across clinically relevant thresholds.

**Conclusion** A handful of non-invasive predictors can give robust early-pregnancy GDM risk estimates; previous-pregnancy history further improves accuracy in multiparous women.  External validation and prospective trials remain necessary before clinical deployment.

## Repository layout

```
BMJDHAI_Paper/
├─ models/                       # Git-LFS tracked bundles
│  ├─ First_Trimester.joblib        # First-Trimester
│  ├─ Nulliparous.joblib   # Nulliparous
│  ├─ Past_Pregnancy.joblib           # Past-Pregnancy
│  └─ Multiparous_Models.joblib          # Multiparous
├─ preprocessors/
│  ├─ First-Trimester_preprocessor.pkl
│  ├─ Nulliparous_preprocessor.pkl
│  ├─ Multiparous_preprocessor.pkl
│  └─ PastPregnancy_preprocessor.pkl
├─ src/
│  └─ utils.py                  # simple loaders
├─ notebooks/
│  └─ 01_quick_demo.ipynb       # short load-and-predict demo
├─ requirements.txt
└─ .gitattributes               # tells Git to use LFS for *.joblib
```

Each bundle stores the four fitted estimators (RF, LR, XGB, EBM) plus ROC/PR arrays and calibration data.

## Model feature sets

| Cohort / bundle | # Predictors | Key variables |
|-----------------|-------------|---------------|
| **First-trimester** | 9 | Ethnicity, family-history-diabetes, history-of-GDM, endocrine problems, parity, age, BMI, systolic BP, diastolic BP |
| **Nulliparous** | 7 | Same as FTP-9 except parity & history-of-GDM |
| **Multiparous** | 8 | Ethnicity, age, inter-pregnancy weight-change, history-of-GDM, BMI, inter-pregnancy interval, previous birth-weight percentile, family-history-diabetes |
| **Past-pregnancy** | 6 | Ethnicity, age, history-of-GDM, BMI, previous birth-weight percentile, family-history-diabetes |

---


## Usage

These models are provided for **research purposes only**. They require external validation before any consideration for clinical implementation.  Researchers can use the provided models and preprocessors to test their own datasets or to build upon this work.

## Citation

If you use the models or code from this repository in your research, please cite our paper:

Germaine, M., O'Higgins, A. C., Egan, B., & Healy, G. (2024). Evaluation of Machine Learning Models for Early Prediction of Gestational Diabetes Using Retrospective Electronic Health Records from Current and Previous Pregnancies. *BMJ Digital Health and AI*.


## Data and Code Availability

Due to patient confidentiality and data use agreements, the individual-level data used in this study cannot be shared publicly. The code and saved models are available in this repository for other researchers to use for research purposes. 

## Funding

This research was supported in part by a grant from Research Ireland Ireland under Grant Number 18/CRT/6183. 

## Contact

For any questions or collaborations, please contact Mark Germaine at mark.germaine2@mail.dcu.ie.
