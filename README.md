# Customer Segmentation Using RFM and K-Means Clustering

This project segments customers from an e-commerce dataset based on purchasing behaviour using RFM analysis and unsupervised machine learning. It aims to support data-driven business decisions by identifying behavioral customer profiles.

---

## Objective

- To apply RFM modeling and clustering to identify distinct customer segments.
- To provide interpretable insights for business action, such as customer retention, reactivation, or value maximization.

---

## Dataset Summary

The analysis is based on the **Olist Brazilian E-Commerce public dataset**, which contains transactional records.

**Key Features Processed:**
* `Recency`: days since last purchase
* `Frequency`: number of orders
* `Monetary`: total value paid

## Data Cleaning & Preparation

The following key steps were performed to ensure data quality and readiness for analysis:

-   **Data Sources**: The project utilized `olist_orders_dataset.csv`, `olist_customers_dataset.csv`, `olist_order_items_dataset.csv`, and `olist_order_payments_dataset.csv` from the Olist Brazilian E-Commerce dataset.
-   **RFM Feature Engineering**: `Recency`, `Frequency`, and `Monetary` features were engineered and grouped by `customer_unique_id`.
-   **Preprocessing**:
    * Null values and duplicate records were removed.
    * Outliers were filtered (99th percentile, non-positive values).
    * Log transformation was applied to `Frequency` and `Monetary` to reduce skewness.
    * `StandardScaler` was applied to RFM values.

---

## Exploratory Data Analysis

### 1. **RFM Feature Engineering**
- `Recency`: days since last purchase
- `Frequency`: number of orders
- `Monetary`: total value paid
- Grouped by `customer_unique_id`

### 2. **Clustering**
- The K-Means algorithm from `sklearn` was used for clustering.
- The optimal K was determined via the Elbow Method and Silhouette Score (with subsampling).
- Final segmentation was performed with K = 4.

### 3. **Key Visualizations**
- RFM distributions and boxplots
- Cluster boxplots per feature
- Heatmap of normalized cluster averages
- 2D scatterplot (Monetary vs Recency)

---

## Tools & Methods

-   **Python**: Used for data processing, RFM modeling, and clustering.
    -   `sklearn`: K-Means algorithm for clustering.
    -   `Seaborn`: Data visualization for consistency and clarity.
-   **Google Colab**: All analysis was conducted in this environment.

---

## Cluster Profiles (Summary)

The project identified four distinct customer segments based on their RFM patterns:

| Cluster | Recency ↑ | Frequency ↑ | Monetary ↑ | Profile                                 |
|---------|-----------|-------------|-------------|-----------------------------------|
| 0       | Low       | Very Low    | Very High   | **Recent Big Spenders, Infrequent**  |
| 1       | Low       | Very High   | Very High   | **High-Value Frequent Champions** |
| 2       | High      | Very Low    | Low         | **Long-Term Inactive / Lost Customers** |
| 3       | Very Low  | Very Low    | Very Low    | **New/Recent Low Spenders** |

---

## Repository Structure

<pre><code>
rfm-kmeans-segmentation/
│
├── notebook/
│   └── clustering_rfm_kmeans.ipynb
│
├── data/
│   ├── olist_orders_dataset.csv
│   ├── olist_customers_dataset.csv
│   ├── olist_order_items_dataset.csv
│   └── olist_order_payments_dataset.csv
│
├── output/
│   └── rfm_customer_segments.csv
│
├── assets/
│   ├── boxplot.png
│   ├── heatmap.png
│   └── scatter.png
│
└──  README.md
</code></pre>

---

## Key Insights

-   Distinct customer segments were identified using RFM modeling and K-Means clustering, providing interpretable insights for business actions.
-   The project successfully applied advanced data preprocessing techniques, including outlier filtering and transformations, to prepare the data for robust analysis.
-   Visualizations confirmed the effectiveness of the clustering by illustrating clear patterns within each customer segment.

---

## Learnings & Reflection

This project significantly enhanced my skills in:

-   **RFM modelling and feature engineering**: Developing key metrics to understand customer behavior.
-   **Unsupervised machine learning (K-Means)**: Applying clustering algorithms to identify hidden patterns in data.
-   **Exploratory data analysis and visual storytelling**: Communicating complex analytical findings through clear visualizations.
-   **Customer analytics in an e-commerce context**: Translating data insights into actionable business strategies.

This project reinforces my ability to deliver comprehensive data solutions that bridge technical analysis with practical business needs.

---

## License

This project is for educational and demonstration purposes only.  
Dataset provided by Olist via Kaggle under public access.
