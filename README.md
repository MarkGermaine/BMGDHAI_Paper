# BMGDHAI_Paper

# Early Prediction of Gestational Diabetes Mellitus using Machine Learning

[cite_start]This repository contains the code and resources for the research paper titled: **"Evaluation of Machine Learning Models for Early Prediction of Gestational Diabetes Using Retrospective Electronic Health Records from Current and Previous Pregnancies"**. 

This work focuses on the development and evaluation of machine learning models to predict Gestational Diabetes Mellitus (GDM) early in pregnancy using electronic health record (EHR) data. We explore the predictive power of data from the first antenatal visit and assess the improvement in model performance when incorporating data from previous pregnancies.

## Abstract

[cite_start]**Objective:** To assess the performance of machine learning (ML) models in predicting gestational diabetes mellitus (GDM) using electronic health record (EHR) data from the first antenatal visit, and determine whether incorporating previous pregnancies data improves performance. 

[cite_start]**Methods and Analysis:** In this retrospective cohort study, several ML models were developed to predict GDM using EHR data from nulliparous and multiparous populations (n=27,561, GDM 11.6%).  [cite_start]Data from past pregnancies (n=4,005) were used to enhance future GDM predictions.  [cite_start]We evaluated four ML algorithms: logistic regression (LR), random forest (RF), XGBoost (XGB), and explainable boosting machine (EBM).  [cite_start]Model performance was assessed on an internal validation set by looking at model discrimination (AUROC), calibration (plots, slope, and intercept), and decision-curve analysis for clinical usefulness. 

[cite_start]**Results:** First-trimester models using all features achieved an AUROC of 0.832 (slope 0.967; intercept -0.088) with LR, which was similar to more complex models like XGB (AUROC 0.828; slope 0.976; intercept -0.072).  [cite_start]The model incorporating past pregnancy data along with first-trimester data showed the highest predictive performance, with XGB achieving an AUROC of 0.904 (slope 0.618; intercept -0.136).  [cite_start]Models that used a smaller set of top clinical features also performed well for both first-trimester (AUROC 0.809; slope 0.978; intercept -0.006; 9 predictors) and past pregnancy (AUROC 0.897; slope 1.137; intercept 0.161; 8 predictors) scenarios. 

[cite_start]**Conclusion:** The inclusion of data from previous pregnancies improved the performance of ML models for GDM prediction.  [cite_start]Furthermore, using a focused set of clinically relevant features produced comparable performance, suggesting the potential for integration into clinical decision support systems.  [cite_start]These findings indicate the promise of early GDM risk identification in both first-time and subsequent pregnancies.  [cite_start]However, further research, including external validation and clinical trials, is necessary to establish the practical utility of these models and their impact on maternal and neonatal outcomes. 

## Repository Contents

This repository provides the following resources:

1.  **Generic Code:** A general outline of the code structure and procedures applied to the various study populations. This can serve as a template for researchers looking to apply similar methodologies.
2.  **FTP-9 Model:** The trained machine learning model for the First-Trimester Population using the top 9 most predictive features.
3.  **SPP-8 Model:** The trained machine learning model for the Sequential Pregnancy Population using the top 8 most predictive features from both past and current pregnancies.
4.  **Preprocessors:** The corresponding data preprocessors for both the FTP-9 and SPP-8 models to ensure data is correctly formatted before being fed into the models.

## Model Details

### First-Trimester Population (FTP-9) Model

[cite_start]This model is designed to predict GDM risk using data available at the first antenatal visit (~12th week of gestation) for all pregnancies. 

* **Model:** `FTP-9_model.pkl`
* **Preprocessor:** `FTP-9_preprocessor.pkl`

#### FTP-9 Features

The model utilizes the following 9 features:
* [cite_start]**Ethnicity:** The ethnic origin of the patient. 
* [cite_start]**Family History of Diabetes:** A binary indicator of whether the patient has a family history of diabetes. 
* [cite_start]**Previous History of GDM:** A binary indicator of whether the patient had GDM in a previous pregnancy. 
* [cite_start]**Endocrine Problems:** A binary indicator for the presence of endocrine conditions such as Polycystic Ovary Syndrome (PCOS) or thyroid issues. 
* [cite_start]**Parity:** An integer representing the number of times the patient has given birth. 
* [cite_start]**Age:** The maternal age in years. 
* [cite_start]**BMI:** Maternal Body Mass Index. 
* [cite_start]**Systolic Blood Pressure:** The systolic blood pressure measurement. 
* [cite_start]**Diastolic Blood Pressure:** The diastolic blood pressure measurement. 

### Sequential Pregnancy Population (SPP-8) Model

[cite_start]This model is developed for multiparous women and incorporates data from previous pregnancies to predict GDM in the current pregnancy. 

* **Model:** `SPP-8_model.pkl`
* **Preprocessor:** `SPP-8_preprocessor.pkl`

#### SPP-8 Features

The model utilizes the following 8 features:
* [cite_start]**Ethnicity:** The ethnic origin of the patient. 
* [cite_start]**Age:** The maternal age in years. 
* [cite_start]**Interpregnancy weight change:** The change in maternal booking weight between successive pregnancies (in float). 
* [cite_start]**History of GDM:** A binary indicator of a GDM diagnosis in any previous pregnancy. 
* [cite_start]**BMI:** Maternal Body Mass Index at the current booking visit. 
* [cite_start]**Time between pregnancies:** The inter-pregnancy interval in days. 
* [cite_start]**Birthweight Percentile:** The birthweight percentile from a previous pregnancy, calculated based on the baby's weight and gestational age at delivery. 
* [cite_start]**Family history of diabetes:** A binary indicator of a family history of diabetes. 

## Usage

These models are provided for **research purposes only**. [cite_start]They require external validation before any consideration for clinical implementation.  Researchers can use the provided models and preprocessors to test their own datasets or to build upon this work.

## Citation

If you use the models or code from this repository in your research, please cite our paper:

Germaine, M., O'Higgins, A. C., Egan, B., & Healy, G. (2024). Evaluation of Machine Learning Models for Early Prediction of Gestational Diabetes Using Retrospective Electronic Health Records from Current and Previous Pregnancies. *BMJ Digital Health and AI*.


## Data and Code Availability

[cite_start]Due to patient confidentiality and data use agreements, the individual-level data used in this study cannot be shared publicly.  [cite_start]The code and saved models are available in this repository for other researchers to use for research purposes. 

## Funding

[cite_start]This research was supported in part by a grant from Research Ireland Ireland under Grant Number 18/CRT/6183. 

## Contact

For any questions or collaborations, please contact Mark Germaine at mark.germaine2@mail.dcu.ie.
