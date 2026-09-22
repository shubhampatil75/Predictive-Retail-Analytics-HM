# 🛍️ Predictive Retail Analytics: H&M

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-Churn%20Prediction-red.svg)
![Scikit-Surprise](https://img.shields.io/badge/Scikit--Surprise-Recommendation-purple.svg)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Statistics-green.svg)

### An end-to-end machine learning project analyzing H&M retail transactions to understand customer behavior, personalize product recommendations, predict customer churn, and forecast sales.

---

## 📌 Table of Contents

* [Overview](#-overview)
* [Business Problem](#-business-problem)
* [Dataset](#-dataset)
* [Project Objectives](#-project-objectives)
* [Project Workflow](#-project-workflow)
* [Key Analysis](#-key-analysis)

  * [Customer Segmentation](#1-customer-segmentation)
  * [Recommendation System](#2-recommendation-system)
  * [Churn Prediction](#3-customer-churn-prediction)
  * [Sales Forecasting](#4-sales-forecasting)
* [Key Results](#-key-results)
* [Technologies Used](#-technologies-used)
* [Project Structure](#-project-structure)
* [How to Run](#-how-to-run)
* [Visualizations](#-visualizations)
* [Future Improvements](#-future-improvements)
* [Author](#-author)

---

# 📊 Overview

This project applies **Data Science and Machine Learning techniques** to the H&M Personalized Fashion Recommendations dataset.

The objective is to transform historical retail transaction data into actionable insights across four major business areas:

* 👥 Customer segmentation
* 🎯 Personalized product recommendations
* 🚨 Customer churn prediction
* 📈 Sales forecasting

The project combines **exploratory data analysis, feature engineering, unsupervised learning, recommendation systems, classification, regression, and statistical analysis** into a single retail analytics pipeline.

---

# 🎯 Business Problem

Retail companies generate millions of customer transactions, but historical transaction data alone does not directly answer important business questions.

This project focuses on four practical questions:

| Business Question                                              | Analytical Approach      |
| -------------------------------------------------------------- | ------------------------ |
| Which customers have similar purchasing behavior?              | RFM + K-Means            |
| Which products should be recommended to a customer?            | SVD Matrix Factorization |
| Which customers are at risk of becoming inactive?              | XGBoost Classification   |
| What can historical sales patterns tell us about future sales? | Random Forest Regression |

---

# 📂 Dataset

The project uses the **H&M Personalized Fashion Recommendations** dataset from Kaggle.

The dataset contains information related to:

* Customer transactions
* Customer information
* Product/article information

The project works with approximately:

* **15M+ historical transactions**
* **1.3M+ customers**

> Raw CSV files and the local SQLite database are not included in the repository because of their large file size.

### Dataset Source

**H&M Personalized Fashion Recommendations**

---

# 🎯 Project Objectives

### Customer Analytics

* Understand customer purchasing behavior
* Create meaningful customer segments
* Identify high-value and inactive customer groups

### Recommendation System

* Learn customer-product interaction patterns
* Generate personalized product recommendations
* Evaluate recommendation performance

### Customer Retention

* Define a 90-day churn window
* Identify behavioral patterns associated with churn
* Build a predictive churn classification model

### Sales Analytics

* Analyze historical revenue patterns
* Create temporal and lag-based features
* Forecast future sales

---

# 🔄 Project Workflow

```text
Raw H&M Dataset
       │
       ▼
Data Extraction & SQLite Database
       │
       ▼
Data Cleaning & Preprocessing
       │
       ▼
Exploratory Data Analysis
       │
       ├──────────────┬──────────────┬──────────────┐
       ▼              ▼              ▼              ▼
      RFM          Customer-Item    Churn        Time-Series
   Analysis        Interactions   Features       Features
       │              │              │              │
       ▼              ▼              ▼              ▼
    K-Means           SVD          XGBoost      Random Forest
       │              │              │              │
       └──────────────┴──────────────┴──────────────┘
                              │
                              ▼
                    Business Insights
```

---

# 🔍 Key Analysis

## 1. 👥 Customer Segmentation

### Objective

Group customers according to their purchasing behavior.

### Methodology

Created **RFM features**:

* **Recency** → Days since the last purchase
* **Frequency** → Number of purchases
* **Monetary** → Total spending

The RFM features were then scaled and used as inputs for **K-Means clustering**.

### Customer Profiles

The resulting clusters were analyzed to identify behavioral profiles such as:

* VIP / high-value customers
* Frequent active shoppers
* Occasional shoppers
* Lapsed customers

### Business Value

Customer segmentation can support:

* Targeted marketing campaigns
* Customer retention
* Personalized offers
* High-value customer identification

---

## 2. 🎯 Recommendation System

### Objective

Generate personalized product recommendations based on historical customer-product interactions.

### Methodology

The recommendation engine uses:

**SVD Matrix Factorization**

implemented using the `scikit-surprise` library.

The model learns latent relationships between customers and products from historical interactions.

### Output

The system generates **12 personalized product recommendations** for a selected customer.

### Model Performance

**RMSE: 0.45**

### Business Value

The recommendation system can support:

* Personalized product discovery
* Cross-selling
* Product recommendations
* Customer engagement
* Long-tail product discovery

---

## 3. 🚨 Customer Churn Prediction

### Objective

Identify customers who are likely to become inactive based on their historical purchasing behavior.

### Churn Definition

A customer is considered churned when there is **no purchase activity for 90 days** according to the project definition.

### Methodology

```text
Customer Transactions
        ↓
Customer-Level Features
        ↓
90-Day Churn Label
        ↓
Class Imbalance Analysis
        ↓
SMOTE
        ↓
XGBoost Classifier
        ↓
Model Evaluation
```

### Model

**XGBoost Classifier**

### Business Value

The model can help identify customers who may require retention or re-engagement efforts.

Potential applications include:

* Retention campaigns
* Customer reactivation
* Targeted offers
* CRM prioritization

---

## 4. 📈 Sales Forecasting

### Objective

Forecast future sales using historical transaction patterns and time-based features.

### Feature Engineering

The forecasting dataset includes temporal features such as:

* 7-day lag
* 30-day lag
* Historical sales
* Time-based variables
* Rolling/temporal characteristics

### Statistical Analysis

Additional analysis was performed using:

* OLS Regression
* Variance Inflation Factor (VIF)
* Residual Analysis

### Model

**Random Forest Regressor**

### Model Performance

**RMSE: 113.74**

### Business Value

Forecasting can support:

* Inventory planning
* Warehouse operations
* Workforce planning
* Demand planning
* Sales planning

---

# 📌 Key Results

| Analysis              | Technique                | Result                       |
| --------------------- | ------------------------ | ---------------------------- |
| Customer Segmentation | RFM + K-Means            | Behavioral customer segments |
| Recommendation System | SVD Matrix Factorization | **RMSE: 0.45**               |
| Churn Prediction      | XGBoost + SMOTE          | 90-day churn classification  |
| Sales Forecasting     | Random Forest Regression | **RMSE: 113.74**             |

---

# 🛠️ Technologies Used

| Category              | Technologies          |
| --------------------- | --------------------- |
| Programming           | Python                |
| Data Manipulation     | Pandas, NumPy         |
| Database              | SQLite                |
| Visualization         | Matplotlib, Seaborn   |
| Machine Learning      | Scikit-Learn, XGBoost |
| Recommendation System | Scikit-Surprise, SVD  |
| Statistical Analysis  | Statsmodels           |
| Development           | Jupyter Notebook      |
| Version Control       | Git, GitHub           |

---

# 📁 Project Structure

```text
Predictive-Retail-Analytics-HM/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_Data_Extraction.ipynb
│   ├── 02_Exploratory_Data_Analysis.ipynb
│   ├── 03_Customer_Segmentation.ipynb
│   ├── 04_Recommendation_System.ipynb
│   ├── 05_Churn_Prediction.ipynb
│   └── 06_Sales_Forecasting.ipynb
│
├── models/
│   ├── recommender_svd.pkl
│   └── sales_forecast_rf_tuned.pkl
│
├── images/
│   ├── customer_segments.png
│   ├── recommendation_analysis.png
│   ├── churn_analysis.png
│   └── sales_forecast.png
│
└── data/
    └── README.md
```

---

# 🚀 How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/Predictive-Retail-Analytics-HM.git

cd Predictive-Retail-Analytics-HM
```

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Or:

```bash
pip install pandas numpy scikit-learn xgboost scikit-surprise statsmodels matplotlib seaborn
```

## 3. Download the Dataset

Download the H&M Personalized Fashion Recommendations dataset from Kaggle.

Place the required CSV files in the project data directory.

## 4. Run the Notebooks

Execute the notebooks in the following order:

```text
01_Data_Extraction.ipynb
        ↓
02_Exploratory_Data_Analysis.ipynb
        ↓
03_Customer_Segmentation.ipynb
        ↓
04_Recommendation_System.ipynb
        ↓
05_Churn_Prediction.ipynb
        ↓
06_Sales_Forecasting.ipynb
```

---

# 📊 Visualizations

The project includes visual analysis covering:

### Customer Segmentation

* RFM distributions
* Cluster characteristics
* Customer segment comparisons

### Recommendation System

* Recommendation performance
* Customer-product interactions
* Recommendation examples

### Churn Prediction

* Churn distribution
* Feature analysis
* Classification performance
* Confusion matrix

### Sales Forecasting

* Historical sales trends
* Actual vs predicted sales
* Residual analysis
* Forecast performance

Example:

```text
images/
├── customer_segments.png
├── recommendation_analysis.png
├── churn_analysis.png
└── sales_forecast.png
```

---

# 🔮 Future Improvements

* Deploy the recommendation system using Streamlit
* Build an interactive Power BI retail dashboard
* Develop Customer Lifetime Value (CLV) prediction
* Compare SVD with Neural Collaborative Filtering
* Experiment with LightFM and other recommendation algorithms
* Compare XGBoost with LightGBM and CatBoost
* Evaluate advanced time-series models
* Implement automated model retraining
* Containerize the project using Docker
* Deploy the pipeline to a cloud platform

---

# 👨‍💻 Author

### Shubham Patil

**Data Science & Analytics | Python | SQL | Machine Learning | Power BI**

This project demonstrates the application of machine learning and analytics techniques to a real-world retail use case, covering the complete journey from **transaction data to predictive insights**.

---

⭐ If you found this project useful, consider giving the repository a star.
