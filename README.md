# Customer Segmentation Analysis: Identifying Distinct Customer Profiles Using K-Means Clustering

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

<!-- Text-based badges for specific libraries -->
![K-Means](https://img.shields.io/badge/K--Means-008080?style=for-the-badge)
![PCA](https://img.shields.io/badge/PCA-4B0082?style=for-the-badge)
![StandardScaler](https://img.shields.io/badge/StandardScaler-FF6B6B?style=for-the-badge)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)

## Project Overview
This project performs customer segmentation using K-Means clustering to identify distinct customer profiles from marketing data. The analysis includes data preprocessing, feature engineering, PCA for dimensionality reduction, and clustering interpretation.

## Business Objective
Identify meaningful customer segments to enable targeted marketing strategies, personalized campaigns, and improved customer retention.

## Methodology

### 1. Data Preprocessing
- **Data Cleaning**: Handled missing values in Income column, removed duplicates
- **Outlier Handling**: Identified and removed implausible values (e.g., $666,666 income with near-zero spending)
- **Categorical Encoding**: 
  - Ordinal encoding for Education (Undergraduate=0, Graduation=1, Master=2, PhD=3)
  - One-hot encoding for Marital_Status

### 2. Feature Engineering
Created new features to better capture customer behavior:
- **Demographic**: Age, Tenure_Years, Family_Size, Is_Parent
- **Behavioral**: Total_Spent, Total_Purchases, Total_Accepted_Cmp
- **Preference Ratios**: Wine_Ratio, Meat_Ratio, Gold_Ratio, Web_Purchase_Ratio, Catalog_Purchase_Ratio, Store_Purchase_Ratio

### 3. Multicollinearity Handling
- Removed highly correlated features using correlation matrix analysis
- Dropped redundant columns: AcceptedCmp1-5, Response, Total_Children

### 4. Dimensionality Reduction
- Applied PCA to reduce 20 features to 10 principal components
- Retained ~90% of variance while mitigating the curse of dimensionality

### 5. Clustering
- Used K-Means algorithm with optimal k=4 determined by Elbow Method and Silhouette Analysis
- Silhouette score: 0.215 indicating moderate but meaningful separation

## Customer Segments Identified
1. **Family Store Shoppers**: Middle-income, price-sensitive, in-store shoppers
2. **Catalog Connoisseurs**: High-income, catalog-preferring, high spenders
3. **Loyal Wine Enthusiasts**: Wine-focused, long-tenured, multichannel shoppers
4. **Young Budget Browsers**: Young, low-income, high browsing, low conversion

## Technologies Used
- **Platform**: Databricks
- **Languages**: Python
- **Libraries**: 
  - pandas, numpy
  - scikit-learn (KMeans, PCA, StandardScaler, silhouette_score)
  - matplotlib, seaborn
  - scipy.stats (gaussian_kde)

## Results
- 4 distinct customer segments with actionable marketing insights
- Moderate silhouette score (0.21) reflecting real-world behavioral overlap
- Clear business strategies for each segment (promotions, loyalty programs, etc.)

## How to Run

1. Import the `.ipynb` notebook into your Databricks workspace
2. Upload the dataset to DBFS or mount your storage
3. Update the file path in the first cell
4. Run all cells sequentially

