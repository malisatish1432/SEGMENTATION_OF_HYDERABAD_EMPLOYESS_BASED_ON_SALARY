# 📌 Segmentation of Hyderabad Employees Based on Salary :
## 🏦 Project Overview :
### 🔸 This project performs employee segmentation for Hyderabad-based salaried individuals using clustering techniques.
### 🔸 It groups employees into salary-based categories to help HR departments, recruiters, and policymakers make data-driven decisions on salaries, hiring strategies, and retention.
# 🎯 Why It Matters :
### 🔸 Identify salary benchmarks and fair pay ranges for specific job roles.
### 🔸 Support career planning by providing salary expectations based on skills, experience, and qualifications.
### 🔸 Improve hiring efficiency by targeting the right candidates for specific budget ranges.
### 🔸 Assist in employee retention by spotting underpaid high-skilled professionals.
# 📊 Dataset Summary :
## 🔸 Target Variable:
### 🔸 salary (numeric, LPA – Lakhs Per Annum)
### 🔸 Converted into salary brackets for segmentation:
### 🔸 Low Salary (≤ ₹5 LPA)
### 🔸 Mid Salary (₹5–₹10 LPA)
### 🔸 High Salary (> ₹10 LPA)
# Features include:
### 🔸 Job Information: Job Title, Experience, Skills
### 🔸 Demographics: Age, Gender, Location
### 🔸 Employment: Company Type, Industry, Employment Type
### 🔸 Salary-related: Previous Salary, Annual Hike %
# 🛠 Approach :
## 🔸 1. Data Preprocessing:
### 🔸  Missing value handling
### 🔸  Outlier detection & removal
### 🔸 Encoding categorical variables (Label Encoding, One-Hot Encoding)
### 🔸 Feature scaling using StandardScaler
### 🔸 Variance Threshold for feature selection
## 🔸 2. Clustering Models Used :
### 🔸 K-Means Clustering (Elbow Method & Silhouette Score for optimal K)
### 🔸 Hierarchical Clustering (Dendrogram Analysis)
### 🔸 DBSCAN for density-based grouping
### 🔸PCA for dimensionality reduction & visualization
## 🔸 3. Evaluation Metrics :
### 🔸 Silhouette Score
## 🚀 Results :  
| Model               | Silhouette Score | 
|---------------------|------------------|
| K-Means (K=9)       | 0.4289           | 
| Hierarchical (Ward) | 0.4142           | 
| DBSCAN              | 0.3806           | 
## 📌 K-Means with K=9 was selected as the best clustering method due to its highest Silhouette Score and lowest Davies-Bouldin Index.
# 📈 Visualizations :
### 🔸Elbow Method Plot (K selection)
### 🔸Silhouette Analysis Plot
### 🔸Dendrogram (Hierarchical Clustering)
### 🔸PCA 2D Cluster Visualization
### 🔸Feature Distribution Plots
# 🖥 Tech Stack :
### 🔸Python: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, SciPy
### 🔸Clustering: K-Means, Agglomerative Clustering, DBSCAN
### 🔸Feature Engineering: Label Encoding, One-Hot Encoding, Variance Threshold, PCA
### 🔸Environment: Jupyter Notebook
# 📜 Conclusion :
### 🔸Using K-Means clustering, employees were effectively segmented into Nine salary-based groups, enabling:
### 🔸Better hiring strategies
### 🔸Fairer salary decisions
### 🔸Targeted retention programs
### 🔸 This analysis can help HR professionals and companies retain top talent, reduce attrition, and optimize salary budgets.
