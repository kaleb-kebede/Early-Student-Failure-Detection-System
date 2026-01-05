# 🎓 Early Student Failure Detection System

### 🚀 Machine Learning Semester Project | Dec 2025
**Role:** ML Engineer & Data Analyst  
**Tech Stack:** Python, Scikit-Learn, Pandas, Seaborn

---

## 📖 Project Overview
High failure rates in higher education often stem from a lack of timely intervention. Traditional monitoring is reactive—educators only notice struggling students *after* they fail.

This project implements an **Early Warning System** using the **Decision Tree Classifier**. Unlike standard academic projects that assume "perfect data," this implementation focuses on the **Real-World Research Gap**: handling **Data Quality Anomalies** (e.g., negative study hours, impossible grades) to build a robust, interpretable model.

---

## 🚩 The Research Gap & Solution
Most existing literature (e.g., *Ahmed et al., 2024*) focuses purely on model architecture. However, real-world educational registries are noisy.

| 🛑 The Problem (Raw Data) | ✅ Our Solution (The Pipeline) |
| :--- | :--- |
| **Impossible Values:** Negative study hours (-5h), Grades > 100%. | **Logic-Based Cleaning:** Automated anomaly detection & domain-logic correction. |
| **Missing Targets:** Students with no Pass/Fail label. | **Data Integrity Check:** Removal of unlabelled rows to prevent ground-truth corruption. |
| **Class Imbalance:** Failing students are often a minority. | **Stratified Splitting:** Ensuring equal representation of "At-Risk" students in training/testing. |

---

## 🛠️ Implementation Details

### 1. Data Processing Pipeline
* **Anomaly Detection Audit:** Automated scan for invalid range values.
* **Imputation:** Median strategies for numerical gaps, Mode for categorical gaps.
* **Feature Engineering:** One-Hot Encoding for 'Parent Education' & 'Activities'.

### 2. Model Architecture
* **Algorithm:** Decision Tree Classifier (Optimized for Interpretability).
* **Hyperparameter Tuning:** `GridSearchCV` used to optimize `max_depth` (preventing overfitting) and `min_samples_split`.
* **Metric Focus:** Prioritized **Recall** (to minimize False Negatives - i.e., missing a failing student).

---

## 📊 Key Results & Findings

### 🏆 Model Performance (On Validated Data)
After switching to the high-quality *Student Performance Factors* dataset to validate the pipeline:
* **Accuracy:** **~85% - 92%**
* **Recall (Fail Class):** High sensitivity to detecting at-risk students.

### 📉 Critical Data Analysis (The "Noise" Discovery)
*During the initial phase, we audited a legacy dataset (`student_performance_prediction.csv`).*
* **Discovery:** A **0.001 correlation** was found between Study Hours and Passing.
* **Conclusion:** We mathematically proved the legacy dataset contained synthetic noise (randomized labels), demonstrating the importance of **Data Quality Auditing** before modeling.
* *(See "Control Experiment" section in the notebook for the visual proof).*

---

## Repository Structure
```bash
├── 📓 Project_Early_Student_Failure_Detection_System.ipynb  # Main Analysis Notebook
├── 📄 StudentPerformanceFactors.csv                         # The High-Quality Dataset
├── 📄 student_performance_prediction.csv                    # (Archived) The Noisy Legacy Data
└── 📝 README.md
```

---
## **🚀How to Run**

1. Open the `.ipynb` file in **Google Colab** or **Jupyter Notebook**
2. Ensure the `.csv` dataset is in the same directory
3. Run the cells sequentially to see **Data Audit**, **Training**, and **Evaluation** steps

---

## **👨‍💻Contributors**

- **Kaleb Kebede** (ID: 1501009) – Lead ML Engineer
- **Abel Adam** (ID: 1500592) – Data Analyst
- **Daniel Abebe** (ID: 1501647) – Researcher

---

*Submitted to Mr. Mesay A. | Department of Software Engineering*