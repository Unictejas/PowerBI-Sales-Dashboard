# PowerBI-Sales-Dashboard
Interactive Power BI dashboard analyzing sales performance by region, product, and month.
My project is an Interactive Sales Analysis Dashboard built in Power BI. Its main purpose was to transform raw sales data into actionable business intelligence for the sales management team."

1. The Goal
Problem: The sales team lacked a single, clear, and interactive view to monitor performance.

Goal: To create a centralized dashboard that would allow managers to instantly see key metrics, spot trends, and identify the top and bottom performers.

2. The Technical Work
Data Model: I connected to three separate files—Sales Data, Product Master, and Employee Master—and structured them into an efficient Star Schema.

Key Metric (DAX): The most important calculation was the Revenue measure. I used DAX to calculate Revenue by multiplying the Unit Sold from the Sales table by the Price per unit from the Product table to ensure accuracy.

3. The Results
Key Insights: The dashboard immediately shows the total performance, such as $96.62M in Total Revenue for the period.

Actionable Visuals: It provides specific breakdowns, including:

The Daily Revenue Trend to track momentum.

Revenue by Supervisor and Employee to manage team performance.

For example, we can see that the top supervisor drives 31.08% of the total revenue, highlighting a key success area.

Interactivity: Users can easily filter the entire report by Date, Product Name, or Supervisor to get specific answers fast.

# 📊 Interactive Sales Analysis Dashboard

This project features an interactive sales analysis dashboard built using Power BI. It provides a comprehensive view of sales performance, key metrics, and detailed breakdowns by employee and product over the period from **January 1, 2019, to April 20, 2019**.

## ✨ Key Features & Visualizations

The dashboard is designed for ease of use, allowing analysts and managers to filter and drill down into sales data instantly.

### Key Performance Indicators (KPIs)
* **Total Revenue**: The primary metric, calculated using Unit Sold multiplied by the Price per Unit.
* **Total Unit Sold**: The aggregate count of all products sold.

### Core Visualizations
* **Sum of Revenue by Day**: A line chart visualizing daily sales trends.
* **Revenue and Unit Sold by Product Name**: A combined chart for product performance comparison.
* **Revenue by Supervisor**: A visual breakdown showing each supervisor's contribution to total revenue, including their percentage share.
* **Revenue by EMP Name**: Detailed revenue contribution for individual employees.

### Filters & Slicers
The dashboard includes slicers for interactive filtering by:
* Date Range (1/1/2019 to 4/20/2019)
* Product ID
* Product Name
* EMP Name
* Supervisor

## 🛠️ Prerequisites

To view and edit this dashboard, you must have the following software installed:

* **Power BI Desktop** (latest version recommended)

## 📁 Data Source and Schema

The Power BI model utilizes a star schema composed of one fact table and two dimension tables. All data is provided in the `.csv` files within this repository.

| Table Name | Type | Key Columns | Other Columns |
| :--- | :--- | :--- | :--- |
| **Sales Data** (`Sales Data.csv`) | Fact | `Date`, `EMP ID`, `Product ID` | `Unit Sold` |
| **Product Master** (`Product Master.csv`) | Dimension | `Product ID` | `Product Name`, `Price per unit` |
| **Emp Master** (`Emp Master.csv`) | Dimension | `EMP ID` | `EMP Name`, `Supervisor` |

### Calculated Measure (DAX)

The primary measure, **Revenue**, is calculated in the Power BI model as:
```dax
Revenue = SUMX('Sales Data', 'Sales Data'[Unit Sold] * RELATED('Product Master'[Price per unit]))
