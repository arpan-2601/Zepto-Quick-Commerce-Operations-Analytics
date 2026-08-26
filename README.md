# Zepto-Quick-Commerce-Operations-Analytics

📌 Project Overview

This project presents an end-to-end data analytics solution built on Zepto's quick-commerce delivery operations. Starting from raw, uncleaned order data, the project covers the complete analytics pipeline — data cleaning in Python, exploratory analysis, feature engineering, and finally a fully interactive 4-page Power BI dashboard with 17+ DAX measures and role-based access control.

The core business problem addressed: which warehouse hubs are underperforming, and what operational factors — delivery delays, cancellations, surge pricing, or low ratings — are driving poor customer experience?

🧹 Data Cleaning & Preprocessing (Python)

File: zepto.ipynb

The raw dataset contained missing values, outliers, and unstructured categorical fields. The following steps were performed using Pandas and NumPy:

Handled missing values across 21 columns using median imputation for numerical fields

Detected and treated outliers in Delivery_Time, Distance_km, and Order_Value

Engineered new features:

Delivery_Efficiency — Distance covered per minute (km/min)

Late_Delivery — Binary flag (1 if delivery time exceeded 20 minutes)

Cancelled — Binary flag derived from Order_Status

Order_Size — Categorized orders as Low, Medium, or High based on Order_Value

Distance_Category — Bucketed distances into Near (0–5 km), Medium (5–10 km), Far (10–20 km)

Standardized categorical columns: Time_Slot, Warehouse_Location, Payment_Method

Final cleaned dataset: 204 rows × 21 columns exported as zepto_cleaned.csv

📊 Power BI Dashboard

File: zeptopbi.pbix

Built a 4-page interactive dashboard in Power BI Desktop using the cleaned CSV. All metrics are dynamic — every visual responds to 7 synchronized slicers across all pages.


Dashboard Features

✅ 7 synchronized slicers (Time Slot, Warehouse, Payment Method, Order Status, Distance, Order Size, Surge)

✅ Cross-page filter sync via Power BI Sync Slicers

✅ Conditional formatting — heat-map matrix, gradient bar charts, color-coded KPI cards

✅ Custom tooltip page with 4 KPIs on warehouse hover

✅ Row-Level Security (RLS) — warehouse-specific access roles

✅ Custom Zepto purple brand theme applied across all pages

✅ Reset Filters bookmark button on every page


📈 Key Metrics Tracked

Category	Metrics

Delivery Performance	Avg Delivery Time, Late Delivery Rate %, Delivery Efficiency

Revenue & Orders	Total Revenue, Avg Order Value, % High-Value Orders

Customer Experience	Avg Customer Rating, Avg Rider Rating, Combined CX Score

Operations	Cancellation Rate %, Surge Rate %, Revenue Rank by Warehouse


🛠 Tools & Technologies

Python - (Pandas, NumPy)	Data cleaning, feature engineering

Jupyter Notebook	- Analysis environment

Power BI Desktop	- Dashboard design & DAX modelling

DAX	- KPI measures, calculated columns, RLS filters

Power BI Service	- Publishing, scheduled refresh, role-based sharing


💡 Key Insights

Which of the 5 warehouse hubs has the highest late delivery rate and lowest customer rating

Whether surge-priced orders have a higher cancellation rate than normal orders

How delivery time varies across Morning, Afternoon, Evening, and Late Night slots

Which payment method (UPI, Card, COD) correlates with higher order values

Revenue contribution by distance zone (Near, Medium, Far) across time slots
