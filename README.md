# 🧑‍💼 Hyderabad Employee Salary Segmentation (Clustering) 💡  
💡 *Unsupervised segmentation of employees by salary, experience, role, and qualifications to aid HR analytics*  
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)]()
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)]()
[![KMeans](https://img.shields.io/badge/KMeans-Clustering-green)]()
[![Agglomerative](https://img.shields.io/badge/Agglomerative-Clustering-lightgrey)]()
[![DBSCAN](https://img.shields.io/badge/DBSCAN-Density--based-yellowgreen)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()


---

## 🧭 Table of Contents
- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Dataset](#-dataset)
- [Workflow](#-workflow)
- [Clustering Performance](#-clustering-performance)
- [Visualizations](#-visualizations)
- [Insights](#-insights)
- [Limitations](#-limitations)
- [Future Work](#-future-work)
- [Tools & Libraries](#-tools--libraries)
- [Conclusion](#-conclusion)
- [Author](#-author)

---

## 🔍 Overview
This project performs **unsupervised clustering** to segment employees in **Hyderabad** based on their **salary** along with attributes like **experience**, **designation**, **company**, **location**, and **qualifications**.  

The goal is to help HR teams with:
- **Salary benchmarking** and fair pay ranges  
- **Talent retention** by spotting underpaid skilled groups  
- **Targeted hiring strategies** and compensation design  
- **Workforce analytics** for planning and budgeting  

---

## 📊 Problem Statement
- **Goal:** Group employees into meaningful clusters that reflect salary bands and career profiles  
- **Type:** Unsupervised Learning (Clustering)  
- **Primary Variables:** `salary`, `experienceMas`, `designation`, `qualificationMas`, `qualificationMas2`, `companyName`, `locationCurrentMas`  

---

## 📁 Dataset
- **Name:** Hyderabad Employees Dataset  
- **Shape:** *(28,847 rows × 9 columns)*  
- **Columns:**  
  `candidateName`, `companyName`, `designation`, `experienceMas`, `locationCurrentMas`, `qualificationMas`, `qualificationMas2`, `salary`, `Category`  
- **Missing Values (notable):**  
  - `designation` (~4630 missing)  
  - `qualificationMas` (~4876 missing)  
  - `qualificationMas2` (~13398 missing)  
- Salary & experienceMas have **no missing values**  

> 💡 *Salary may also be binned into Low (≤ ₹5 LPA), Mid (₹5–10 LPA), High (> ₹10 LPA) for interpretability.*

---

## 🧪 Workflow
### 1️⃣ Data Understanding
- Reviewed schema, data types, missing values, and basic distributions  

### 2️⃣ Data Cleaning & Preprocessing
- Imputed/handled missing values (`designation`, `qualifications`)  
- Encoded categorical features (`designation`, `company`, `location`, `qualifications`)  
- Scaled numerical features for clustering stability  

### 3️⃣ Exploratory Data Analysis (EDA)
- Salary distributions and experience trends  
- Category-wise counts (designation, qualifications, locations)  
- Pairwise relationships and outlier checks  

### 4️⃣ Dimensionality Reduction
- **PCA** for structure + speed  
- **t-SNE** for cluster visualization  

### 5️⃣ Clustering Algorithms
- **K-Means** (various *k* via elbow/silhouette)  
- **Agglomerative Clustering** (linkage: ward/complete/average)  
- **DBSCAN** (ε and min_samples tuning)  

### 6️⃣ Evaluation
- **Silhouette Score** (higher is better)  
- **Davies–Bouldin Index** (lower is better)  
- **Calinski–Harabasz Score** (higher is better)  

---

## 🧩 Clustering Performance
✅ In this dataset, **K-Means (k=2)** produced the most coherent and interpretable clusters aligned with salary and experience patterns.  

| Algorithm       | Silhouette | Davies–Bouldin | Calinski–Harabasz | k / (ε, min_samples) | Notes |
|-----------------|-----------:|---------------:|------------------:|---------------------:|--------------------------------|
| **K-Means ✅**  | **0.650**  | **0.516**      | **70538.43**      | k = 2                | Best separation & balance       |
| Agglomerative   | 0.643      | 0.532          | 69301.92          | k = 2                | Good but slightly less balanced |
| DBSCAN          | -0.071     | 1.622          | 29.60             | -   | Many noise points; weak sep.    |

---

## 🏆 Best Model Selected
- **Algorithm** : K-Means  
- **No. of Clusters** : 2  
- **Silhouette Score** : 0.650  
- **Davies–Bouldin** : 0.516  
- **Calinski–Harabasz**: 70,538.43  

---

## 📈 Visualizations
- **Elbow & Silhouette plots** to select optimal *k*  
- **PCA/t-SNE 2D cluster maps**  
- **Cluster profiles**: mean salary, experience, top designations/qualifications per cluster  
- **Box/violin plots** of salary by cluster  

---

## 💡 Insights
- Clear grouping into **Low/Mid/High salary clusters** with distinct **experience** and **qualification** profiles  
- Specific **designations** and **companies** dominate higher-salary clusters  
- **Experience** strongly correlates with salary clusters; qualifications further refine segments  
- Location mostly **Hyderabad/Secunderabad**, minor variance impact compared to role & experience  

---

## ⚠️ Limitations
- Missing values in designation/qualifications can blur cluster boundaries  
- DBSCAN sensitive to ε; may label many points as noise on high-dimensional sparse encodings  
- Clusters reflect correlations, **not causation**; interpret with domain context  

---

## 🚀 Future Work
- Add domain features (tech stack, industry segment, company size)  
- Try **Gaussian Mixture Models** and **HDBSCAN**  
- Automated model selection pipeline (Grid/Optuna) for *k*, linkages, and ε  
- Build an **interactive dashboard** (Streamlit) for HR to explore clusters  

---

## 🛠 Tools & Libraries
- Python, pandas, numpy  
- scikit-learn (KMeans, Agglomerative, DBSCAN, PCA, t-SNE)  
- matplotlib, seaborn  
- joblib (model artifacts)  

---

## 📜 Conclusion
**K-Means** provided the most stable and interpretable segmentation of Hyderabad employees by salary, delivering actionable clusters for **salary benchmarking**, **hiring strategy**, and **retention planning**.  

The notebook follows a complete workflow—from **EDA** and **preprocessing** to **algorithm comparison** and **cluster evaluation**—to arrive at a practical segmentation solution.  

---

## 👤 Author
**Mali Satish**  
🎓 *M.Sc. Statistics & Computing @ BHU*  
💡 *Machine Learning & Data Science Enthusiast*  

