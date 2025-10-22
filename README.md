# ✈️ PySpark Air Traffic Analysis and Regression Modeling

## Project Overview

This project focuses on a comprehensive analysis of the "Air Traffic Passenger Statistics" dataset. The analysis leverages **PySpark** on **Google Colab** to handle large-scale data processing, perform rigorous Exploratory Data Analysis (EDA), conduct data cleaning and feature engineering, and apply advanced regression techniques.

The primary objective is to understand passenger traffic patterns and build predictive models (Decision Tree and Random Forest Regressors) to forecast passenger counts based on various operational and geographic features.

### 📝 Important Note on Language Translation

**This project was originally developed in Spanish and has been professionally translated into English.** All variable names, comments, markdown, and output descriptions within the notebook reflect this English translation to ensure clarity and adherence to international coding standards.

## 🛠️ Technologies and Environment

* **Platform:** Google Colab
* **Core Library:** PySpark (for distributed data processing)
* **Language:** Python
* **Modeling:** PySpark MLlib (Decision Tree Regressor, Random Forest Regressor)
* **Version Control:** GitHub

## 📂 Project Structure

| File/Folder | Description |
| :--- | :--- |
| `pyspark_air_traffic_analysis.ipynb` | The main Jupyter Notebook containing all the code, analysis, and modeling steps. |
| `/data` | **Placeholder for the input CSV data file.** (The original file is loaded from Google Drive). |
| `/results` | Contains the final exported CSV with aggregated statistical results. |
| `README.md` | This overview file. |

## 🚀 Execution Steps (How to Run the Analysis)

The project is designed to be executed entirely within a Google Colab environment.

1.  **Setup Colab:** Open the `pyspark_air_traffic_analysis.ipynb` file in Google Colab.
2.  **Install PySpark:** The first cell automatically installs the necessary `PySpark` library.
3.  **Data Access:** The notebook requires access to the input CSV file, `Air_Traffic_Passenger_Statistics.csv`, which is expected to be mounted from your **Google Drive**.
    * **Crucial:** You must update the `CSV_PATH` variable in **Section 1** to point to the correct location of your dataset on your mounted Google Drive.
4.  **Run:** Execute all cells sequentially (**Runtime** $\rightarrow$ **Run all**).

## 💡 Key Analysis Highlights

The notebook covers the following major steps:

### 1. Data Ingestion and EDA
* Spark Session initialization and schema inference.
* Counting unique airlines and filtering records for specific carriers (e.g., Air China, Air Berlin).
* Aggregation of total passengers by operating airline.

### 2. Data Cleaning and Preparation
* Filtering out inconsistent or outdated airline entries (e.g., "United Airlines - Pre 07/01/2013").
* Calculation of the **average passenger count** per airline.
* Deduplication of `GEO Region` records, retaining the entry with the maximum passenger count.
* **Export of aggregated results** (Averages and Unique Geo Regions) to a combined CSV file.

### 3. Statistical Analysis
* Calculation of **Mean and Standard Deviation** for `Adjusted Passenger Count` grouped by key categorical features (`Year`, `Month`, `GEO Region`, `Terminal`, `Airline` codes, etc.) to understand traffic variability.

### 4. Feature Engineering and Correlation
* Categorical features (`Month`, `GEO Region`, etc.) are converted to numerical indices using `StringIndexer`.
* A **Pearson Correlation Matrix** is computed to identify the top 10 strongest linear relationships between the engineered features and the target variable.

### 5. Data Quality
* Identification and imputation of missing values (`nulls`) in IATA code columns using the **mode** (most frequent value).
* Final removal of exact duplicate rows.

### 6. Predictive Modeling (PySpark MLlib)

The cleaned and prepared dataset is used to train and evaluate two regression models with the goal of predicting the `Adjusted Passenger Count`:

| Model | Key Parameters | Performance Metric |
| :--- | :--- | :--- |
| **Decision Tree Regressor** | `maxDepth=10`, `minInstancesPerNode=50` | $R^2$ and RMSE |
| **Random Forest Regressor** | `numTrees=100`, `maxDepth=15` | $R^2$ and RMSE |
