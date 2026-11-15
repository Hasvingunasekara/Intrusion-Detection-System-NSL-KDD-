# Intrusion Detection System (NSL-KDD) - README

A comprehensive Machine Learning pipeline for Network Intrusion Detection using the **NSL-KDD** dataset. This project processes network traffic features to classify connections as either **Normal** or an **Attack**.

---

## 📂 Project Structure

*   `Intrusion Detection System [NSL-KDD].ipynb`: The primary Jupyter Notebook containing the full end-to-end data processing, exploratory data analysis (EDA), and classification pipeline.
*   `archive (6)/KDDTrain+.txt`: The training data split provided by the NSL-KDD benchmark.
*   `README.md`: Project documentation.

---

## 🛠️ Pipeline Overview

### 1. Import Libraries & Setup
Essential data science and visualization packages are loaded (`numpy`, `pandas`, `matplotlib`, `seaborn`). Display settings are customized for better dataframe readability.

### 2. Read Dataset & Feature Alignment
*   The raw text dataset (`KDDTrain+.txt`) lacks native header columns. 
*   Columns are explicitly mapped using standard NSL-KDD feature names (spanning 43 attributes, including duration, protocol type, service, flag, source/destination bytes, and various traffic rate metrics) sourced from established benchmark references.

### 3. Data Cleaning & Inspection
*   **Null Values:** Checked and confirmed zero missing values across all 125,972 rows.
*   **Duplicates:** Verified that no duplicate rows exist in the training set.
*   **Outliers:** Statistical distribution checks (`describe()`) and boxplot visualizations were performed. Outliers are preserved as they often represent critical signatures of actual network anomalies/attacks.
*   **Target Label Simplification:** The multi-class attack labels (e.g., *neptune, satan, ipsweep*, etc.) are consolidated into a binary classification task:
    *   `normal`: Standard network behavior.
    *   `attack`: Any recorded intrusion attempt.

### 4. Exploratory Data Analysis (EDA)
*   Categorical features (`protocol_type`, `service`, `flag`, and consolidated `attack` labels) are inspected for value distributions.
*   Visualizations map out feature distributions to evaluate their impact on attack detection.

---

## 🚀 Getting Started

### Prerequisites
Make sure you have Python installed along with the required libraries:
```bash
pip install numpy pandas matplotlib seaborn
