# Scalable Fraud Detection in Credit Card Transactions Using PySpark

**Course:** DS/CMPSC 410  
**Semester:** Fall 2025  
**Team Name:** AGT Fraud Detection Team  
**Team Members:** Tarun Kumar Srikumar, Zhixuan Alex Zhou, Yashwanth Velayudham, Nihal Ravindra, Rhianna Ferreira, Yongqi Sheng, Abhilash Katigiri

---

## 1. Introduction and Motivation
Fraudulent activities in the banking sector result in up to **$40 billion annually** worldwide. This project addresses the challenge of detecting fraudulent credit card transactions within massive datasets. By using **PySpark**, we leverage distributed processing to handle the volume and variety of data that traditional tools like Pandas or Scikit-learn cannot manage efficiently.

## 2. Project Objectives
* **Scalable Data Handling:** Collect and preprocess large-scale transaction data, scaling datasets to simulate big data environments.
* **PySpark Workflows:** Develop pipelines for data cleaning, transformation, and feature extraction (e.g., transaction velocity).
* **Distributed Machine Learning:** Implement anomaly detection using Spark MLlib (Random Forest, Logistic Regression).
* **Performance Analysis:** Evaluate model performance and scalability across varying cluster sizes.

## 3. Data Description
* **Source:** [Kaggle’s Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).
* **Size:** 284,807 records (150 MB CSV).
* **Characteristics:** 30 features (28 anonymized PCA components, Time, and Amount).
* **Challenges:** High class imbalance (only **0.172%** are fraud), high dimensionality, and skewed distributions.

## 4. Technical Approach
### Tools & Frameworks
* **Core:** PySpark (DataFrames, SQL, MLlib).
* **Analysis:** Pandas, Matplotlib, Scikit-learn (for baselines).
* **Cluster:** 3-4 CPU nodes with 2-5 GB temporary storage.

### Pipeline Overview
1. **Ingestion:** Load scaled CSVs into PySpark DataFrames and normalize the `Amount` feature.
2. **EDA:** Use PySpark SQL for summary statistics and identifying data skews.
3. **Modeling:** Feature engineering followed by training classifiers using MLlib pipelines.
4. **Evaluation:** Generate confusion matrices and precision-recall curves to interpret results.

## 5. Results and Findings
The project successfully demonstrated that distributed processing significantly enhances both speed and detection accuracy.

| Metric | Value |
| :--- | :--- |
| **Accuracy** | 0.9993 |
| **AUC-ROC** | 0.99 |
| **Precision** | 0.87 |
| **Recall (Fraud)** | 0.87 |
| **F1 Score** | 0.88 |

**Key Findings:**
* Class weighting significantly improved fraud detection recall.
* Scalability tests showed **3× faster** query times with 100 partitions compared to 10.
* ROC and PR curves show near-perfect separation between classes.

## 6. Visual Summaries
The following visuals illustrate the model's performance and the benefits of scalability:





---

## 7. Division of Labor
| Task | Assigned To |
| :--- | :--- |
| **Data Acquisition & Preprocessing** | Yashwanth Velayudham, Abhilash Katigiri |
| **Exploratory Data Analysis (EDA)** | Yongqi Sheng, Zhixuan Alex Zhou |
| **Feature Engineering** | Rhianna Ferreira, Tarun Kumar Srikumar |
| **Model Building & Training** | Tarun Kumar Srikumar, Zhixuan Alex Zhou |
| **Evaluation & Visualization** | Nihal Ravindra, Rhianna Ferreira, Yashwanth Velayudham |
| **Documentation & Integration** | Nihal Ravindra, Abhilash Katigiri |

## 8. Work Plan & Timeline
* **Weeks 1-2:** Data acquisition and synthetic scaling.
* **Weeks 3-4:** EDA and problem identification (imbalance).
* **Weeks 5-6:** Feature engineering and model building.
* **Week 7:** Model evaluation and visualization.
* **Week 8:** Pipeline refinement.
* **Weeks 9-10:** Documentation and final report.

## 9. Potential Challenges & Mitigation
* **Data Volume:** Mitigated by sampling subsets for local testing before scaling to the cluster.
* **Imbalance:** Mitigated using oversampling and class-weighting techniques.
* **Resources:** Optimized Spark jobs to run within cluster limits during off-peak hours.

---

## 10. Repository Link
Full code, notebooks, and visualizations can be found here:  
[https://github.com/AGTNurat/DS410FraudDetection](https://github.com/AGTNurat/DS410FraudDetection)
