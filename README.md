# 📊 Olist E-Commerce: End-to-End Business Intelligence Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data_Manipulation-list)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-orange)

## 📌 Project Overview
This project performs a deep-dive Exploratory Data Analysis (EDA) on the **Brazilian Olist E-Commerce dataset**. The goal was to transform raw, fragmented relational data into actionable business insights regarding sales trends, customer satisfaction, and logistical performance.

**Status:** ✨ Completed Analysis (Currently documenting dataset error resolutions).
**Data Source:** [Kaggle - Olist Brazilian E-Commerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

---

## 🛠️ Tech Stack & Skills
* **Language:** Python 3.12
* **Libraries:** `Pandas` (Data Wrangling), `NumPy` (Vectorized Math), `Matplotlib` & `Seaborn` (Data Viz).
* **Key Techniques:** Relational Data Merging (Left Joins), Feature Engineering, Geospatial Analysis (Haversine Formula), Data Imputation.

---

## 📈 Executive Summary of Insights

### 1. Sales & Revenue Growth
* **Trend:** Observed a significant upward trajectory throughout 2017, peaking during **Black Friday (November)**. 
* **Performance:** Revenue is heavily concentrated in the **Health & Beauty** and **Watches & Gifts** categories.

### 2. Customer Satisfaction (The "4-Star Threshold")
* **Distribution:** Over **74%** of customers provided 4 or 5-star reviews.
* **High Performers:** Niche categories like **Books (Imported)** and **Food & Drink** maintain the highest average scores (>4.5), indicating high product-market fit.

### 3. Logistical Challenges (Geospatial Analysis)
* **The Distance Gap:** Shipping distance is a major bottleneck. Orders traveling >2,000km average **35+ days** for delivery.
* **Resilience:** Interestingly, customer satisfaction (Review Scores) remains stable even as distance increases, suggesting that Olist successfully manages customer expectations regarding long-haul shipping times.

---

## 🏗️ Data Engineering Pipeline

### Step 1: Standardizing the Foundation
* Converted 5+ string-based timestamp columns into Python `datetime` objects for time-series analysis.
* Translated 70+ product categories from Portuguese to English using a mapping file and a **Left Join** to ensure no product data was lost during translation.

### Step 2: Relational Data Merging
Built a "Master DataFrame" by linking disparate tables through a central bridge:
1.  **Orders** → Joined with **Items** on `order_id`.
2.  **Items** → Joined with **Products** on `product_id`.
* *Result:* A unified dataset containing price, timestamps, product attributes, and customer locations.

### Step 3: Feature Engineering
Calculated custom business metrics that were not in the original data:
* `delivery_time_days`: Speed of fulfillment.
* `shipping_delta_days`: Accuracy of estimated delivery.


---

## 🚀 How to Run
1. Clone this repository.
2. Download the CSV files from the Kaggle link above.
3. Run the `analysis_notebook.ipynb` sequentially.
