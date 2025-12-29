# Scalable Fraud Detection in Credit Card Transactions Using PySpark

**Course:** DS/CMPSC 410  
**Semester:** Fall 2025  


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
<img width="505" height="293" alt="DS410 VISUAL 6" src="https://github.com/user-attachments/assets/7a84440d-f2f9-4354-bcaa-8a121c810948" />
<img width="969" height="291" alt="DS410 VISUAL 7" src="https://github.com/user-attachments/assets/db67d852-7e9b-4fb1-90a0-566de4c6d44f" />
<img width="642" height="365" alt="DS410 VISUAL 1" src="https://github.com/user-attachments/assets/5168c1d3-c8d7-4992-8000-b70fd722c1e9" />
<img width="469" height="302" alt="DS410 VISUAL 2" src="https://github.com/user-attachments/assets/6ccc9007-7a56-4e46-ad30-5fa33c9a676c" />
<img width="976" height="290" alt="DS410 VISUAL 3" src="https://github.com/user-attachments/assets/fb996fb6-320b-4097-9460-21920fd89d21" />
<img width="945" height="295" alt="DS410 VISUAL 4" src="https://github.com/user-attachments/assets/d6217007-35e5-49cc-a32f-4d755ea6e1f2" />
<img width="917" height="712" alt="DS410 VISUAL 5" src="https://github.com/user-attachments/assets/74b4a011-3b5a-4d10-80c8-45ee9ba50dca" />



---


## 7. Work Plan & Timeline
* **Weeks 1-2:** Data acquisition and synthetic scaling.
* **Weeks 3-4:** EDA and problem identification (imbalance).
* **Weeks 5-6:** Feature engineering and model building.
* **Week 7:** Model evaluation and visualization.
* **Week 8:** Pipeline refinement.
* **Weeks 9-10:** Documentation and final report.

## 8. Potential Challenges & Mitigation
* **Data Volume:** Mitigated by sampling subsets for local testing before scaling to the cluster.
* **Imbalance:** Mitigated using oversampling and class-weighting techniques.
* **Resources:** Optimized Spark jobs to run within cluster limits during off-peak hours.

---

## 9. Repository Link
Full code, notebooks, and visualizations can be found here:  
[https://github.com/AGTNurat/DS410FraudDetection](https://github.com/AGTNurat/DS410FraudDetection)
