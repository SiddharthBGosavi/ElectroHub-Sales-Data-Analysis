# ⚡ ElectroHub Sales Data Analysis

> An interactive **Power BI sales analytics project** built to analyze ElectroHub's sales performance, profitability, product performance, discounts, promotions, customer activity, and geographical trends.

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Analytics-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Sales%20Analytics-1F6FEB?style=for-the-badge)
![Dashboard](https://img.shields.io/badge/Dashboard-Interactive-2EA44F?style=for-the-badge)

---

## 📌 Project Overview

**ElectroHub Sales Data Analysis** is a Power BI dashboard designed to transform raw transaction-level sales data into an interactive business intelligence solution.

The project focuses on answering practical business questions such as:

- How are sales and profit changing over time?
- Which products generate the highest sales and profit?
- Which products have the weakest performance?
- Which cities contribute most to sales?
- How much discount is being offered across promotion categories?
- How do sales, profit, and units sold compare across different time periods?
- How can management quickly filter and investigate customer, product, promotion, and date-level performance?

The dashboard combines **data modeling, DAX measures, interactive filters, KPI analysis, charts, maps, and detailed transaction views** in a single Power BI solution.

---

## 🎯 Objectives

1. Analyze overall sales, profit, and quantity sold.
2. Identify top-performing and underperforming products.
3. Evaluate product performance using sales, units, and profit together.
4. Understand sales distribution across cities.
5. Analyze discount levels across different promotional categories.
6. Study sales and profitability trends over time.
7. Enable flexible analysis through date-based and category-based filters.
8. Build a dimensional data model suitable for Power BI reporting.

---

## 🧰 Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development and visualization |
| **DAX** | Measures, calculations, and KPI analysis |
| **Power Query** | Data transformation and preparation |
| **Microsoft Excel** | Source-data handling / preparation |
| **Data Modeling** | Relationships between fact and dimension tables |
| **Bing Maps** | City-level geographical analysis |
| **Power BI Slicers** | Interactive filtering |
| **GitHub** | Version control and portfolio hosting |

---

## 🗂️ Data Model

The project uses a dimensional model centered around a sales **Fact Table** and supporting dimension tables.

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
Used for date-based analysis and comparison between reporting periods / filter selections.

#### `Measures Table`
A dedicated location for reusable DAX measures such as Net Sales, Net Profit, Units Sold, and supporting calculations.

---

## 📊 Dashboard Highlights

### 🌍 Sales by City
A map visual displays the geographical distribution of sales across cities. Bubble size helps identify locations with relatively higher sales activity.

**Business use:** Identify strong geographic markets and regions requiring further investigation.

### 🧾 Total Number of Orders
The KPI card displays approximately **3.51K orders** for the current dashboard context.

### 🏷️ Average Discount by Promotion Category
The dashboard compares average discount values across promotion categories such as Weekend Flash Sale, Clearance Sale, Summer Sale, New Year Sale, and Festive Diwali.

### 📈 Profit vs Net Sales
A scatter plot compares **Profit** against **Net Sales**, helping identify the relationship between revenue and profitability and spot unusual observations.

### 📅 Sales Trend Over Time
The time-series visual tracks sales across the available years from 2020 onward.

The displayed annual values are approximately:

| Year | Sales shown |
|---|---:|
| 2020 | 33M |
| 2021 | 31M |
| 2022 | 30M |
| 2023 | 35M |
| 2024 | 0M* |

> *The screenshot shows 0M for 2024. This may represent no applicable sales records in the current model/filter context or incomplete 2024 data.

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

### 📦 Bottom 5 Products by Units Sold
Examples include Nivea Body Lotion, Tupperware Lunch Box, Milton Thermos Flask, Fabindia Kurta, and Borosil Glass Set.

### 💰 Top 5 Products by Profit
Examples visible in the dashboard include Apple iPhone 14 (~2.25M), Apple MacBook Air (~2.08M), Sony Bravia 55\" TV (~2.05M), Samsung Galaxy S21 (~1.61M), and HP Pavilion Laptop (~1.55M).

### 📉 Bottom 5 Products by Profit
The lowest-profit group shown includes Tupperware Lunch Box, L'Oreal Shampoo, Nivea Body Lotion, Dove Soap Pack, and Colgate Toothpaste.

### 🔄 Period Comparison
Two date filters are used to compare KPI outcomes across selected periods. The comparison includes **Total Sales, Total Profit, and Total Quantity / Units Sold**.

### 📋 Detailed Transaction Table
A filtered detail table provides visibility into Customer ID, Product ID, Promotion ID, Date, Discount Percentage, Discount Value, Net Sales, Price Per Unit, Profit, and order-level information.

---

## 🔎 Interactive Filters

The report supports filtering by:

- 📅 Date / date range
- 👤 Customer / Name
- 📱 Product Name
- 🏷️ Promotion Name

These controls allow users to move from an executive-level overview to focused product, customer, promotion, or time-period analysis.

---

## 📐 Key DAX Measures

The project uses a dedicated **Measures Table** to organize reusable calculations.

Representative measures include:

```DAX
Sum of Net Sales = SUM(FactTable[Net_Sales])

Sum of Net Profit = SUM(FactTable[Profit])

Sum of Units Sold = SUM(FactTable[Units Sold])
```

Additional measures can be added as the analytical model evolves.

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

These are dashboard observations and can change when filters are applied.

---

## 💡 Business Insights

### Product performance
High-value electronics such as smartphones, laptops, and televisions dominate the top-sales and top-profit rankings, while several household and personal-care products appear among the lowest performers.

### Sales volume vs profitability
A product can perform strongly in units sold without being among the highest-profit products. Evaluating **sales, units, and profit together** provides a more complete view of product performance.

### Promotion effectiveness
Promotion categories have different discount levels. Discounting should therefore be evaluated against sales uplift and profitability rather than volume alone.

### Geographic performance
The city map helps identify geographic concentrations of sales and can support future regional marketing and distribution decisions.

### Time-based performance
The displayed trend peaks around **2023 (~35M)**, while the current visual shows 0M for 2024. The underlying date/data configuration should be checked before treating the 2024 point as a business conclusion.

---

## 🧠 Analytical Questions Answered

- What is the total sales generated?
- What is the total profit generated?
- How many units have been sold?
- How many orders have been placed?
- Which products generate the most revenue?
- Which products generate the most profit?
- Which products have the lowest sales?
- Which products have the lowest profit?
- Which products have the highest unit volume?
- Which promotion categories provide higher discounts?
- How does profit relate to net sales?
- Which cities contribute to sales?
- How does performance change across selected dates?
- What does the transaction-level data look like after applying filters?

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
6. Compare sales, profit, and units across different periods.

---

## 📷 Dashboard Preview

The report contains views for:

- Geographic sales analysis
- KPI overview
- Discount analysis
- Profit vs Net Sales
- Sales trend over time
- Top and bottom product performance
- Date-range comparisons
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
- Add monthly and quarterly trend analysis.
- Add product-category and product-line drilldowns.
- Add customer segmentation and customer lifetime value analysis.
- Add promotion ROI analysis.
- Add a decomposition-tree analysis for sales and profit.
- Validate the 2024 date/data configuration responsible for the 0M point.
- Add a dedicated executive-summary page with fewer, more decision-oriented visuals.

---

## 👨‍💻 Author

**Siddharth Gosavi**  
Data Analytics | SQL | Power BI | Python | Excel

GitHub: [@SiddharthBGosavi](https://github.com/SiddharthBGosavi)

---

## ⭐ Project Purpose

This project was created as a practical **Power BI portfolio project** to demonstrate how sales data can be modeled, analyzed, visualized, and converted into business-oriented insights.

If you find the project useful, consider giving the repository a ⭐.

---

## 📄 License

This project is intended for educational and portfolio purposes. Dataset ownership and licensing should be verified before redistribution or commercial use.
