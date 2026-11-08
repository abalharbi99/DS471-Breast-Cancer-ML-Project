# DS-471 Machine Learning Project: Breast Cancer Classification

This repository contains the complete code and report for the Machine Learning Project utilizing the **UCI Breast Cancer Wisconsin (Diagnostic)** dataset.

## 📁 Project Structure
- `DS471_Breast_Cancer_Project.ipynb`: Full implementation notebook (Data Prep, EDA, Splitting, Model Training, and Evaluation).
- `DS471_Project_Report.pdf`: Final academic project report.

## 🚀 Project Stages
1. **Stage 1 (Data Prep & EDA)**: Analyzed 569 instances and 30 numerical features. Verified zero missing values and applied `StandardScaler` normalization.
2. **Stage 2 (Data Splitting)**: Stratified partition into 70% Training, 15% Validation, and 15% Test sets.
3. **Stage 3 & 4 (Models & Training)**: Developed a mandatory Neural Network (with Early Stopping), a Support Vector Machine (SVM), and a Random Forest Classifier.
4. **Stage 5 (Evaluation)**: Evaluated models using Accuracy, Precision, Recall, and F1-Score.

## 📊 Final Results Summary
| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Neural Network** | 97.67% | 0.98 | 0.98 | 0.98 |
| **Support Vector Machine (SVM)** | 98.84% | 0.99 | 0.99 | 0.99 |
| **Random Forest** | 96.51% | 0.96 | 0.98 | 0.97 |

## 🛠️ Requirements
- Python 3.8+
- Key Libraries: `scikit-learn`, `tensorflow`, `pandas`, `numpy`, `matplotlib`, `seaborn`
