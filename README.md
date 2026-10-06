# 📊 TCS Stock Market Analysis Dashboard

An interactive **Power BI dashboard** built to analyze historical **Tata Consultancy Services (TCS)** stock-market data. The project combines data preparation, calculated date dimensions, KPI cards, market-summary visuals, time-series analysis, and a detailed data table.

> **Project type:** Data Analytics / Business Intelligence  
> **Tool:** Microsoft Power BI  
> **Dataset:** TCS historical stock data (`TCS.NS.csv`)  
> **Period shown in the dashboard:** 2018–2023

---

## 📌 Project Overview

This project analyzes TCS stock performance across different time levels — **day, month, quarter, and year**.

The dashboard was designed to answer questions such as:

- What are the latest/open/high/low stock values?
- How does TCS stock performance change over time?
- Which years show higher or lower stock-price levels?
- How do open, high, low, and close prices move together?
- How does stock performance vary by month and quarter?
- Can the detailed daily stock records be explored from a table view?

The Power BI report contains two main pages:

1. **Home** — KPI cards and interactive charts.
2. **Table** — Detailed stock records and automatically generated analytical insights.

---

## 🖼️ Dashboard Preview

### Home Dashboard

![TCS Dashboard Home](Screenshot%20(153).png)

### Detailed Table

![TCS Dashboard Table](Screenshot%20(154).png)

---

## 📊 Dashboard Components

### 1. KPI Cards

The top section displays:

- **Tata Open**
- **Tata Close**
- **Tata High**
- **Tata Low**

These cards provide a quick view of the selected/current stock metrics.

### 2. TCS Market Summary — Year

A stacked column chart compares TCS market values across years.

### 3. TCS Market Summary — Horizontal View

A stacked bar chart provides another comparison of market values by year.

### 4. TCS Stock by Day

A line chart shows daily movement in:

- Open Price
- High Price
- Close Price
- Low Price

### 5. TCS Stock by Quarter

A quarterly trend visualization helps compare stock performance across Q1–Q4.

### 6. TCS Stock by Month

A monthly line chart shows how TCS stock values change throughout the year.

### 7. TCS Stock by Year

A yearly trend chart provides a high-level view of long-term stock movement.

### 8. Detailed Data Table

The table page contains:

| Column | Description |
|---|---|
| Year | Year extracted from Date |
| Quarter | Quarter extracted from Date |
| Month | Month extracted from Date |
| Day | Day extracted from Date |
| Tata Open Price | Opening stock price |
| Tata High Price | Highest price |
| Tata Close Price | Closing stock price |
| Tata Low Price | Lowest price |

---

## 📁 Dataset

The project uses the `TCS.NS.csv` dataset.

The uploaded dataset contains **1,236 records** and **7 columns**:

```text
Date
Tata Open
Tata High
Tata Low
Tata Close
Tata Adj Close
Tata Volume
```

### Data quality

The CSV contains no blank values in these seven source columns.

One important preprocessing step is **date standardization**. The source file contains dates represented using both `/` and `-` separators. Before publishing or rebuilding the report, the Date column should be converted to one consistent Date type in Power Query.

---

## 🧹 Data Preparation

The main preparation workflow is:

```text
Raw CSV
   ↓
Import into Power BI
   ↓
Clean / standardize Date
   ↓
Set correct data types
   ↓
Create Year / Quarter / Month / Day
   ↓
Build measures
   ↓
Create visualizations
   ↓
Add filters/interactions
   ↓
Publish dashboard
```

### Recommended Power Query transformations

1. Import `TCS.NS.csv`.
2. Remove unnecessary spaces from column names if required.
3. Standardize the `Date` column.
4. Set stock-price columns to Decimal Number.
5. Set `Tata Volume` to Whole Number.
6. Validate missing values and duplicate dates.
7. Create a proper Date table for time intelligence if expanding the project.

---

## 🧮 DAX Calculated Columns

The original project uses the following calculated columns:

```DAX
Day = DAY('TCS NS'[Date])

Month = MONTH('TCS NS'[Date])

Quarter = QUARTER('TCS NS'[Date])

Year = YEAR('TCS NS'[Date])
```

These columns support the day, month, quarter, and year visualizations used in the dashboard.

---

## 💡 Key Analytical Insights

The dashboard's table page automatically surfaces analytical observations from the selected data.

Examples visible in the report include:

- Comparison of the highest and lowest Tata High Price values.
- Relationship/correlation between Tata High Price and total Tata Open Price.
- Contribution of a selected period to Tata High Price.
- Range of Tata Open and Tata Close prices across the displayed day-level analysis.

These statements are generated from the Power BI report's selected/filter context, so they should be interpreted together with the active filters.

---

## 🎯 Business Questions

This dashboard can be used to answer:

### Stock Performance

1. What was the highest TCS stock price?
2. What was the lowest TCS stock price?
3. How did the closing price change over time?
4. How large is the difference between high and low prices?

### Time Analysis

5. Which year had the strongest stock-price levels?
6. How does performance vary by quarter?
7. Which months show higher or lower average prices?
8. How does daily volatility change?

### Price Relationships

9. How are Open, High, Low, and Close prices related?
10. Is a higher opening price generally associated with a higher high price?

### Dashboard Analysis

11. What happens to the selected KPIs when filters are applied?
12. Which period should be investigated further based on unusual price movement?

---

## 🏗️ Suggested GitHub Repository Structure

Use this structure when uploading the project:

```text
TCS-Stock-Analysis-PowerBI/
│
├── README.md
│
├── data/
│   └── TCS.NS.csv
│
├── dashboard/
│   └── TCS_Stock_Analysis.pbix
│
├── screenshots/
│   ├── Screenshot (153).png
│   └── Screenshot (154).png
│
└── docs/
    └── project-notes.md
```

> Rename the PBIX file to something clean such as `TCS_Stock_Analysis.pbix` before pushing it to GitHub.

---

## 🚀 How to Run the Project

### Prerequisites

- Microsoft Power BI Desktop
- Git / GitHub
- `TCS.NS.csv`
- The `.pbix` report file

### Steps

```bash
git clone https://github.com/<your-username>/TCS-Stock-Analysis-PowerBI.git
cd TCS-Stock-Analysis-PowerBI
```

Then:

1. Open the `.pbix` file in **Power BI Desktop**.
2. Check the CSV data-source path.
3. If Power BI cannot find the CSV, update the source path.
4. Refresh the dataset.
5. Verify the Date data type.
6. Explore the **Home** and **Table** pages.
7. Use filters/interactions to analyze different periods.

---

## 📈 Skills Demonstrated

This project demonstrates practical skills in:

- Power BI
- Data Cleaning
- Power Query
- Data Transformation
- DAX
- KPI Design
- Data Visualization
- Time-Series Analysis
- Exploratory Data Analysis
- Business Question Formulation
- Dashboard Design
- Git & GitHub

---

## 🔮 Future Improvements

The current dashboard can be made substantially stronger by adding:

- Date slicer
- Year slicer
- Dynamic KPI cards
- Average Open / Close / High / Low measures
- Daily return %
- Cumulative return %
- Moving averages
- Volatility analysis
- Trading volume analysis
- Candlestick chart
- Monthly return heatmap
- Year-over-year performance
- Drawdown analysis
- Conditional formatting
- Drill-through from year → quarter → month → day
- Proper star-schema Date table
- Bookmarks for switching between analytical views

### Example advanced measures

```DAX
Average Close Price =
AVERAGE('TCS NS'[Tata Close])
```

```DAX
Average Volume =
AVERAGE('TCS NS'[Tata Volume])
```

```DAX
Price Range =
MAX('TCS NS'[Tata High]) - MIN('TCS NS'[Tata Low])
```

---

## ⚠️ Disclaimer

This project is created for **educational and portfolio purposes**.

The dashboard is intended for historical data analysis and visualization. It is **not financial advice** and should not be used alone to make investment decisions.

---

## 👨‍💻 Author

**Sai Mukesh**

Data Analytics / Data Science Student

GitHub: `https://github.com/saikasineni`

---

## ⭐ If You Find This Project Useful

If this project helped you understand Power BI dashboard development, consider giving the repository a ⭐ on GitHub.
