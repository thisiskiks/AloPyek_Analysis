# 🛵 AloPeyk Operational Efficiency & Fleet Segmentation Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458)
![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-F7931E)
![Status](https://img.shields.io/badge/Status-Complete-green)

## 📌 Project Overview
This project provides a comprehensive data-driven analysis of **AloPeyk's operational performance** across three major cities: **Tehran, Mashhad, and Shiraz**. The goal was to identify bottlenecks in the last-mile delivery ecosystem, detect statistical anomalies in service quality, and segment the fleet (Vendors & Bikers) to optimize resource allocation.

Using **Python** for data processing and **Unsupervised Machine Learning (K-Means)** for segmentation, this analysis delivers actionable insights to reduce hyper-delays and improve customer satisfaction.

---

## 🚀 Key Objectives
1.  **Operational Health Check:** Assess KPIs (Order Volume, Delay Rates, Queue Times) across different geographies.
2.  **Anomaly Detection:** Identify statistically significant spikes in failure rates using **Z-Score analysis**.
3.  **Root Cause Analysis:** Determine whether delays are driven by traffic, supply shortages, or vendor prep times.
4.  **Strategic Segmentation:** Cluster Vendors and Bikers into meaningful business groups (e.g., "Stars" vs. "High Risk") using **K-Means Clustering**.

---

## 🛠️ Tools & Technologies
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (StandardScaler, K-Means, Elbow Method)
* **Environment:** Google Colab / Jupyter Notebook

---

## 📊 Methodology & Workflow

### 1. Data Preprocessing & Cleaning
* Handled missing values and removed outliers (e.g., GPS errors showing speeds > 120 km/h).
* Engineered new features: `Operation_DU` (Total Duration), `Is_HyperDelay` (>60 min flag), and `Speed_LastMile_kmh`.

### 2. Exploratory Data Analysis (EDA)
* **City Scorecard:** Identified that while **Tehran** handles the highest volume, **Shiraz** suffers from the highest "Queue Time" (supply shortage).
* **Heatmaps:** Revealed that delays are highly correlated with specific **"Confirmation Hours"** (peak demand) rather than average fleet speed.
* **Trend Analysis:** Daily time-series plots highlighted system-wide volatility and specific degradation trends in Shiraz.

### 3. Statistical Anomaly Detection
* Applied **Z-Score Analysis** to flag daily failure rates.
* Detected critical anomalies (Z > 2.0) in **Tehran** on May 30th and June 5th, indicating severe, non-random operational incidents in the core market.

### 4. Advanced Segmentation (K-Means)
* **Vendor Clustering:** Segmented into 4 groups.
    * *Insight:* A "Ghost Cluster" was found with a **67% failure rate** but negligible volume, separating noise from actual operational risks.
* **Biker Clustering:** Segmented into 4 groups based on Volume, Speed, and Reliability.
    * *Insight:* Identified a "Critical Risk" segment (low activity, high error) vs. "Workhorses" (high activity, low error).

---

## 📈 Key Insights & Results

| Insight | Description | Impact |
| :--- | :--- | :--- |
| **The "Tehran Paradox"** | Tehran is stable but experienced 2 critical shock events (Anomalies). | High impact due to volume dominance. |
| **Supply Shortage** | Shiraz has a ~10 min average queue time. | Indicates a need for dynamic pricing/supply incentives. |
| **Speed vs. Quality** | No strong correlation between high speed and low delay. | KPIs should shift from speed to "Reliability". |
| **Pareto Rule** | ~4% of vendors cause a disproportionate amount of delays. | Targeted offboarding required. |

---

## 📂 Project Structure
```text
├── AloPeyk_Task_KianaSammak.ipynb  # Main Analysis Notebook (Source Code)
├── DataTask.xlsx                   # Raw Dataset (Confidential/Sample)
├── README.md                       # Project Documentation
└── requirements.txt                # List of dependencies
