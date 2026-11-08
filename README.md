DS-471 MACHINE LEARNING PROJECT REPORT
Course: DS-471 Machine Learning | CRN: 10700 | Deadline: 30/11/2026 @ 23:59

Team Leader: Abdulrhman Salem Almohammadi | ID: S210044670
Team Members: Mohammed Khalid Almadhi (ID: S230019632), Raid Abdulrahman Alotaibi (ID: S230003591)

BREAST CANCER CLASSIFICATION
Predictive Modeling via Deep Neural Networks, Support Vector Machines, and Random Forest

1. INTRODUCTION & PROBLEM DEFINITION
Breast cancer remains one of the leading causes of cancer-related mortality globally. Early and precise diagnostic classification is vital to establishing effective clinical treatment pathways and improving patient prognosis. Traditionally, diagnostic decisions rely on biopsy evaluations that are labor-intensive and subject to intra-observer variability. The primary objective of this project is to implement, evaluate, and compare supervised machine learning algorithms to automate the diagnostic classification of breast masses into Malignant or Benign states using digitized fine needle aspirate (FNA) cell nuclei characteristics from the UCI Breast Cancer Wisconsin (Diagnostic) dataset[cite: 1].

2. STAGE 1: DATA PREPARATION, CLEANING, AND EXPLORATION
Dataset Characteristics: The dataset comprises 569 instances with 30 numeric features computed from digitized FNA images[cite: 1]. The target variable is binary: 357 cases are classified as Benign (62.7%) and 212 cases as Malignant (37.3%)[cite: 1].
• Data Hygiene & Quality: Comprehensive inspection confirmed zero missing values and zero duplicate records across all 30 features[cite: 1]. Consequently, no row deletion or synthetic imputation was required[cite: 1].
• Feature Preprocessing & Scaling: Feature magnitudes span significantly different scales (e.g., mean area ranges from 143.5 to 2501.0, whereas mean smoothness ranges from 0.053 to 0.163)[cite: 1]. Because optimization in Deep Neural Networks (gradient descent) and Support Vector Machines (margin distance calculation) is sensitive to raw feature magnitude, Z-score standardization (StandardScaler) was applied: $z = (x - \mu) / \sigma$[cite: 1].
• Exploratory Data Analysis (EDA): Correlation analysis revealed high multicollinearity among radius, perimeter, and area features ($r > 0.95$)[cite: 1]. Non-linear kernels (SVM RBF) and dense hidden layers (Neural Network) were prioritized to manage non-linear spatial feature correlations[cite: 1].

3. STAGE 2: DATA SPLITTING & JUSTIFICATION
To maintain strict experimental integrity and prevent data leakage, the dataset was partitioned into three independent subsets[cite: 1, 2]:
- Training Set | 70% (398 samples) | Used to update model weights and learn decision boundaries[cite: 1, 2].
- Validation Set | 15% (85 samples) | Used for monitoring epoch-by-epoch loss, tuning, and early stopping[cite: 1, 2].
- Test Set | 15% (86 samples) | Held out entirely until final evaluation to measure generalization performance[cite: 2, 3].

Stratified sampling was enforced during the split to preserve the exact 62.7:37.3 ratio of Benign to Malignant cases across all three partitions, ensuring unbiased class representations during model training and evaluation[cite: 2].

4. STAGE 3: MODEL SELECTION AND DEVELOPMENT
Three distinct classification architectures were developed to evaluate non-linear feature spaces[cite: 2]:
• Mandatory Deep Neural Network (MLP): Formulated with an input layer of 30 neurons, two hidden dense layers (64 and 32 units) with Rectified Linear Unit (ReLU) activations, Dropout regularization (0.3 and 0.2), and a single Sigmoid output unit for probability estimation[cite: 2].
• Support Vector Machine (SVC): Utilized a Radial Basis Function (RBF) kernel to project the 30-dimensional feature space into higher dimensions, enabling optimal maximum-margin hyper-plane separation[cite: 2].
• Random Forest Classifier: An ensemble method combining 100 decision trees trained on bootstrap samples to assess feature interaction importance and resist overfitting[cite: 2].

5. STAGE 4: MODEL TRAINING & HYPERPARAMETER OPTIMIZATION
The Neural Network was trained with the Adam optimizer (learning rate = 0.001) and binary_crossentropy loss[cite: 2]. Early Stopping (patience = 10) monitored validation loss to halt execution when convergence was achieved, preventing memorization of noise[cite: 2].
Figure 1: Neural Network Training & Validation Diagnostics (Loss and Accuracy curves over 45 epochs showing smooth convergence without divergence, confirming that Dropout layers effectively prevented overfitting)[cite: 2].

6. STAGE 5: MODEL FINAL EVALUATION & COMPARISON
Models were evaluated on the unseen test set (86 samples). Primary metrics include Accuracy, Precision, Recall, and F1-Score[cite: 2, 3].

| Model Architecture | Accuracy | Precision (Malignant) | Recall (Malignant) | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| Support Vector Machine (RBF) | 98.84% | 0.99 | 0.99 | 0.99[cite: 3] |
| Mandatory Neural Network (MLP) | 97.67% | 0.98 | 0.98 | 0.98[cite: 3] |
| Random Forest Classifier | 96.51% | 0.96 | 0.98 | 0.97[cite: 3] |

7. DISCUSSION
All models demonstrated high performance (>96% test accuracy). However, the Support Vector Machine (SVM) achieved the top overall performance (98.84% accuracy, 0.99 recall)[cite: 3]. In diagnostic oncology, maximizing Recall is crucial: missing a malignant diagnosis (False Negative) has severe health consequences compared to a False Positive[cite: 3]. SVM excelled because its maximum-margin hyper-plane handles structured high-dimensional datasets with strong separability exceptionally well, slightly outperforming the Neural Network on this sample size[cite: 3].

8. CONCLUSION & FUTURE WORK
This project successfully built and evaluated machine learning classifiers for automated breast cancer detection[cite: 3]. The SVM model provided superior sensitivity and precision[cite: 3]. 
Future Work: Incorporating Recursive Feature Elimination (RFE) to trim the 30 features down to the top 5 most impactful markers would reduce computational overhead for real-time diagnostic software integration[cite: 3].

GitHub Project Repository: https://github.com/abalharbi99/DS471-Breast-Cancer-ML-Project.git
Includes full Jupyter Notebook code, preprocessing scripts, model weights, and performance evaluation curves[cite: 3].
