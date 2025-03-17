# Optimizing Craft Beer Production and Sales: A Big Data Analysis Project

**Project Title:**  
Optimizing Craft Beer Production and Sales: Analyzing Factors Affecting Quality, Efficiency, and Alcohol Content

**Authors:**  
Charan Kumar Pathakamuri, Srinivasan Lakkala, Sherin Feno Kumaresan

---

## Problem Statement
The objective of this project is to uncover actionable insights to improve the brewing process, optimize resource utilization, enhance product quality, and maximize profitability. In addition to exploring market trends, the project aims to build a predictive model for estimating quality and providing manufacturers with data-driven recommendations.

---

## Data Overview
- **Source:** The dataset was taken from Kaggle.  
- **Size:** Approximately 2.4 GB (9,545,009 x 20).  
- **Link:** [Brewery Operations and Market Analysis Dataset](https://www.kaggle.com/datasets)  
- **Columns:**  
  - Batch_ID, Brew_Date, Beer_Style, SKU, Location, Fermentation_Time, Temperature, PH_Level, Gravity, Alcohol_Content, Bitterness, Color, Ingredient_Ratio, Volume_Produced, Total_Sales, Quality_Score, Brewhouse_Efficiency, Loss_During_Brewing, Loss_During_Fermentation, Loss_During_Bottling_Kegging.

---

## Project Execution Overview

### 1. Data Loading
- **Environment:** Apache Spark on Databricks.
- **Files:** Multiple CSV files (df1.csv to df10.csv) stored in DBFS are loaded using a defined schema.
- **Union:** The datasets are unioned to create a single comprehensive DataFrame for analysis.

### 2. Data Cleanup & Preprocessing
- **Handling Nulls:** Null values are identified and dropped or imputed as needed.
- **Feature Extraction:**  
  - Date components are extracted from `Brew_Date` (e.g., Day_of_Week and Hour).  
  - New features such as **Alcohol_to_Bitterness**, **Ingredient_Efficiency**, **SKU_Location**, **Total_Loss**, **Loss_Percentage**, **Quality_Category**, and **Sales_Efficiency** are engineered.
  
### 3. Exploratory Data Analysis (EDA)
- **Descriptive Statistics:** Summary statistics and aggregations by Beer Style, Day_of_Week, and Location.
- **Trend Analysis:**  
  - Analysis of total sales by packaging type and location.
  - Identification of trends such as Ale being the most sold beer style, despite its low efficiency.
  - Analysis of production losses and bitterness levels to guide manufacturing adjustments.

### 4. Predictive Modeling
- **Objective:** Build a model to estimate quality and forecast key production parameters.
- **Models Explored:**  
  - **Logistic Regression:** For classification tasks (e.g., predicting quality categories).  
  - **Linear Regression:** For predicting continuous variables such as Alcohol Content.  
    - *Example Metrics:* Logistic Regression accuracy ≈ 0.5001, and Linear Regression RMSE ≈ 0.4241 on test data.
- **Pipeline:** A Spark ML Pipeline is constructed using StringIndexer, VectorAssembler, and a Decision Tree Classifier.

### 5. Network Analysis using PageRank
- **GraphFrames:** The SKU-Location network is built and analyzed using the PageRank algorithm to identify key hubs in the distribution network.

### 6. Correlation and Advanced Analytics
- **Correlation Analysis:**  
  - Correlation among brewing parameters is computed using Spark ML's Correlation module.
  - Visualizations such as heatmaps (with Seaborn and Matplotlib) highlight relationships between factors like Temperature, pH_Level, and Quality_Score.
- **Market Insights:**  
  - Analysis revealed that in December 2021, alcohol sales dropped due to COVID-19 impacts.
  - Trends indicate that while Ale is the most popular style, it has the lowest brewhouse efficiency—prompting the need for innovative manufacturing methods.
  - Additional insights include variations in bitterness levels and their correlation with sales.

---

## Tools and Technologies
- **Apache Spark & PySpark:** For large-scale data processing.
- **Databricks:** Cloud-based analytics platform.
- **GraphFrames:** For network analysis using PageRank.
- **Python:** Core programming language.
- **Visualization:** Matplotlib, Seaborn.
- **Machine Learning:** Spark ML Pipelines.

---

## How to Run the Project
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/SHERIN_FENO/Optimizing Craft Beer Production and Sales.ipynb
