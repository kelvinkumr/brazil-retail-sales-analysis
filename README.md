# Olist E-Commerce Data Analysis

## ⚠️ Status
Currently being reworked as there was an error within the original dataset provided.
**Dataset Sourced From:** [Kaggle Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

---

## 🎯 Project Goal
The primary goal of this project was to perform a comprehensive exploratory data analysis (EDA) and feature engineering on the Olist E-Commerce dataset (Brazilian public data). The analysis focused on identifying key business drivers, operational bottlenecks, and customer satisfaction factors across transactions, products, sellers, and logistics.

## 💾 Dataset Overview
The project uses the publicly available Olist dataset, comprising 8 files related to ~100k orders placed between 2016 and 2018.

Key datasets used:
* `olist_orders_dataset.csv`: Core order status and timestamps.
* `olist_order_items_dataset.csv`: Item details (price, freight, product/seller IDs).
* `olist_products_dataset.csv` & `product_category_name_translation.csv`: Product categories and attributes.
* `olist_order_reviews_dataset.csv`: Customer satisfaction scores.
* `olist_sellers_dataset.csv`: Seller location data.
* `olist_geolocation_dataset.csv`: Geolocation coordinates for ZIP codes.

---

## 🛠️ Key Steps Completed

### 1. Data Cleaning and Merging
* All core transaction and product datasets were merged into a single `master_df`.
* Product categories were translated from Portuguese to English.
* Date columns were converted to `datetime` objects.
* Rows with missing critical transaction data (e.g., `price`, `product_id`) were dropped to ensure transactional integrity.
* Missing product features (e.g., length, weight) were imputed with zero.

### 2. Feature Engineering (Metrics Creation)
Several new, high-value metrics were calculated for analysis:
* **`delivery_time_days`**: Actual time between purchase and delivery.
* **`shipping_delta_days`**: Difference between actual and estimated delivery date (Negative = early delivery).
* **`distance_km`**: Geodesic distance between seller and customer, calculated using the Haversine formula. 

### 3. Merging Reviews, Sellers, and Geolocation
* Review scores were merged by `order_id`.
* Seller location data was merged by `seller_id`.
* Customer and Seller coordinates were aggregated from the `geolocation_dataset` and merged into the `master_df` for distance calculation.

---

## 📈 Key Findings & Insights

### 1. Overall Trends and Categories
* **Revenue Trend:** [Describe the key trend from your monthly sales chart—e.g., "Sales show a strong seasonal peak around November/December of 2017, followed by a decline."]
* **Top Categories:** The top revenue-generating categories are typically **[Insert your top 3 categories from Visualization B, e.g., 'Health & Beauty', 'Bed Bath & Table', 'Sports & Leisure']**.

### 2. Customer Satisfaction
* The overall satisfaction is high, with over **74%** of orders receiving a 4 or 5-star rating.
* **Top Rated Categories:** Categories like **[Insert one or two highly-rated categories from your chart, e.g., 'Books - Imported' and 'Food & Drink']** consistently achieve the highest average review scores, indicating strong product quality or service in those segments.

### 3. Seller Performance
* **Geographic Concentration:** Seller activity is heavily concentrated in the state of **SP (São Paulo)**, which dominates the total revenue.
* **Revenue Skew:** Revenue is highly skewed, with the top individual sellers contributing a disproportionately large share of total sales.

### 4. Geospatial Logistics
* **Distance Calculation:** The **`distance_km`** metric was successfully calculated for almost all orders, enabling logistical analysis.
* **Delivery Time Impact:** [Insert a brief summary of your Delivery Time vs. Distance finding—e.g., "Delivery time increases linearly with distance, demonstrating significant logistical challenge for inter-state orders (>1000km)."]

---

## 🚀 How to Replicate the Analysis
1.  **Dependencies:** Ensure you have Python 3.x and the following libraries installed:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
2.  **Data:** Place all Olist CSV files (8 total) in the same directory as the notebook/script.
3.  **Execution:** Run the Jupyter Notebook sequentially from the start. The code is designed to rebuild the final cleaned `master_df` and generate all visualizations in order.
