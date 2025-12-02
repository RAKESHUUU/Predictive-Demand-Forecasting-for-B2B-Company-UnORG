# 🛒 UnORG Demand Forecasting & Inventory Planning
### General Championship Tech | Mid Prep Problem
**Predictive Supply Chain Solution for B2B Grocery Delivery**

---

### 📌 Project Overview
This project delivers a predictive framework for **UnORG** to forecast daily customer orders (SKUs and quantities) for a **14-day horizon**. The system optimizes inventory planning by minimizing stockouts and reducing waste through advanced time-series analysis and machine learning.

### ⚙️ Technical Architecture

#### 1. Data Processing & Engineering
* **Data Handling:** Zero-fill imputation for stockouts, calendar reindexing for time-series continuity, and Regex-based text normalization.
* **Outlier Detection:** SKU-level Z-score thresholding and IQR bounds.
* **Feature Engineering:**
    * **RFM Analysis:** Recency, Frequency, Monetary (extended to quantity/discounts).
    * **Temporal Features:** Day-of-week trends, monthly seasonality.
    * **Demand Segmentation:** Classification of SKUs into **Smooth**, **Intermittent**, or **Lumpy** demand.

#### 2. Modeling Strategy
We employed a hybrid approach based on demand variability:
* **Prophet:** For SKUs with regular, continuous demand patterns.
* **Croston’s Method:** For intermittent demand (sparse data/many zeros).
* **XGBoost / Random Forest:** For order probability and regression tasks.

#### 3. Inventory Planning Logic
* **Aggregation:** Consolidating predicted daily demand per customer across SKUs.
* **Safety Stock:** Applied a dynamic buffer (approx. 10%) to accommodate lead-time lags and service SLAs.
* **Output:** optimized stocking quantity = `Aggregated Demand + Safety Stock`.

---

### 📊 Key Results & Performance

| Metric | Customer Order Model | SKU-Level Forecast |
| :--- | :--- | :--- |
| **R² Score** | **0.9999** | **0.7529** |
| **MAE** | 0.0005 | - |
| **MAPE** | 0.12% | - |

**Business Insights:**
* **Top Customer:** Ramesh Hotel.
* **Peak Demand:** Mondays show maximum order volume; Sundays show minimum.
* **Seasonality:** Significant revenue surges observed during festivals (Diwali, Holi).

---

### 🛠️ Tech Stack
* **Language:** Python 🐍
* **Libraries:** Pandas, Scikit-learn, XGBoost, Prophet, Matplotlib/Seaborn.
* **Concepts:** Time Series Analysis, Regression, Classification, Inventory Optimization.

---

### 👨‍💻 Author
**Rakesh Reddy**
* 📧 Email: [alumolu_rr@me.iitr.ac.in](mailto:alumolu_rr@me.iitr.ac.in)
* 🏛️ **IIT Roorkee**

> *This project was developed for the General Championship Tech Mid Prep Problem organized by the Cultural Council.*
