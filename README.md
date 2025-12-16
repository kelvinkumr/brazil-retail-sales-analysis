# Currently being reworked as there was an error within the original dataset provided

# Dataset sourced from here: [Kaggle Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

# Olist E-Commerce Data Analysis

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


## 🛠️ Key Steps Completed

### 1. Data Merging and Translation
* All core transaction and product datasets were merged into a single `master_df`.
* Product categories were translated from Portuguese to English using the `product_category_name_translation.csv` file.

### 2. Data Cleaning and Imputation
* Date columns were converted to `datetime` objects.
* Rows with missing critical data (e.g., `price`, `product_id`) were dropped to ensure transactional integrity.
* Missing product features (e.g., length, weight) were imputed with zero.
* The `master_df` was verified for completeness, leaving only expected missing values in delivery dates (for orders not yet delivered/canceled).

### 3. Feature Engineering (Metrics Creation)
Several new, high-value metrics were calculated for analysis:
* **`delivery_time_days`**: Actual time between purchase and delivery.
* **`shipping_delta_days`**: Difference between actual and estimated delivery date (Negative = early delivery).
* **`order_month_year`**: For time-series analysis.
* **`distance_km`**: Geodesic distance between seller and customer using the Haversine formula (calculated during the Geospatial Analysis).




