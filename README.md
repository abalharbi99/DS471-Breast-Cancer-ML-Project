# Breast Cancer Wisconsin (Diagnostic) Classification

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-orange.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0%2B-FF6F00.svg)
![Course](https://img.shields.io/badge/Course-DS471%20Machine%20Learning-green.svg)

Predictive Modeling via Deep Neural Networks (MLP), Support Vector Machines (SVM), and Random Forest Classifiers on the UCI Breast Cancer Wisconsin (Diagnostic) Dataset.

---

## 📌 Project Overview

Breast cancer diagnosis relies on accurate classification of cellular characteristics to determine mass malignancy. This project implements, evaluates, and compares three supervised machine learning models to automate the classification of digitized fine needle aspirate (FNA) cell nuclei characteristics into **Benign** or **Malignant** states.

### Course Information
* **Course:** DS-471 Machine Learning
* **CRN:** 10700
* **Institution:** Prince Musaid bin Abdulrahman University
* **College:** College of Computing and Informatics
* **Department:** Data Science

---

## 👥 Team Members

* **Abdulrhman Salem Almohammadi** (Team Leader) — ID: `S210044670`
* **Mohammed Khalid Almadhi** — ID: `S230019632`
* **Raid Abdulrahman Alotaibi** — ID: `S230003591`

---

## 📊 Dataset Summary

* **Dataset:** UCI Breast Cancer Wisconsin (Diagnostic)
* **Total Instances:** 569 samples (357 Benign, 212 Malignant)
* **Feature Count:** 30 continuous numeric features
* **Data Hygiene:** 0 missing values, 0 duplicate records
* **Scaling:** Z-score Standardization (`StandardScaler`) applied to all features

---

## 📐 Data Splitting Strategy

To ensure experimental integrity and prevent data leakage, stratified sampling was applied to maintain the 62.7:37.3 target class distribution:

| Subset | Percentage | Sample Count | Purpose |
| :--- | :--- | :--- | :--- |
| **Training Set** | 70% | 398 | Model weight optimization and boundary learning |
| **Validation Set** | 15% | 85 | Hyperparameter tuning and early stopping monitoring |
| **Test Set** | 15% | 86 | Unseen final evaluation and generalization measurement |

---

## 📈 Model Performance & Results

Evaluated on the unseen test set (86 samples):

| Model Architecture | Accuracy | Precision (Malignant) | Recall (Malignant) | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Support Vector Machine (RBF)** | **98.84%** | **0.99** | **0.99** | **0.99** |
| **Multi-Layer Perceptron (MLP Neural Net)** | **97.67%** | 0.98 | 0.98 | 0.98 |
| **Random Forest Classifier** | **96.51%** | 0.96 | 0.98 | 0.97 |

> **Key Finding:** Support Vector Machine (RBF kernel) achieved the highest overall performance (98.84% accuracy, 0.99 Recall). High recall is essential in clinical oncology to minimize False Negative diagnoses.

---

## 🛠️ Project Structure

```text
├── DS471_Breast_Cancer_Project.ipynb  # Primary Jupyter Notebook with full implementation
├── DS471_Project_Report.pdf           # Formal Academic Project Report
├── README.md                          # Project Documentation
