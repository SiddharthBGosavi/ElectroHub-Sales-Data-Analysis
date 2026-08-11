# ⚡ ElectroHub Sales Data Analysis

> An interactive **Power BI sales analytics project** built to analyze ElectroHub's sales performance, profitability, product performance, discounts, promotions, customer activity, and geographical trends.

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Analytics-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Sales%20Analytics-1F6FEB?style=for-the-badge)
![Dashboard](https://img.shields.io/badge/Dashboard-Interactive-2EA44F?style=for-the-badge)

---

## 📌 Project Overview

**ElectroHub Sales Data Analysis** is a Power BI dashboard designed to transform raw transaction-level sales data into an interactive business intelligence solution.

The dashboard combines **Excel, Power Query, Power BI, DAX, data modeling, interactive filters, KPI analysis, charts, maps, and detailed transaction views** to answer practical business questions and support data-driven decision-making.

---

## 🎯 Project Objectives

- Analyze overall sales, profit, and quantity sold.
- Identify top-performing and underperforming products.
- Analyze sales trends across different time periods.
- Understand the relationship between sales and profit.
- Compare business performance between user-selected periods.
- Evaluate discount levels across promotion categories.
- Analyze order-level sales and profitability details.
- Understand geographical sales performance across cities.

---

## 🧰 Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Microsoft Excel** | Source-data handling and preparation |
| **Power Query** | Data cleaning and transformation |
| **Power BI Desktop** | Dashboard development and visualization |
| **DAX** | Measures, calculations, and KPI analysis |
| **Data Modeling** | Fact and dimension relationships |
| **Bing Maps** | City-level geographical analysis |
| **Power BI Slicers** | Interactive filtering |
| **GitHub** | Version control and portfolio hosting |

---

## 🗂️ Data Model

The project follows a dimensional modeling approach with a central sales fact table and supporting dimension tables.

```text
                    ┌───────────────────┐
                    │    Dim Product    │
                    │ Product ID        │
                    │ Product Name      │
                    │ Product Line      │
                    │ Price Per Unit    │
                    └─────────┬─────────┘
                              │
                              ▼
┌───────────────────┐   ┌───────────────┐   ┌────────────────────┐
│  Dim Customers    │──►│   FactTable   │◄──│   Dim Promotion    │
│ Customer ID       │   │ CustomerID    │   │ Promotion ID       │
│ Customer Name     │   │ Product ID    │   │ Promotion Name     │
│ City / State      │   │ PromotionID   │   │ Discount %         │
│ Pincode           │   │ Date          │   │ Coupon Code        │
└───────────────────┘   │ OrderID       │   └────────────────────┘
                        │ Units Sold    │
                        │ Total Sales   │
                        │ Discount      │
                        │ Net Sales     │
                        │ Profit        │
                        └───────┬───────┘
                                │
                                ▼
                         ┌──────────────┐
                         │  Date Table  │
                         │     Date     │
                         └──────────────┘

                    ┌────────────────────┐
                    │   Measures Table   │
                    │ Reusable DAX KPIs  │
                    └────────────────────┘
```

### Main Tables

#### `FactTable`
Contains transaction-level sales information including Customer ID, Product ID, Promotion ID, Date, Order ID, Units Sold, Price Per Unit, Total Sales, Discount Percentage, Discount Value, Net Sales, and Profit.

#### `Dim Product`
Contains Product ID, Product Name, Product Line, and Price Per Unit attributes.

#### `Dim Customers`
Contains Customer ID, Customer Name, City, State, Pincode, Email ID, and Phone Number attributes.

#### `Dim Promotion`
Contains Promotion Name, Ad Type, Coupon Code, Discount Percentage, and Price Reduction Type.

#### `Date Table 1` / `Date Table 2`
Used for date-based analysis and comparison between selected reporting periods.

#### `Measures Table`
A dedicated table for reusable DAX measures such as Net Sales, Net Profit, Units Sold, and supporting calculations.

---

# 🎯 KPIs & Business Questions Answered

The ElectroHub dashboard was specifically designed to answer the following **8 key business requirements**:

### 1. 🏆 Top / Bottom 5 Products by Sales, Profit & Quantity Sold

Identify the **Top 5 and Bottom 5 products** using three important performance metrics:

- **Sales** – Which products generate the highest and lowest revenue?
- **Profit** – Which products contribute most and least to profitability?
- **Quantity Sold** – Which products have the highest and lowest sales volume?

This provides a multi-dimensional view of product performance instead of evaluating products using sales alone.

---

### 2. 📅 Sales Trends Over Time

Analyze how sales performance varies over different time granularities:

- **Daily**
- **Monthly**
- **Quarterly**
- **Annually**

This allows users to identify trends, fluctuations, seasonal patterns, growth periods, and changes in sales performance over time.

---

### 3. 📈 Relationship Between Sales & Profit

The dashboard uses a **scatter plot** to visualize the relationship between **Net Sales and Profit**.

This helps answer questions such as:

- Do higher sales generally result in higher profit?
- Are there products/orders with high sales but comparatively low profit?
- Are there unusual or potentially low-margin transactions?

---

### 4. 🔄 Compare Sales, Profit & Quantity Sold Between Any Two Periods

Users can select **any two date ranges** and compare:

- **Total Sales**
- **Total Profit**
- **Total Quantity / Units Sold**

This enables flexible period-over-period analysis without requiring separate dashboards for different time periods.

---

### 5. 🏷️ Average Discount Offered in Each Discount Category

Analyze the **average discount offered** for each promotion / discount category.

The dashboard can be used to compare categories such as:

- Weekend Flash Sale
- Clearance Sale
- Summer Sale
- New Year Sale
- Festive Diwali

This helps understand the discount strategy used across different promotional campaigns.

---

### 6. 🧾 Total Number of Orders

A dedicated KPI card displays the **Total Number of Orders**, allowing users to quickly understand the overall transaction volume.

The dashboard currently shows approximately **3.51K orders** in the overall context shown in the screenshots.

---

### 7. 🔎 Detailed Order-Level Analysis with Visual Filters

The dashboard provides a detailed table containing sales and other available fields for individual orders / transactions.

Users can filter this detailed view using visual filters such as:

- **Product**
- **Date**
- **Customer ID / Customer Name**
- **Promotion Category / Promotion Name**

The detailed view can expose fields such as:

- Order ID
- Customer ID
- Product ID
- Promotion ID
- Date
- Units Sold
- Price Per Unit
- Total Sales
- Discount Percentage
- Discount Value
- Net Sales
- Profit

This allows users to move from **high-level KPIs to detailed transaction-level investigation**.

---

### 8. 🌍 Sales by Different Cities

A geographical map visual shows **sales distribution across different cities**.

This helps identify:

- High-performing cities
- Low-performing regions
- Geographic concentration of sales
- Potential regional opportunities

The map provides a quick geographic overview that complements the product and time-based analysis.

---

## 📊 Dashboard Highlights

### 🌍 Sales by City
A map visual displays the geographical distribution of sales across cities.

### 🧾 Total Number of Orders
The KPI card displays approximately **3.51K orders** in the overall dashboard context shown.

### 🏷️ Average Discount by Promotion Category
A horizontal bar chart compares average discount values across promotion categories.

### 📈 Profit vs Net Sales
A scatter plot shows the relationship between profit and net sales.

### 📅 Sales Trend Over Time
The dashboard contains a time-series analysis of sales performance across the available date range, with analysis possible at daily, monthly, quarterly, and annual levels.

### 🏆 Top 5 Products by Sales
Products visible among the leading sales performers include:

| Product | Sales shown |
|---|---:|
| Apple iPhone 14 | 22.0M |
| Apple MacBook Air | 20.3M |
| Sony Bravia 55\" TV | 20.0M |
| Samsung Galaxy S21 | 15.7M |
| HP Pavilion Laptop | 14.9M |

### 📉 Bottom 5 Products by Sales
The lowest-sales group shown includes Tupperware Lunch Box, L'Oreal Shampoo, Nivea Body Lotion, Dove Soap Pack, and Colgate Toothpaste.

### 📦 Top 5 Products by Units Sold
Examples visible in the dashboard include Apple iPhone 14 (281), Raymond Suit (274), Fossil Smartwatch (269), Zara Casual Shirt (269), and IFB Microwave Oven (259).

### 💰 Top 5 Products by Profit
Examples visible in the dashboard include Apple iPhone 14 (~2.25M), Apple MacBook Air (~2.08M), Sony Bravia 55\" TV (~2.05M), Samsung Galaxy S21 (~1.61M), and HP Pavilion Laptop (~1.55M).

---

## 🔎 Interactive Filters

The report supports filtering and interactive analysis by:

- 📅 Date / date range
- 👤 Customer / Customer ID
- 📱 Product Name
- 🏷️ Promotion Name / Promotion Category

These filters allow users to move from an executive-level overview to focused product, customer, promotion, date, or transaction-level analysis.

---

## 📐 Key DAX Measures

The project uses a dedicated **Measures Table** to organize reusable calculations.

Representative measures include:

```DAX
Sum of Net Sales = SUM(FactTable[Net_Sales])

Sum of Net Profit = SUM(FactTable[Profit])

Sum of Units Sold = SUM(FactTable[Units Sold])
```

Additional measures are used to support the dashboard's KPIs, comparisons, and analytical visuals.

---

## 📈 Key Metrics Observed

From the dashboard screenshots, the overall dataset shows approximately:

| KPI | Value shown |
|---|---:|
| **Total Sales** | **126.1M** |
| **Total Profit** | **12.9M** |
| **Total Units Sold** | **7.1K** |
| **Total Orders** | **3.51K** |
| **Total Discount Value** | **3.39M** |

These values represent the dashboard context shown in the screenshots and can change when filters are applied.

---

## 💡 Business Insights

### Product performance
The dashboard makes it possible to identify products that perform strongly across sales, profit, and quantity, as well as products that may require further investigation.

### Sales volume vs profitability
A product may have high quantity sold without being the most profitable product. Comparing **Sales + Profit + Quantity Sold** provides a more complete picture of product performance.

### Promotion effectiveness
Different promotion categories have different average discount levels. Discounting should therefore be evaluated alongside sales and profit to understand its business impact.

### Geographic performance
City-level sales analysis can help identify important markets and support regional sales, marketing, and distribution decisions.

### Time-based performance
Daily, monthly, quarterly, and annual analysis enables identification of trends and changes in sales performance over time.

---

## 🏗️ Project Workflow

```text
Raw Sales Data
      ↓
Excel / Power Query
      ↓
Data Cleaning & Transformation
      ↓
Fact & Dimension Tables
      ↓
Power BI Data Model
      ↓
Relationships
      ↓
DAX Measures
      ↓
Interactive Visualizations
      ↓
KPI Analysis
      ↓
Business Insights
```

---

## 📁 Suggested Repository Structure

```text
ElectroHub-Sales-Data-Analysis/
│
├── README.md
├── ElectroHub Sales Data Analysis.pbix
├── Dataset/
│   └── sales_data.csv
├── Screenshots/
│   ├── dashboard-overview.png
│   ├── product-analysis.png
│   ├── date-comparison.png
│   └── detailed-table.png
└── Documentation/
    └── project-notes.md
```

> Adjust the file names above to match the files actually stored in the repository.

---

## 🚀 How to Use

1. Clone or download the repository.
2. Install **Power BI Desktop**.
3. Open the `.pbix` file.
4. Refresh the data source if the dataset is stored separately.
5. Use the date, customer, product, and promotion filters to explore the report.
6. Compare sales, profit, and quantity across selected periods.
7. Use the detailed table to investigate individual transactions.

---

## 📷 Dashboard Preview

The report contains views for:

- Geographic sales analysis
- KPI overview
- Discount analysis
- Profit vs Net Sales
- Sales trend over time
- Top and bottom product performance
- Two-period comparison
- Detailed filtered transactions

To make the GitHub repository more visual, exported screenshots can be placed in a `Screenshots/` folder and embedded like this:

```md
![ElectroHub Dashboard](Screenshots/dashboard-overview.png)
```

---

## 🎓 Skills Demonstrated

- Data Analytics
- Business Intelligence
- Power BI
- DAX
- Power Query
- Excel
- Data Modeling
- Dimensional / star-schema modeling concepts
- KPI development
- Data visualization
- Sales analytics
- Profitability analysis
- Product performance analysis
- Promotion and discount analysis
- Geographical analysis
- Interactive dashboard design
- Business storytelling

---

## 🔮 Future Improvements

- Add year-over-year growth KPIs.
- Add profit margin % and discount-impact measures.
- Add more detailed monthly and quarterly trend analysis.
- Add product-category and product-line drilldowns.
- Add customer segmentation and customer lifetime value analysis.
- Add promotion ROI analysis.
- Add a decomposition-tree analysis for sales and profit.
- Add additional drill-through pages for products and customers.
- Add an executive-summary page with decision-oriented KPIs.

---

## 👨‍💻 Author

**Siddharth Gosavi**  
Data Analytics | SQL | Power BI | Python | Excel

GitHub: [@SiddharthBGosavi](https://github.com/SiddharthBGosavi)

---

## ⭐ Project Purpose

This project was created as a practical **Power BI portfolio project** to demonstrate how sales data can be cleaned, modeled, analyzed, visualized, and converted into business-oriented insights.

If you find the project useful, consider giving the repository a ⭐.

---

## 📄 License

This project is intended for educational and portfolio purposes. Dataset ownership and licensing should be verified before redistribution or commercial use.
