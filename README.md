# customer segmentation using rfm analysis, kmeans clustering & excel insights

## overview

this project demonstrates how to perform **customer segmentation** on transactional data by combining:

- **rfm (recency, frequency, monetary) analysis with kmeans clustering** in python to discover distinct customer groups based on purchasing behavior.
- **exploratory data analysis and insights using excel and power query**, including pivot tables, slicers, and charts to understand sales trends by time, location, and order status.

the combined approach helps businesses tailor marketing strategies and improve customer retention by identifying meaningful customer segments and visualizing key transactional patterns.

---

## dataset

the dataset contains customer transaction records with fields such as:

- `customerid`: unique customer identifier  
- `orderdate`: date of purchase  
- `orderid`: unique order number  
- `orderamount`: purchase amount  
- `orderstatus`, `paymentmethod`, `city`, `state`: additional categorical info  

> **note:** due to privacy, the dataset is not included here. use your own transactional data or a public dataset with similar structure.

---

## features and methodology

### 1. rfm feature engineering (python)

- **recency:** days since last purchase (calculated from `orderdate`)  
- **frequency:** number of orders per customer  
- **monetary:** total amount spent per customer  

### 2. data preprocessing (python)

- handle missing values in categorical columns (`orderstatus`, `paymentmethod`, `city`, `state`) by filling with the mode.  
- encode categorical variables using `labelencoder`.  
- scale features with `standardscaler` for normalization before clustering.

### 3. clustering with kmeans (python)

- use the **elbow method** to determine the optimal number of clusters by plotting within-cluster sum of squares (wcss).  
- apply kmeans clustering (default: 5 clusters).  
- validate clustering quality using the **silhouette score**.  

### 4. similarity function (python)

- find similar customers based on euclidean distance in scaled rfm feature space to identify customers with similar purchasing behavior within clusters.

---

## excel & power query insights

to complement python analysis, detailed exploratory data analysis was performed in excel:

- extracted **day** and **month** from the `orderdate` using power query transformations for time-based analysis.  
- filled missing or unknown values in categorical fields with "unknown" to maintain data integrity.  
- created **pivot tables** to summarize key metrics:
  - sum of `orderamount` by **state** and **payment method**.  
  - count of orders and sum of `orderamount` by **month**.  
  - count of orders by **order status** (e.g., cancelled, delivered).  
- added **slicers** in excel to filter data interactively by months, states, and order statuses for dynamic exploration.  
- developed **visualizations** such as pie charts, histograms, and bar graphs to visually represent distribution of sales, payment methods, and order outcomes.

---

## visualizations (python)

- scatter plots visualizing clusters by frequency and monetary values.  
- bar plots summarizing average monetary value per cluster.  
- heatmaps to explore correlations between rfm features.

---

## installation

install the required python libraries 
pip install pandas numpy scikit-learn matplotlib seaborn like this



usage
place your dataset csv in the project folder and update the file path in the python script or notebook.

run the script/notebook to perform rfm analysis, clustering, and generate visualizations.

open the provided excel workbook (if available) to explore pivot tables, slicers, and charts.

results & insights
the clustering reveals meaningful customer segments such as high value loyal customers, at risk customers, and potential loyalists.

excel pivot tables and charts help validate and understand sales distribution and customer behavior by time, location, payment method, and order status.

combining python clustering with excel insights provides a comprehensive view for data-driven marketing strategies.

license
this project is open source and available under the mit license.
   
