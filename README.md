# ✈️ PySpark Air Traffic Analysis & Regression Modeling

> Original project in **Spanish**, professionally translated into **English** for clarity and international standards.

---

## 📑 Table of Contents
1. [Project Overview](#project-overview)  
2. [Technologies & Environment](#technologies--environment)  
3. [Project Structure](#project-structure)  
4. [Execution Steps](#execution-steps)  
5. [Key Analysis Highlights](#key-analysis-highlights)  
   - [Data Ingestion & Initial EDA](#data-ingestion--initial-eda)  
   - [Data Cleaning & Preparation](#data-cleaning--preparation)  
   - [Statistical Analysis](#statistical-analysis)  
   - [Feature Engineering & Correlation](#feature-engineering--correlation)  
   - [Data Quality Assessment](#data-quality-assessment)  
   - [Predictive Modeling](#predictive-modeling)  
6. [Conclusion](#conclusion)

---

## 🧭 Project Overview
This project performs a **comprehensive analysis** of the *Air Traffic Passenger Statistics* dataset using **PySpark** in Google Colab.  

It includes:  
- Exploratory Data Analysis (EDA)  
- Data Cleaning & Feature Engineering  
- Advanced Regression Modeling (Decision Tree & Random Forest)  

**Objective:** Understand passenger traffic patterns and build predictive models to forecast passenger counts by operational and geographic features.

> ⚠️ **Note:** Originally developed in Spanish; fully translated to English. All code, variable names, markdown, and outputs reflect the translation.

---

## 🛠️ Technologies & Environment
- **Platform:** Google Colab (cloud-based Jupyter environment)  
- **Core Library:** PySpark (distributed data processing)  
- **Language:** Python  
- **Modeling:** PySpark MLlib (Decision Tree, Random Forest Regressors)  
- **Version Control:** GitHub  

---

## 📂 Project Structure
| File / Folder | Description |
|---------------|-------------|
| `notebooks/pyspark_air_traffic_analysis.ipynb` | Main notebook with all code, analysis, and modeling steps |
| `data/` | Placeholder for input CSV (`Air_Traffic_Passenger_Statistics.csv`) from Google Drive |
| `results/` | Exported CSV files with aggregated statistical results |
| `README.md` | Project overview and instructions |
| `.gitignore` | Files/folders excluded from GitHub |

---

## 🚀 Execution Steps
1. **Open Colab:** Load `pyspark_air_traffic_analysis.ipynb`.  
2. **Install PySpark:** The first cell installs PySpark automatically.  
3. **Data Access:** Mount Google Drive and ensure `CSV_PATH` points to your dataset.  
4. **Run All:** Execute all cells sequentially (**Runtime → Run all**).

---

## 📊 Key Analysis Highlights

### Data Ingestion & Initial EDA
- Load dataset into Spark DataFrame; inspect schema and types.  
- Count unique airlines and examine basic statistics for key carriers (Air China, Air Berlin).  
- Aggregate total passengers by airline.

### Data Cleaning & Preparation
- Remove outdated entries (e.g., `"United Airlines - Pre 07/01/2013"`).  
- Calculate **average passenger count** per airline.  
- Deduplicate **GEO Region** records (retain max passengers).  
- Export aggregated results (averages and unique regions) to CSV.

### Statistical Analysis
- Compute **mean & standard deviation** of `Adjusted Passenger Count` by Year, Month, GEO Region, Terminal, Airline codes.  
- Identify trends, seasonality, and traffic variability.

### Feature Engineering & Correlation
- Encode categorical features (`Month`, `GEO Region`, `Terminal`, etc.) using `StringIndexer`.  
- Compute Pearson correlation matrix to find top 10 strongest predictors of passenger traffic.

### Data Quality Assessment
- Impute missing IATA codes using **mode** (most frequent value).  
- Remove exact duplicates for accurate records.

### Predictive Modeling
- **Decision Tree Regressor:** Hyperparameter tuning (`maxDepth`, `minInstancesPerNode`).  
- **Random Forest Regressor:** Hyperparameter tuning (`numTrees`, `maxDepth`).  
- **Evaluation Metrics:** RMSE & R² on training and test sets.  
- Random Forest generally outperforms Decision Tree, providing better predictive accuracy.

---

## 🎯 Conclusion
This project demonstrates a **full end-to-end pipeline** for air traffic passenger analysis and predictive modeling using PySpark:  

- **Insights:** Passenger traffic patterns, seasonal trends, key predictors.  
- **Predictive Power:** Models accurately forecast passenger counts; Random Forest provides the best fit.  
- **Practical Use:** Supports operational planning, route optimization, and resource allocation in the airline industry.  
- **Data Quality:** Highlights the importance of cleaning, deduplication, and feature engineering.

🏅 This project served as my **final assignment for the Big Data Master program at Tokio School**, achieving a **9/10 grade**.
