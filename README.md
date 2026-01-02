# 📊 Global Online Retail Strategic Intelligence (2010–2011)
> **An end-to-end Data Analytics solution transforming 541K+ raw records into strategic business insights using Python and Power BI.**

---

## 🎥 Project Demo
* **[🚀 Live Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZGE3NzBjZTUtZmNhOS00OTQwLTlmMGItNzU2MWYzMTQzOGJlIiwidCI6IjEwMWRhNTg3LTE4NDMtNGY1Mi04YjhhLTE3YjA2OWM2NmQzMyIsImMiOjJ9)**
* **Video Walkthrough:** Found in `/Media/capstone video.mp4`

---

## 🛠️ Data Engineering Pipeline (Python)
Before visualization, I performed extensive ETL using **Pandas** to ensure data quality:
* **Data Scale:** Processed **541,909 raw records**.
* **Cleaning Logic:** * Removed **135,080 rows** with missing Customer IDs.
    * Filtered out transactions with non-positive quantities and unit prices.
* **Final Result:** **397,884 cleaned rows** generating a total revenue of **$8,911,407.90**.

---
## 🧮 Technical Implementation (DAX & Modeling)

### 1. Core Business Logic
Established explicit measures to ensure calculation accuracy and report performance. Utilizing `SUMX` for row-level precision to calculate total revenue from quantity and unit price.

```dax
Sales Amount = 
SUMX (
    Online_Retail,
    Online_Retail[Quantity] * Online_Retail[UnitPrice]
)
Total Quantity = SUM ( Online_Retail[Quantity] )

## 2. Time Intelligence & Seasonality
Developed a dynamic Calendar table to enable advanced temporal filtering. This powered the discovery that Q4 (Autumn) drives 35.48% of total sales volume.

Calendar = 
VAR _minDate = CALCULATE ( MIN ( Online_Retail[InvoiceDate] ), REMOVEFILTERS ( Online_Retail ) )
VAR _maxDate = CALCULATE ( MAX ( Online_Retail[InvoiceDate] ), REMOVEFILTERS ( Online_Retail ) )
RETURN
ADDCOLUMNS (
    CALENDAR ( _minDate, _maxDate ),
    "Year", YEAR ( [Date] ),
    "Month Name", FORMAT ( [Date], "MMM" ),
    "Season", SWITCH ( TRUE(), 
                MONTH ( [Date] ) IN { 12, 1, 2 }, "Winter",
                MONTH ( [Date] ) IN { 3, 4, 5 },  "Spring",
                MONTH ( [Date] ) IN { 6, 7, 8 },  "Summer", 
                "Autumn" )
)


---

## 📈 Visual Insights
### 1. Executive Summary
Overview of global KPIs including Total Revenue, Total Quantity, and Average Unit Price.
![Dashboard Overview](Media/Dashboard.png)

### 2. Temporal Analysis
Identifying sales peaks and seasonal trends. **Q4 (Autumn)** was identified as the highest-performing period.
![Sales Trends](Media/Sales_Trends_by_Time.png)

### 3. Geospatial Intelligence
Revenue distribution across international markets, highlighting the UK, EIRE, and Hong Kong.
![Global Sales](Media/Sales_by_Country.png)

### 4. Market Benchmarking
Analysis of Average Unit Price by country and high-value product categories.
![Pricing Analysis](Media/Unit_Price_vs_Country.png)
![Category Analysis](Media/Country_Category.png)

---

## 📂 Repository Structure
```text
├── Data/
│   └── Online_Retail_Sample.csv    # 10,000 row sample for demonstration
├── Scripts/
│   └── Online_Retail_powerbi.ipynb # Python ETL & Data Cleaning
├── Media/
│   ├── capstone video.mp4         # Project walkthrough
│   ├── Dashboard.png              # Screenshot
│   ├── Sales_Trends_by_Time.png   # Screenshot
│   ├── Sales_by_Country.png       # Screenshot
│   ├── Unit_Price_vs_Country.png  # Screenshot
│   └── Country_Category.png       # Screenshot
└── README.md                       # Project documentation
