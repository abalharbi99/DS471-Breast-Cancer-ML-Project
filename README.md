# DS-471 Machine Learning Project: Breast Cancer Classification

This repository contains the complete code, report, and documentation for the Machine Learning Project utilizing the **UCI Breast Cancer Wisconsin (Diagnostic)** dataset.

---

## 📋 Project Overview & Objectives
The goal of this project is to apply supervised machine learning techniques to classify breast tissue masses as either **Malignant** or **Benign** based on cellular characteristics computed from fine needle aspirate (FNA) images.

---

### 👥 Team Members
- **Abdulrhman Salem Almohammadi** (Team Leader) — ID: `S210044670`
- **Mohammed Khalid Almadhi** — ID: `S230019632`
- **Raid Abdulrahman Alotaibi** — ID: `S230003591`

## 📂 Repository Structure
- `DS471_Breast_Cancer_Project.ipynb`: Complete Google Colab / Jupyter Notebook covering data preparation, EDA, feature scaling, model training, and evaluation.
- `DS471_Project_Report.pdf`: Final academic project report formatted according to course requirements.
- `README.md`: Project documentation and workflow guide.

---

## 🚀 Project Workflow & Stages

1. **Stage 1: Data Cleaning, Preparation, and Exploration**
   - Analyzed 569 instances and 30 numerical input features with zero missing values.
   - Applied `StandardScaler` to normalize feature distributions for optimal Neural Network and SVM performance[cite: 1].
   - Performed Exploratory Data Analysis (EDA) using correlation heatmaps.

2. **Stage 2: Data Splitting**
   - Partitioned the dataset using stratified sampling to maintain class balance:
     - **Training Set (70%)**[cite: 1]
     - **Validation Set (15%)**[cite: 1]
     - **Test Set (15%)**[cite: 1]

3. **Stage 3 & 4: Model Development, Training & Optimization**
   - Developed three classification models:
     - **Mandatory Neural Network (MLP)** trained with Early Stopping via the Adam optimizer.
     - **Support Vector Machine (SVM)** utilizing an RBF kernel.
     - **Random Forest Classifier** with controlled tree depth.
   - Generated training and validation loss/accuracy curves to monitor and prevent overfitting[cite: 1].

4. **Stage 5: Final Evaluation & Comparison**
   - Evaluated all models on the unseen test dataset using Accuracy, Precision, Recall, and F1-Score[cite: 1].

---

## 📊 Final Results Summary

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Neural Network** | 97.67% | 0.98 | 0.98 | 0.98 |
| **Support Vector Machine (SVM)** | 98.84% | 0.99 | 0.99 | 0.99 |
| **Random Forest** | 96.51% | 0.96 | 0.98 | 0.97 |

---

## 🛠️ Setup & Execution Instructions

1. **Clone the repository:**
  
   git clone https://github.com/abalharbi99/DS471-Breast-Cancer-ML-Project.git
