# Addressing Data Leakage in UAV CyberattackDetection: A Realistic Machine Learning Benchmark

## 📌 Paper Overview
As the operational scope of Unmanned Aerial Vehicles (UAVs) expands, the need for robust security against cyber-attacks such as GPS Spoofing and Jamming has become critical. This project focuses on developing an anomaly-based Intrusion Detection System (IDS) for UAVs using realistic machine learning evaluations. 

A prevalent issue in many existing UAV cybersecurity studies is **data leakage**—where models achieve near 100% accuracy by relying on features (like explicit attack flags) that would be unavailable during a real-world, real-time attack. This project addresses this flaw by systematically eliminating leakage-prone features and using domain-specific telemetry (like control signal variances and integrated GPS uncertainties) to establish a mathematically sound, realistic performance baseline.

## 👥 Authors
* **Şerif Mert Çeker** (Fenerbahçe University)
* **Güldal Akçiçek** (Fenerbahçe University)
* **Sıla İlayda Dönmez** (Fenerbahçe University)
* **Aziz Burak Kaçar** (Fenerbahçe University)

## 📊 Dataset Information
This project utilizes the well-regarded **UAV Attack Dataset**, which contains real-world flight logs capturing benign flights, GPS Spoofing, and GPS Jamming maneuvers.

* **Original Data:** UAV Attack Dataset (IEEE DataPort Open Access)
* **Original Data Link:** [https://ieee-dataport.org/open-access/uav-attack-dataset](https://ieee-dataport.org/open-access/uav-attack-dataset)

## ⚙️ Methodology & Results
1. **Data Preprocessing & Feature Selection:** Explicitly leakage-prone parameters (e.g., `timestamp`, `jamming_indicator`) and highly correlated redundant metrics were dropped. New features representing horizontal velocity and control standard deviations were engineered.
2. **Models Evaluated:** Logistic Regression, K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Random Forest (RF), and eXtreme Gradient Boosting (XGBoost).
3. **Performance:** Under strict, realistic conditions without data leakage, the **XGBoost** model demonstrated the best performance, successfully classifying attacks with an accuracy and F1-score of **97.35%**.

## 📂 Repository Structure

* `Data/` - Contains the raw and processed versions of the UAV flight logs.
* `Models/` - Jupyter Notebooks containing the data engineering pipelines, hyperparameter tuning, and implementation of the machine learning classifiers (`xgboost_model.ipynb`, `SupportVectorMachine_model.ipynb`, etc.).
* `Data Preparation and Visualisation/` - Scripts and notebooks used for Exploratory Data Analysis (EDA) and generating dataset figures (Correlation Matrices, Feature Importance, etc.).
* `LaTeX_Template/` - Contains the finalized, IEEE-compliant LaTeX source code (`paper.tex`) for the academic paper output, along with necessary `.cls` files and embedded PDF figures.
* `Literatür/` - PDF repository of cited academic literature related to UAV cyber security and dataset benchmarks.
* `paper_draft.md` - The markdown equivalent draft of the final academic paper.
* `format_conflicts.md` - A report mapping the paper's compliance with exact IEEE constraints.
* `Live GPS Spoofing and Jamming/` - Contains specific subsets of the data highlighting targeted attack windows.

## 🚀 How to Run
1. Navigate to the `Models/` directory.
2. Open the individual Jupyter notebooks to view the model training sequences. Ensure you have standard data science libraries installed (`scikit-learn`, `xgboost`, `pandas`, `numpy`, `matplotlib`, `seaborn`).
3. To view or compile the academic paper, navigate to `LaTeX_Template/` and compile `paper.tex` using any standard LaTeX distribution (e.g., pdfLaTeX) or an editor like Overleaf.
