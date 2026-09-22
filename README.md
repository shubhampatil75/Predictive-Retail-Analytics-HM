# 🛍️ Predictive Retail Analytics: H&M

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![SQL](https://img.shields.io/badge/SQL-Data%20Engineering-orange.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-Churn%20Prediction-red.svg)
![Scikit-Surprise](https://img.shields.io/badge/Scikit--Surprise-Recommendation-purple.svg)

### An end-to-end retail analytics and machine learning project built on H&M transaction data to analyze customer behavior, generate personalized recommendations, predict customer churn, and forecast sales.

---

## 📌 Project Overview

Retail transaction data contains valuable information about customer purchasing behavior, product preferences, retention patterns, and sales trends.

This project transforms large-scale H&M transaction data into actionable insights using a combination of:

- SQL data processing
- Exploratory Data Analysis
- Customer segmentation
- Recommendation systems
- Classification
- Imbalanced learning
- Time-series feature engineering
- Statistical analysis
- Predictive modeling

The project is organized into four major analytical components:

| Business Problem | Solution |
|---|---|
| Who are our different customer groups? | RFM Analysis + K-Means |
| Which products should be recommended? | SVD Recommendation System |
| Which customers are at risk of churn? | XGBoost Classification |
| What will future sales look like? | Random Forest Forecasting |

---

# 🎯 Business Objectives

The project focuses on four key retail business questions:

### 1. Customer Segmentation
Identify customer groups based on purchasing behavior and spending patterns.

### 2. Personalized Recommendations
Develop a recommendation system that suggests relevant products to individual customers.

### 3. Customer Churn Prediction
Identify customers who may become inactive based on their historical purchasing behavior.

### 4. Sales Forecasting
Use historical sales patterns and temporal features to predict future sales.

---

# 🔄 Project Workflow

```text
                H&M Transaction Data
                         │
                         ▼
               SQL Data Loading
                         │
                         ▼
             Data Cleaning & Preparation
                         │
                         ▼
               EDA & Visualization
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   Customer          Customer-Item     Time-Series
   Analytics         Interactions      Analysis
        │                │                │
        ▼                ▼                ▼
   RFM Analysis          SVD          Lag Features
        │                │                │
        ▼                ▼                ▼
    K-Means         Recommendations  Sales Forecast
        │                │                │
        └────────────────┼────────────────┘
                         │
                         ▼
                 Business Insights
```

---

# 📂 Dataset

The project uses transaction data based on the **H&M Personalized Fashion Recommendations** dataset.

The project dataset has been prepared and uploaded to **Kaggle** for reproducibility and easier access.

The dataset contains information related to:

- Customer transactions
- Customer identifiers
- Product/article information
- Transaction dates
- Product attributes

> Raw data files are not stored directly in this GitHub repository because of their large size.

### Dataset

🔗 **Kaggle Dataset:**  
`https://www.kaggle.com/datasets/shubhampatil75/h-and-m-personalized-fashion-recommendations/data`

---

# 📊 Dataset Scale

The project works with approximately:

- **15M+ transactions**
- **1.3M+ customers**
- Large-scale customer-product interactions

The data is processed using SQL and Python before being used for machine learning workflows.

---

# 🔍 Analysis & Machine Learning

## 1️⃣ Customer Segmentation

### Objective

Identify distinct customer groups based on purchasing behavior.

### Methodology

Customer-level RFM features were created:

- **Recency**: Time since the customer's latest purchase
- **Frequency**: Number of purchases
- **Monetary**: Total spending

The resulting RFM features were prepared and scaled before applying **K-Means clustering**.

### Customer Segments

The resulting clusters are analyzed based on:

- Customer activity
- Purchase frequency
- Spending behavior
- Recency
- Overall customer value

This allows customers to be grouped into meaningful behavioral segments such as:

- High-value customers
- Frequent active customers
- Occasional shoppers
- Lapsed customers

### Business Applications

Customer segmentation can support:

- Targeted marketing
- Customer retention
- Personalized campaigns
- High-value customer identification
- Customer lifecycle analysis

---

## 2️⃣ Recommendation System

### Objective

Build a personalized product recommendation system using historical customer-product interactions.

### Methodology

The recommendation engine uses:

**Singular Value Decomposition (SVD)**

implemented using the `scikit-surprise` library.

The model learns latent relationships between customers and products from historical interactions.

### Output

The system generates **12 personalized product recommendations** for a selected customer.

### Model Performance

**RMSE: 0.45**

### Business Applications

The recommendation system can support:

- Personalized product discovery
- Cross-selling
- Product recommendations
- Customer engagement
- Long-tail product discovery

---

## 3️⃣ Customer Churn Prediction

### Objective

Predict customers who are at risk of becoming inactive based on their historical purchasing behavior.

### Churn Definition

The project defines churn using a **90-day inactivity window**.

Customer-level behavioral features are created and used to train a classification model.

### Methodology

```text
Transaction Data
       ↓
Customer-Level Aggregation
       ↓
Feature Engineering
       ↓
90-Day Churn Definition
       ↓
Class Imbalance Analysis
       ↓
SMOTE
       ↓
XGBoost
       ↓
Model Evaluation
```

### Models & Techniques

- XGBoost Classification
- SMOTE
- Feature Engineering
- Classification Metrics
- Confusion Matrix Analysis

### Business Applications

The churn model can help businesses:

- Identify at-risk customers
- Prioritize retention campaigns
- Target re-engagement offers
- Monitor customer activity
- Improve customer retention strategies

---

## 4️⃣ Advanced Churn Analysis

The advanced churn notebook extends the initial churn modeling workflow with additional analysis and model evaluation.

This stage focuses on improving the predictive workflow through:

- Additional feature analysis
- Model experimentation
- Performance evaluation
- Threshold analysis
- Business interpretation

The advanced workflow is designed to evaluate the model beyond a single accuracy metric and focus on identifying customers who are relevant from a retention perspective.

---

## 5️⃣ Sales Forecasting

### Objective

Forecast future sales using historical transaction patterns and time-based features.

### Feature Engineering

The forecasting workflow includes temporal features such as:

- 7-day lag
- 30-day lag
- Historical sales
- Time-based variables
- Rolling/temporal features

### Statistical Analysis

The project also applies:

- OLS Regression
- Variance Inflation Factor (VIF)
- Residual Analysis

### Model

**Random Forest Regressor**

### Model Performance

**RMSE: 113.74**

### Business Applications

Sales forecasting can support:

- Demand planning
- Inventory planning
- Warehouse operations
- Workforce scheduling
- Sales planning

---

# 📌 Key Results

| Component | Technique | Result |
|---|---|---|
| Customer Segmentation | RFM + K-Means | Behavioral customer segments |
| Recommendation System | SVD Matrix Factorization | **RMSE: 0.45** |
| Churn Prediction | XGBoost + SMOTE | 90-day churn prediction |
| Sales Forecasting | Random Forest Regression | **RMSE: 113.74** |

> Model performance should be interpreted together with the corresponding dataset, feature engineering approach, validation methodology, and business objective.

---

# 🛠️ Technologies Used

### Programming & Data Processing

- Python
- Pandas
- NumPy

### Database

- SQL
- SQLite

### Data Visualization

- Matplotlib
- Seaborn

### Machine Learning

- Scikit-Learn
- XGBoost

### Recommendation Systems

- Scikit-Surprise
- SVD Matrix Factorization

### Statistical Analysis

- Statsmodels
- OLS Regression
- VIF
- Residual Analysis

### Development

- Jupyter Notebook
- Git
- GitHub
- Kaggle

---

# 📁 Project Structure

```text
Predictive-Retail-Analytics-HM/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   │
│   ├── 01_SQL_Data_Loading.ipynb
│   │
│   ├── 02_EDA_Visualizations.ipynb
│   │
│   ├── 03_Customer_Segmentation.ipynb
│   │
│   ├── 04_Recommendation_System.ipynb
│   │
│   ├── 05_Churn_Prediction.ipynb
│   │
│   └── 06_Sales_Forecasting.ipynb
│
├── models/
│   ├── recommender_svd.pkl
│   └── sales_forecast_rf_tuned.pkl
│
├── images/
│   ├── customer_segmentation.png
│   ├── recommendation_system.png
│   ├── churn_prediction.png
│   └── sales_forecasting.png
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

## 3. Download the Project Dataset

The prepared project dataset is available through Kaggle.

Download the required data files and place them in the appropriate project directory.

**Kaggle Dataset:**  
`ADD-YOUR-KAGGLE-DATASET-LINK-HERE`

## 4. Execute the Notebooks

Run the notebooks in the following sequence:

```text
01_SQL_Data_Loading
        ↓
02_EDA_Visualizations
        ↓
03_Customer_Segmentation
        ↓
04_Recommendation_System
        ↓
05_Churn_Prediction
        ↓
05_Churn_Prediction_Advanced
        ↓
06_Sales_Forecasting
```

---

# 📈 Visualizations

The project includes visual analysis for:

### Customer Segmentation

- RFM distributions
- Cluster analysis
- Customer segment comparisons

### Recommendation System

- Customer-product interactions
- Recommendation analysis
- Model evaluation

### Churn Prediction

- Churn distribution
- Feature analysis
- Confusion matrix
- Model performance

### Sales Forecasting

- Historical sales trends
- Actual vs predicted sales
- Residual analysis
- Forecast performance

---

# 🔮 Future Improvements

Potential extensions include:

- Deploying the recommendation system using Streamlit
- Building an interactive Power BI dashboard
- Developing Customer Lifetime Value prediction
- Comparing SVD with other recommendation algorithms
- Experimenting with LightFM and Neural Collaborative Filtering
- Comparing XGBoost with LightGBM and CatBoost
- Evaluating advanced time-series models
- Implementing automated model retraining
- Containerizing the project using Docker
- Deploying the complete solution to a cloud platform

---

# 💡 Key Learning Outcomes

This project provided practical experience in:

- Large-scale transaction data processing
- SQL-based data loading
- Exploratory Data Analysis
- Feature engineering
- RFM analysis
- Customer segmentation
- K-Means clustering
- Recommendation systems
- Matrix factorization
- Classification
- Imbalanced learning
- SMOTE
- Churn prediction
- Time-series feature engineering
- Regression
- Statistical analysis
- Model evaluation
- Business-oriented interpretation

---

# 👨‍💻 Author

## Shubham Patil

**Data Science & Analytics | Python | SQL | Machine Learning | Power BI**

This project demonstrates the application of data analytics and machine learning techniques to a large-scale retail use case, covering the journey from **raw transaction data to predictive business insights**.

---

⭐ If you found this project useful, consider giving the repository a star.
