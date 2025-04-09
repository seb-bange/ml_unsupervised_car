# 🚗 Vehicle Silhouette Clustering – Prospect Auto

## 📄 Project Overview

This project focuses on clustering a dataset of **vehicle silhouettes** based on **geometric features** extracted from the silhouettes of vehicles in various angles. The dataset consists of features that describe three different vehicle types:

- **bus**
- **van**
- **car**

The goal of this project is to explore **unsupervised learning** to solve the classification problem presented by **Prospect Auto**, a chain of car repair shops. Specifically, the task is to classify vehicles based on their silhouette using clustering algorithms.

---

## 🧠 Problem Statement

Prospect Auto requested a model that would differentiate between three vehicle classes based on their silhouettes. The challenge is to achieve this classification without labeled data. The solution is to explore unsupervised learning techniques to cluster the vehicles and evaluate the quality of the clusters.

---

## 🛠 Project Steps

1. **Data Preparation**  
   - Imported the necessary libraries  
   - Loaded and read the dataset  
   - Normalized and standardized the features  
   - Split the data into training and testing subsets  

2. **Dimensionality Reduction**  
   - Used **Principal Component Analysis (PCA)** to reduce the original 18 features while preserving most of the variance in the data  

3. **Clustering Models**  
   - Applied **K-Means Clustering**  
   - Applied **DBSCAN Clustering**  

4. **Evaluation**  
   - Measured clustering performance using **Silhouette Score** and other relevant metrics  
   - Evaluated the effectiveness of unsupervised learning methods for this dataset

---

## 📊 Evaluation & Results

### 🔹 K-Means

- **Silhouette Score**: `0.31`
- Insights:
  - The clustering identified three regions well, but there was significant **overlap between the clusters**.
  - **Further feature optimization** led to only **slight improvements** in the clustering results.
  - **Conclusion**: K-Means is **not suitable** for this dataset due to insufficient separation between clusters.

### 🔸 DBSCAN

- **Silhouette Score**: `0.27`
- **Noise Points**: 155 (≈ 20% of the data)
- **Davies-Bouldin Index**: ≈ `1.0`
- Insights:
  - The clustering resulted in a high number of **noise points**, indicating that the clusters are not easily separable.
  - The **Davies-Bouldin Index** suggests **moderate cluster quality**, indicating that some clusters were compact, but others showed overlap.
  - **Conclusion**: DBSCAN also performed **suboptimally** for this dataset.

---

## ✅ Conclusion

During the **supervised learning phase**, I used **Support Vector Machines (SVM)** with an RBF kernel, achieving **excellent results** across all metrics. The model successfully classified vehicle silhouettes with high accuracy.

However, in the **unsupervised learning phase**, both **K-Means** and **DBSCAN** performed poorly, with low silhouette scores and high levels of cluster overlap. The clustering models failed to differentiate the vehicle types effectively.

🔎 **Recommendation**: Given the challenges with unsupervised learning, **supervised learning** (such as **SVM with an RBF kernel**) remains the **optimal solution** for this task. Pre-classifying the data would yield highly effective results for vehicle classification.

---

🔗 **Notebook**: [View on Google Colab](https://colab.research.google.com/drive/1YW85WScqkZJg2i3ze1pLU2Sy97kBA9bl?usp=sharing)

