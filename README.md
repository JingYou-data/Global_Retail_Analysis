# 📊 Global Online Retail Strategic Intelligence (2010–2011)
> **An end-to-end Data Analytics solution transforming 541K+ raw records into strategic business insights using Python and Power BI.**

---

## 🔗 Project Showcase
* **[🚀 Interactive Live Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZGE3NzBjZTUtZmNhOS00OTQwLTlmMGItNzU2MWYzMTQzOGJlIiwidCI6IjEwMWRhNTg3LTE4NDMtNGY1Mi04YjhhLTE3YjA2OWM2NmQzMyIsImMiOjJ9)**
* **🎥 Video Walkthrough:** Available in the `/Media` folder.

---

## 📌 Business Case
This project addresses the challenge of managing and analyzing large-scale international retail data. By leveraging a dataset of over **541,000 raw rows**, the solution provides executives with real-time tracking of revenue, seasonal trends, and regional market performance.

### **High-Level Impact (Post-Cleaning)**
* **Total Cleaned Revenue:** **$8.91 Million**.
* **Processed Transactions:** **397,884 verified rows** (after rigorous ETL).
* **Global Footprint:** Performance tracking across **30+ international markets** including UK, EIRE, and Hong Kong.

---

## 🛠️ The Technical Pipeline

### 1. Advanced ETL & Data Engineering (Python)
I developed a robust cleaning pipeline using **Pandas** to ensure 100% data integrity:
* **Missing Value Treatment:** Resolved **135,080 missing CustomerIDs** and **1,454 missing product descriptions**.
* **Anomaly Filtering:** Systematically removed records with non-positive quantities and unit prices (`Quantity > 0` & `UnitPrice > 0`) to eliminate returns and data errors.
* **Feature Engineering:** Created the `TotalAmount` metric to drive all financial reporting.

### 2. Multi-Dimensional Visual Analytics (Power BI)
The dashboard features a professional UI with five specialized analytical views:
* **Temporal Trends:** Discovered that **Autumn (Q4)** is the peak season, contributing **35.48% ($513.7K)** of revenue, with a massive surge in November.
* **Geospatial Intelligence:** Identified the **United Kingdom** as the primary hub, while recognizing **Hong Kong** and **EIRE** as high-value growth regions.
* **Pricing Strategy:** Benchmarked regional **Average Unit Prices ($7.76 global avg)** to identify premium market opportunities.
* **Product Insight:** Detailed analysis of top-performing items like the **"Regency Cakestand"** to guide inventory restocking.

---

## 📂 Repository Structure
```text
├── Data/                   # Raw Online_Retail.csv (1.45M rows) & Samples
├── Scripts/                # Python/Jupyter scripts for ETL (Online_Retail_powerbi.ipynb)
├── Media/                  # Dashboard screenshots & walkthrough video
└── README.md               # Professional project documentation
