# Early Student Failure Detection System

**Machine Learning Semester Project | December 2025**  
**Role:** ML Engineer & Data Analyst  
**Tech Stack:** Python, Scikit-Learn, Pandas, Seaborn

## Project Overview

High failure rates in higher education often stem from a lack of timely intervention. Traditional monitoring is reactive—educators usually notice struggling students only after they fail.

This project implements an **Early Warning System** using a **Decision Tree Classifier**. Unlike academic projects that assume ideal data, this work addresses the **Real-World Research Gap**: handling **Data Quality Anomalies** (e.g., negative study hours, impossible grades) to build a robust, interpretable model.

## The Research Gap & Solution

Most existing literature focuses primarily on model architecture, but real-world educational data is often noisy.

| Problem in Raw Data | Our Solution |
|---------------------|--------------|
| Impossible Values: Negative study hours, grades over 100% | Logic-Based Cleaning: Automated anomaly detection and domain-logic correction |
| Missing Targets: Students without Pass/Fail labels | Data Integrity Check: Removal of unlabeled rows to prevent ground-truth corruption |
| Class Imbalance: Failing students are often the minority | Stratified Splitting: Ensuring equal representation of at-risk students in training and testing |

## Implementation Details

### 1. Data Processing Pipeline
- **Anomaly Detection Audit:** Automated scan for invalid values
- **Imputation:** Median strategies for numerical gaps, Mode for categorical gaps
- **Feature Engineering:** One-Hot Encoding for 'Parent Education' and 'Activities'

### 2. Model Architecture
- **Algorithm:** Decision Tree Classifier (chosen for interpretability)
- **Hyperparameter Tuning:** `GridSearchCV` to optimize `max_depth` (prevents overfitting) and `min_samples_split`
- **Metric Focus:** Prioritized **Recall** to minimize False Negatives (missing a failing student)

## Key Results & Findings

### Model Performance (On Validated Data)
After using the high-quality *Student Performance Factors* dataset to validate the pipeline:
- **Accuracy:** Approximately 85% - 92%
- **Recall (Fail Class):** High sensitivity in detecting at-risk students

### Critical Data Analysis (The "Noise" Discovery)
During the initial phase, we audited a legacy dataset (`student_performance_prediction.csv`).
- **Discovery:** A **0.001 correlation** was found between Study Hours and Passing
- **Conclusion:** We mathematically demonstrated the legacy dataset contained synthetic noise (randomized labels), highlighting the importance of **Data Quality Auditing** before modeling
- *See "Control Experiment" section in the notebook for visual proof*

## Repository Structure
├── Project_Early_Student_Failure_Detection_System.ipynb # Main Analysis Notebook
├── StudentPerformanceFactors.csv # High-Quality Dataset
├── student_performance_prediction.csv # Archived Noisy Legacy Data
└── README.md # Project Documentation


## How to Run

1. Open the `.ipynb` file in **Google Colab** or **Jupyter Notebook**
2. Ensure the `.csv` dataset is in the same directory
3. Run the cells sequentially to see **Data Audit**, **Training**, and **Evaluation** steps

## Contributors

- **Kaleb Kebede** (ID: 1501009) – Lead ML Engineer
- **Abel Adam** (ID: 1500592) – Data Analyst
- **Daniel Abebe** (ID: 1501647) – Researcher

*Submitted to Mr. Mesay A. | Department of Software Engineering*