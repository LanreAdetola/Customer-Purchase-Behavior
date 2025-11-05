# 🧾 Customer Purchase Behavior Pipeline — Microsoft Fabric Project

A **Microsoft Fabric Data Engineering** project that simulates a real-world retail analytics pipeline — from data generation to Power BI visualization — all inside Fabric.

---

## 🚀 Project Overview

This project demonstrates an end-to-end **data pipeline** in **Microsoft Fabric**, designed to analyze **customer purchase behavior** and loyalty patterns.

### 🎯 Objectives
- Track and analyze customer purchases over time  
- Classify customers into segments: **Loyal**, **Occasional**, and **New**  
- Visualize spending trends and key KPIs in Power BI  

---

## 🧩 Architecture Overview

| Step | Tool | Purpose |
|------|------|----------|
| 1️⃣ | **Fabric Notebook (Python)** | Generate realistic customer and purchase data |
| 2️⃣ | **Lakehouse** | Store raw and processed data |
| 3️⃣ | **Dataflow Gen2** | Clean, transform, and merge data |
| 4️⃣ | **Lakehouse Table** | Create an analytics-ready table |
| 5️⃣ | **SQL Endpoint** | Query and validate results |
| 6️⃣ | **Power BI in Fabric** | Build and publish interactive dashboards |

---

## 📁 Project Structure

```
Customer Insights/
│
├── notebooks/
│   └── generate_data.ipynb         # Fabric notebook for data generation
│
├── data/
│   ├── customers.csv               # Synthetic customer data
│   ├── purchases.csv               # Synthetic purchase data
│
├── lakehouse/
│   └── customer_purchases          # Cleaned and merged data table
│
├── reports/
│   └── CustomerInsights.pbix       # Power BI report (created inside Fabric)
│
└── README.md
```

---

## 💻 Data Generation (Fabric Notebook)

The dataset is generated using the `Faker` library to simulate customer and purchase records.

```python
from faker import Faker
import pandas as pd
import random
from datetime import datetime, timedelta

fake = Faker()
NUM_CUSTOMERS = 500
NUM_PURCHASES = 5000
segments = ["Loyal", "Occasional", "New"]
segment_weights = [0.3, 0.5, 0.2]

# Generate customers and purchases...
# Save to customers.csv and purchases.csv
```

**Output:**
- 500 customers  
- 5,000 purchase transactions  

---

## 🧠 Data Transformation (Dataflow Gen2)

In **Microsoft Fabric Dataflow Gen2**:
1. Load `customers.csv` and `purchases.csv` from Lakehouse  
2. Clean column names and formats  
3. Merge on `CustomerID`  
4. Add calculated columns:  
   - `TotalSpend`  
   - `AveragePurchase`  
   - `RecencyDays`  
5. Output result as a **Lakehouse Table** named `customer_purchases`

---

## 📊 Visualization (Power BI in Fabric)

The final report connects directly to the **Lakehouse dataset** using Power BI inside Fabric.

### Suggested Visuals
- 💰 **Top 10 Loyal Customers by Spend** (bar chart)  
- 🌍 **Purchases by Region** (donut/map chart)  
- 🧍 **Customers by Segment** (pie chart)  
- 🗓️ **Average Spend Over Time** (line chart)  
- 🔢 **KPI Cards**: Total Revenue, Total Customers, Avg. Purchase  

---

## 🧠 Learnings

Through this project, I practiced:
- End-to-end data engineering in **Microsoft Fabric**
- Data cleaning and transformation with **Dataflows**
- Querying using the **Lakehouse SQL Endpoint**
- Building visual stories using **Power BI inside Fabric**

---

## 💡 Future Enhancements

- Automate refresh schedules using **Fabric Pipelines**  

---

## 🏁 Conclusion

This project shows how Microsoft Fabric unifies data engineering, analytics, and visualization in one environment.  
A perfect hands-on exercise for anyone exploring **Data Engineering and Analytics** in Fabric!

> 💬 *“Data storytelling begins with clean, connected, and well-visualized data.”*

---

### 🔗 Tags
`#MicrosoftFabric` `#DataEngineering` `#PowerBI` `#Lakehouse` `#Dataflow` `#SQL` `#Python` `#DataScienceStudent`
