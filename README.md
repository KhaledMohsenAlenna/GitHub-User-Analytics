# GitHub User Data Engineering and Quality Pipeline

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Data Quality](https://img.shields.io/badge/Data%20Quality-Pandera%20%7C%20Great%20Expectations-success)
![Security](https://img.shields.io/badge/Security-GDPR%20%7C%20Encryption-red)

## Project Overview
This project implements a comprehensive end-to-end data engineering pipeline designed to clean, validate, and secure GitHub user data for downstream Artificial Intelligence and Machine Learning applications.

Unlike standard exploratory analysis, this pipeline enforces strict Data Governance protocols, including rigorous schema validation, GDPR compliance mechanisms (such as the "Right to be Forgotten"), and Personally Identifiable Information (PII) encryption. Additionally, it includes a synthetic data generation module to simulate low-resource environments and test pipeline robustness.

## Key Features

### 1. Advanced Data Validation and Quality Assurance
* **Schema Enforcement:** Utilized **Pandera** to define strict data types and validate dataframe schemas, ensuring data integrity across all records.
* **Automated Testing:** Integrated **Great Expectations** to execute automated data quality checks and generate validation reports, preventing data drift and ensuring schema compliance.

### 2. GDPR Compliance and Data Security
* **PII Encryption:** Implemented **Fernet (Symmetric Encryption)** to secure sensitive text fields, such as user biographies.
* **Anonymization:** Applied SHA-256 hashing to email addresses to ensure user anonymity while maintaining unique identifiers for analysis.
* **Data Erasure Protocols:** Developed a dedicated function to permanently delete user records based on unique identifiers, complying with modern privacy regulations and the "Right to be Forgotten."

### 3. Data Cleaning and Feature Engineering
* **Automated Profiling:** Deployed **YData Profiling** to generate comprehensive HTML reports for Exploratory Data Analysis (EDA).
* **Statistical Imputation:** Addressed missing values in numerical columns using statistical methods to maintain dataset distribution.
* **Feature Scaling:** Applied **StandardScaler** (Scikit-learn) to normalize metrics such as `followers` and `public_repos`, optimizing the data for ML model ingestion.
* **Outlier Management:** Identified and handled outliers using the Interquartile Range (IQR) method to reduce statistical noise.

### 4. Synthetic Data Generation
* **Simulation:** Leveraged the **Faker** library to generate realistic synthetic HR data (including names, salaries, and joining dates) to validate pipeline performance under various data scenarios.

## Technical Stack

| Category | Technologies |
|----------|--------------|
| **Core Language** | Python 3.x |
| **Data Manipulation** | Pandas, NumPy |
| **Data Validation** | Pandera, Great Expectations |
| **Security & Cryptography** | Cryptography (Fernet), Hashlib |
| **Visualization** | Matplotlib, Seaborn, YData Profiling |
| **Preprocessing** | Scikit-learn |

## Installation and Usage

### 1. Clone the Repository
```bash
git clone [https://github.com/KhaledMohsenAlenna/GitHub-User-Analytics.git](https://github.com/KhaledMohsenAlenna/GitHub-User-Analytics.git)
cd GitHub-User-Analytics
2. Install Dependencies
Bash

pip install pandas pandera great_expectations ydata-profiling cryptography faker scikit-learn seaborn
3. Execute the Pipeline
Bash

jupyter notebook data_cleaning_pipeline.ipynb
Analytical Insights
The pipeline provides actionable insights into the dataset, including:

User Role Distribution: Analysis of administrative vs. standard user ratios.

Engagement Metrics: Correlation analysis between public repository counts and follower growth.

Security Metrics: Verification of encryption coverage for sensitive bio data.

Author: Khaled Mohsen
