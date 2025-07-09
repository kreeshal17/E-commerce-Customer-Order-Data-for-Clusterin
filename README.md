# Customer Segmentation Using RFM Analysis and KMeans Clustering

## Overview

This project demonstrates how to perform customer segmentation on transactional data using **RFM (Recency, Frequency, Monetary) analysis** combined with **KMeans clustering**. The goal is to identify distinct customer groups based on their purchasing behavior to help businesses tailor marketing strategies and improve customer retention.

---

## Dataset

The dataset contains customer transaction records with fields such as:

- `CustomerID`: Unique identifier for each customer  
- `OrderDate`: Date of purchase  
- `OrderID`: Unique order number  
- `OrderAmount`: Purchase amount  
- `OrderStatus`, `PaymentMethod`, `City`, `State`: Additional categorical info  

> **Note:** The dataset is not included in this repo due to privacy. Please use your own transactional data or public datasets with similar structure.

---

## Features and Methodology

1. **RFM Feature Engineering**  
   - **Recency:** Days since last purchase (calculated from `OrderDate`)  
   - **Frequency:** Number of orders per customer  
   - **Monetary:** Total amount spent by each customer  

2. **Data Preprocessing**  
   - Handling missing values in categorical features (`OrderStatus`, `PaymentMethod`, `City`, `State`) by filling with mode.  
   - Encoding categorical variables using `LabelEncoder`.  
   - Scaling features using `StandardScaler` to normalize data before clustering.

3. **Clustering with KMeans**  
   - Applied the **Elbow Method** to select the optimal number of clusters by plotting Within-Cluster Sum of Squares (WCSS).  
   - Performed KMeans clustering with the chosen number of clusters (default: 5).  
   - Calculated **Silhouette Score** for cluster validation, measuring cluster cohesion and separation.

4. **Similarity Function**  
   - Defined a function to find similar customers based on **Euclidean Distance** in the scaled feature space, helping identify customers with similar buying patterns within the same cluster.

---

## Visualization

- Scatter plots showing clusters by frequency and total amount spent.  
- Bar plots summarizing average monetary value per cluster.  
- Heatmaps to explore correlation between RFM features.

---

Install required libraries:

bash
Copy
Edit
pip install pandas numpy scikit-learn matplotlib seaborn
Place your dataset CSV file in the project folder and update the path in the notebook or script.

Run the notebook or Python script to see the clustering results and visualizations.




Results & Insights
The clustering reveals meaningful segments like High Value Loyal Customers, At Risk Customers, and Potential Loyalists.

Visualization helps interpret customer distribution and spending patterns across clusters.

License
This project is open source and available under the MIT License.
