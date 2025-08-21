# Lifecycle-Anchored VM Morphology Taxonomy for Rightsizing

## 📌 Overview
Cloud platforms often suffer from **inefficient VM provisioning** and **high churn of short-lived instances**, leading to wasted resources and higher costs.  
This project introduces a **lifecycle-anchored morphology taxonomy** for Virtual Machines (VMs) using **minimal telemetry** (aggregate CPU statistics and lifecycle metadata).  

We combine **unsupervised clustering** (Gaussian Mixture Models) with **supervised predictive models** (Random Forest, XGBoost, Logistic Regression) to:
- Discover VM **morphologies** (e.g., steady baseline, bursty survivors, ephemeral spikes).
- Predict **short-lived VMs** with high recall.
- Propose **operational policies** for cloud resource rightsizing.

---

## 🚀 Features
- **Lightweight Feature Set**: Uses only average, p95, max CPU, and VM lifetime.  
- **Clustering (GMM)**: Identifies distinct VM workload morphologies.  
- **Predictive Modeling**: Classifies short-lived VMs using Random Forest, XGBoost, Logistic Regression.  
- **Evaluation**: High recall for detecting ephemeral workloads.  
- **Operational Decision Framework**: Maps VM types to actionable rightsizing policies.

---

## 🛠️ Tech Stack
- **Programming Language**: Python 3.x  
- **Data Analysis**: Pandas, NumPy  
- **Machine Learning**: Scikit-Learn, XGBoost, imbalanced-learn (SMOTE)  
- **Clustering**: Gaussian Mixture Models (Scikit-Learn)  
- **Visualization**: Matplotlib, Seaborn  
- **Statistical Testing**: SciPy (Kruskal-Wallis, BIC)  

---

## 📂 Dataset
- ~50,000 VMs with aggregate CPU metrics and metadata.  
- Features include: average CPU, 95th percentile CPU, max CPU, VM lifetime, vCPU/memory buckets.  
- Dataset used in experiments is not publicly released (provider confidential). Synthetic version may be added for demonstration.  

---

## 📊 Results
- **Morphology Discovery**: Identified 4–6 distinct VM categories.  
- **Classification**:  
  - Logistic Regression → Recall: ~82%  
  - Random Forest → Recall: ~92%  
  - XGBoost → Recall: ~90%  
- **Key Insight**: Tree-based models achieve highest recall, crucial for catching ephemeral VMs.  
- **Trade-off Analysis**: Clusters mapped to inefficiency vs. short-lived rates for rightsizing decisions.  

---

## 📸 Example Visualizations
- GMM clustering plots of VM morphologies.  
- ROC-AUC curves for classification models.  
- Trade-off tables for inefficiency vs. short-lived rates.  

---

## 📖 Research Contribution
- Proposes a **taxonomy for VM rightsizing** grounded in lifecycle-aware clustering.  
- Demonstrates **high-recall predictive modeling** for short-lived VMs using minimal telemetry.  
- Provides an **operational framework** for cost and sustainability-aware resource management.  

---

## 🔮 Future Work
- Incorporate **network and I/O telemetry**.  
- Enable **real-time detection** of short-lived workloads.  
- Extend policies for **carbon-aware scheduling**.  

---
