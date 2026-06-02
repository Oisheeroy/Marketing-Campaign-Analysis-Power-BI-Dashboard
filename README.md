# 📊 Marketing Campaign Analysis Dashboard | Power BI

## 📌 Project Overview

The **Marketing Campaign Analysis Dashboard** is an end-to-end Business Intelligence project developed in **Power BI** to evaluate and compare the performance of digital and traditional marketing campaigns across multiple regions and industries.

The dashboard provides actionable insights into campaign effectiveness through key performance indicators (KPIs) such as **Revenue, Spend, Conversions, Impressions, and Return on Investment (ROI)**, enabling data-driven marketing decisions and budget optimization.

---

## 🎯 Business Objectives

* Analyze the effectiveness of marketing campaigns across channels and regions.
* Measure campaign performance using industry-standard KPIs.
* Identify high-performing and underperforming campaigns.
* Compare Digital vs Traditional marketing strategies.
* Enable stakeholders to make informed decisions through interactive visualizations.

---

## 📂 Dataset Overview

### 1. Marketing_Campaign_Details

Contains campaign-level information including:

* Campaign Name
* Campaign Type (Digital / Traditional)
* Average Spend
* ROI

### 2. Marketing_Campaign_Performance

Fact table containing:

* Impressions
* Clicks
* Conversions
* Spend
* Revenue
* ROI
* Region
* Industry

### 3. Region_Performance

Aggregated regional performance metrics:

* Region
* Total Spend
* Total Revenue
* Average ROI

---

## 🛠 Data Preparation

Data preprocessing was performed using **Power Query**:

* Removed duplicate records
* Standardized data types
* Renamed columns for readability
* Handled inconsistencies and formatting issues
* Optimized datasets for reporting and analysis

---

## 🏗 Data Modeling

A **Star Schema** design was implemented to ensure scalability and efficient query performance.

### Fact Table

* Marketing_Campaign_Performance

### Dimension Tables

* Marketing_Campaign_Details
* Region_Performance

### Relationships

| From          | To            | Relationship |
| ------------- | ------------- | ------------ |
| Campaign_Name | Campaign_Name | One-to-Many  |
| Region        | Region        | One-to-Many  |

This structure improves filtering behavior, DAX calculations, and dashboard responsiveness.

---

## 📈 Key Performance Indicators (DAX)

### Total Impressions

```DAX
Total Impressions =
SUM(Marketing_Campaign_Performance[Impressions])
```

### Total Clicks

```DAX
Total Clicks =
SUM(Marketing_Campaign_Performance[Clicks])
```

### Total Conversions

```DAX
Total Conversions =
SUM(Marketing_Campaign_Performance[Conversions])
```

### Total Spend

```DAX
Total Spend =
SUM(Marketing_Campaign_Performance[Spend])
```

### Total Revenue

```DAX
Total Revenue =
SUM(Marketing_Campaign_Performance[Revenue])
```

### Total ROI

```DAX
Total ROI =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend]
)
```

### Average ROI

```DAX
Average ROI =
AVERAGE(Marketing_Campaign_Performance[ROI])
```

### Best Performing Campaign

```DAX
Best Campaign =
VAR MaxROI =
    MAX(Marketing_Campaign_Performance[ROI])

RETURN
CALCULATE(
    FIRSTNONBLANK(
        Marketing_Campaign_Performance[Campaign_Name],
        1
    ),
    Marketing_Campaign_Performance[ROI] = MaxROI
)
```

---

## 📊 Dashboard Features

* Executive KPI Summary Cards
* Campaign Performance Analysis
* Regional Performance Comparison
* ROI Distribution Analysis
* Revenue vs Spend Visualization
* Interactive Filters and Slicers
* Campaign Type Comparison (Digital vs Traditional)

---

## 🔍 Key Insights

### Digital Campaigns Outperformed Traditional Campaigns

Digital marketing channels consistently generated higher returns, demonstrating stronger ROI efficiency.

### Influencer Marketing Delivered the Highest ROI

Influencer Marketing achieved approximately **109% ROI**, making it the most effective campaign strategy.

### Email Marketing Underperformed

Email campaigns generated the lowest ROI and may require optimization or budget reallocation.

### Strong Regional Performance in North America

North America emerged as the highest-performing region in terms of revenue generation and ROI.

### Overall Business Performance

* **Total ROI:** 65.56%
* **Average ROI:** 67.63%

These metrics indicate a profitable marketing portfolio with opportunities for further optimization.

---

## 🧠 Analytical Concepts Used

### Return on Investment (ROI)

```text
ROI = (Revenue - Spend) / Spend
```

Measures campaign profitability and overall effectiveness.

### Click Through Rate (CTR)

```text
CTR = Clicks / Impressions
```

Evaluates audience engagement with marketing content.

### Conversion Rate

```text
Conversion Rate = Conversions / Clicks
```

Measures the ability of campaigns to convert visitors into customers.

### Total ROI vs Average ROI

Comparing Total ROI and Average ROI helps identify performance skewness and outlier campaigns.

---

## 🧰 Tools & Technologies

* Power BI Desktop
* Power Query (ETL)
* DAX (Data Analysis Expressions)
* CSV Datasets
* Star Schema Data Modeling

---

## 🚀 Getting Started

1. Clone this repository.
2. Open the `.pbix` file in Power BI Desktop.
3. Refresh data sources if required.
4. Use slicers and filters to explore campaign performance interactively.

---

## 📷 Dashboard Preview

> Add screenshots of the dashboard here for better visualization and recruiter engagement.

---

## 📬 Conclusion

This project demonstrates practical experience in **Business Intelligence, Data Modeling, DAX Calculations, Data Visualization, and Marketing Analytics**. It showcases how Power BI can transform raw marketing data into actionable insights that support strategic business decisions.

