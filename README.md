#  Customer Segmentation & Analytics Dashboard

This project applies unsupervised learning to cluster customers based on RFM (Recency, Frequency, Monetary) metrics. It then visualizes these customer segments with an **interactive Power BI dashboard** to derive business insights like top-performing customers, dormant users, order trends, and regional behavior.

---

## 📊 Project Overview

The objective is to:
- Segment customers based on their purchasing behavior
- Use KMeans clustering for unsupervised classification
- Create a Power BI dashboard to visualize and interact with these segments
- Enable data-driven decision-making for targeted marketing, retention, and growth strategies

---

## 🧰 Tools & Technologies

###  Python Libraries:
- `pandas`, `numpy` – Data processing
- `scikit-learn` – Clustering & scaling
- `matplotlib`, `seaborn` – Data visualization

### 📈 Power BI:
Used for building a feature-rich interactive dashboard that presents customer and order insights.

---

## 📁 Dataset Summary

The dataset includes:
- **CustomerID, OrderID, OrderDate, OrderAmount**
- Categorical features: **OrderStatus, PaymentMethod, City, State**

---

## ⚙️ Preprocessing & Feature Engineering

1. **RFM Creation**:
   - `Recency`: Days since the last order
   - `Frequency`: Number of orders per customer
   - `Monetary`: Total amount spent

2. **Categorical Handling**:
   - Missing values filled using mode
   - `LabelEncoder` used to convert categories to numeric

3. **Scaling**:
   - `StandardScaler` applied for normalization

4. **Clustering**:
   - KMeans used for customer segmentation
   - Silhouette score used to determine optimal cluster count
   - Selected 5 clusters and mapped them to intuitive segment names

---

## 🧪 Segment Labels

| Cluster | Segment Name           | Description |
|--------|------------------------|-------------|
| 0      | Mid-Tier Loyal         | Average frequency and spend, consistent |
| 1      | High Value / Loyal     | Most frequent and highest spenders |
| 2      | At Risk / Dormant      | High recency (inactive recently), low frequency |
| 3      | Recent Regular         | Recently active with decent order count |
| 4      | Potential Loyalist     | Moderate spend, could be nurtured further |

---

## 🧬 Similar Customer Recommender

Using Euclidean distance and cluster membership, we find the top 5 customers who are most similar to any selected `CustomerID`:

python
similarcust(custid, rfm)
📊 Power BI Dashboard Description
The Power BI dashboard integrates the clustering output with transactional data to present a full view of customer and order behavior.

##  Key Features

- **Quarter-Based Slicer**: Allows users to filter the dashboard by **Q1–Q4**.
- **Payment Method Slicer**: View trends specific to **UPI**, **card**, **wallet**, etc.

###  Dynamic Tiles

- **Total number of unique customers**
- **Most frequent customer ID**

---

##  Charts & Visuals

| Chart | Description |
|-------|-------------|
| 📍 **Map - Sum of OrderAmount by City** | Geographic visualization showing top cities by revenue |
| 🏙️ **Bar Chart - Count of CustomerID by State** | Compares customer volume across Indian states |
| 📈 **Line Chart - Sum of OrderAmount by OrderDate** | Shows time-series trend of total order value |
| 📊 **Bar Chart - Customer Count by Cluster** | Number of customers in each segment |
| 🍩 **Donut Chart - Order Count by Segment** | Visual share of orders made by different segments |

All visuals dynamically respond to **slicers and filters** for granular analysis.

---

##  Python Visuals

- 📐 **Silhouette Plot**: Helps choose the optimal number of clusters.
- 🔵 **Scatter Plot**: Shows cluster separation based on `frequency` vs `totalamount`.
- 📊 **Bar Plot**: Displays average spend per cluster.
- 🔥 **Heatmap**: Visualizes correlation between features like recency, payment method, city, etc.


##  Business Insights

###  From Clustering

- **Cluster 1 – High Value / Loyal**: Customers with highest frequency and total spend. Critical for retention programs.
- **Cluster 2 – At Risk / Dormant**: Customers with long inactivity — ideal targets for re-engagement campaigns.
- **Cluster 4 – Potential Loyalist**: Middle-tier spenders — could be converted into loyal customers with personalized offers.
- **Cluster 3 – Recent Regular**: Recently active users — ensure satisfaction to keep them engaged.
- **Cluster 0 – Mid-Tier Loyal**: Stable and reliable customers with moderate frequency/spend.

---

### 📊From Power BI Dashboard

- **UPI dominates** as a payment method — suggests enhancing UPI integration and offering exclusive deals.
- **Order peaks during February–March 2025** — ideal window for promotional campaigns and sales.
- **Top revenue cities/states** can be prioritized for regional marketing and sales strategies.
- **Customer ID CUST1351** is the most frequent customer — a key candidate for loyalty programs or rewards.
- **Donut chart** shows that a few segments (Clusters 1 & 3) drive the majority of orders — a focused strategy can yield high ROI.

 ##  How to Use This Project

You can explore and run this customer segmentation project by following the steps below.

### 🖥️ Clone the Repository
```bash
git clone https://github.com/kreeshal17/E-commerce-Customer-Order-Data-for-Clusterin.git
cd E-commerce-Customer-Order-Data-for-Clusterin
```
 


###  Install Python Dependencies
Install all necessary libraries using the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### Make sure you are using Python 3.8 or higher.

 Run the Python Script
This will:

Clean and prepare the dataset

Generate RFM features

Cluster customers using KMeans

Assign segments

Recommend similar customers
```
bash

python segmentation.py
```

After running this, you’ll get:

- **A segmented dataset**
- **A few graphs plotted using matplotlib/seaborn**
- **The ability to recommend similar customers using:**

```py
similarcust(custid, rfm)
```

---

### Full example for README.md:

```yaml
## Power BI Dashboard Details

Below is the configuration info for the Power BI Dashboard:


power_bi_dashboard:
  file: dashboard.pbix
  application: Power BI Desktop
  filters:
    - Quarter slicer (Q1–Q4)
    - Payment Method slicer
  visuals:
    - City-wise revenue map
    - Customer count by state & cluster
    - Order trends over time
    - Segment-based donut chart
```



