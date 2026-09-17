# 🍫 Choco Bites — Sales Analytics Dashboard

> **An end-to-end Power BI sales analytics project focused on turning transactional sales data into an interactive, decision-ready business report.**

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Analytics-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue)
![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Preparation-5C2D91)
![Status](https://img.shields.io/badge/Project-Completed-success)
![Level](https://img.shields.io/badge/Portfolio-Entry%20Level-orange)

---

## 📊 Project Overview

**Choco Bites Sales Analytics Dashboard** is a fictional business intelligence project built in **Microsoft Power BI** to analyze the sales performance of a chocolate company.

The project was designed to answer a practical business question:

> **How is the business performing, where are sales coming from, which products and people are driving revenue, and how is performance changing over time?**

Rather than focusing only on visual design, the project covers the complete analytical workflow:

**Data preparation → Data modeling → DAX measures → KPI development → Interactive reporting → Business insights**

The current version focuses on the **Sales Overview** report page.

---

## 🎯 Project Objective

The primary objective was to build a sales report that gives management a concise view of business performance while still allowing users to investigate the underlying sales drivers.

The dashboard enables users to:

- Monitor overall sales, cost, profit and profitability.
- Track sales performance over time.
- Compare performance across different time periods.
- Analyze sales by category and region.
- Identify the top 5 products by sales.
- Identify the top 5 salespeople by sales.
- Use slicers to dynamically filter the report.
- Evaluate changes in sales compared with the previous period.

---

## 💼 Business Questions

The dashboard was designed around the following business questions:

### Performance
- What are the company's total sales?
- What are the total costs and total profit?
- What is the current profit margin?
- How many boxes have been sold?
- How has sales changed compared with the previous month?

### Time Analysis
- How do sales change by date?
- What are the sales trends by month?
- How does performance compare across quarters?
- How does annual performance change over time?

### Sales Drivers
- Which product categories contribute most to sales?
- Which regions generate the most sales?
- Which are the top 5 products by sales?
- Which are the top 5 salespeople by sales?
- How much of total sales is concentrated among the leading products?

### Interactive Analysis
- How do these metrics change when filtering by date?
- How does performance change by region, country or salesperson?
- Can users investigate a specific segment without rebuilding the analysis?

---

# 🗂️ Dataset

The project uses the **Choco Bites sample sales dataset** provided in an Excel workbook.

### Dataset characteristics

| Attribute | Details |
|---|---|
| Business | Choco Bites |
| Business type | Fictional chocolate company |
| Source | Excel workbook |
| Approx. records | ~7,000 |
| Analysis domain | Sales & profitability |
| Reporting tool | Microsoft Power BI |

The dataset contains transactional information that can be analyzed across products, locations, salespeople and time.

---

# 🔄 Data Preparation

Although the source dataset was already relatively structured, I used **Power Query** to prepare and validate the data before building the analytical model.

The preparation process included:

- Reviewing the structure and contents of source tables.
- Validating and standardizing data types.
- Reviewing columns for consistency and analytical usability.
- Checking for blank or null values.
- Checking for duplicate records.
- Validating date fields used for time-based analysis.
- Standardizing fields required for filtering and grouping.
- Preparing tables for reliable relationships.
- Structuring the dataset into fact and dimension components.

### Why this matters

The goal of the preparation stage was not simply to "clean" the dataset, but to ensure that the data was **consistent, reliable and suitable for analytical modeling** before calculations and visualizations were created.

---

# 🧩 Data Model

The report uses a **star-schema-oriented data model**, with the `shipments` table serving as the central transactional/fact table and supporting dimension tables providing descriptive context.

### Model structure

```text
                    ┌───────────────┐
                    │   Products    │
                    └───────┬───────┘
                            │
                            │
┌───────────────┐     ┌─────▼───────┐     ┌───────────────┐
│    People     │────►│  Shipments  │◄────│   Locations   │
└───────────────┘     └─────┬───────┘     └───────────────┘
                            │
                            │
                    ┌───────▼───────┐
                    │    Calendar   │
                    └───────────────┘

                    ┌───────────────┐
                    │    Measures   │
                    └───────────────┘
```

### Tables

| Table | Role | Purpose |
|---|---|---|
| `shipments` | Fact | Contains transactional sales information |
| `products` | Dimension | Provides product and category attributes |
| `people` | Dimension | Provides salesperson information |
| `locations` | Dimension | Provides geographic attributes |
| `calendar` | Dimension | Supports time intelligence and period analysis |
| `Measures` | Calculation layer | Organizes reusable DAX measures |

### Modeling approach

The model separates **transactional data** from **descriptive dimensions**, allowing measures to respond dynamically to slicers and visual filter context.

This structure also makes the report easier to extend with additional analytical pages and measures.

---

# 🧮 DAX & Analytical Layer

The report contains **approximately 20+ DAX measures**, including core financial KPIs, ratios, time-based calculations and ranking-related calculations.

Examples include:

### Core KPIs

- Total Sales
- Total Cost
- Total Profit
- Total Boxes
- Profit Margin
- Average Selling Price

### Time & Performance Analysis

- Sales %
- Sales % Change
- Previous-period sales
- Period-over-period comparisons
- Time-based sales analysis

### Ranking & Contribution Analysis

- Top 5 products by sales
- Top 5 salespeople by sales
- Product/category contribution
- Regional sales contribution

The measures are designed to work dynamically with the report's filter context rather than relying solely on static calculated values.

---

# 📈 Dashboard — Sales Overview

The current report contains the **Sales Overview** page.

The page is designed as an executive-style summary where users can quickly understand overall performance and then drill into major sales drivers.

### KPI layer

The primary KPI cards include:

| KPI | Purpose |
|---|---|
| **Total Sales** | Measures overall revenue generated |
| **Total Cost** | Measures associated sales cost |
| **Total Profit** | Measures profitability in absolute terms |
| **Profit Margin** | Measures profitability relative to sales |
| **Total Boxes** | Measures volume sold |

### Analytical visuals

The report also includes analysis of:

- Sales trend over time
- Sales by region
- Sales by category
- Top 5 products by sales
- Top 5 salespeople by sales
- Period-over-period sales performance

### Interactive controls

Users can dynamically filter the analysis using slicers such as:

- Date
- Region
- Country
- Salesperson

This allows the same dashboard to support both **high-level monitoring** and **focused exploratory analysis**.

---

# 🔎 Key Findings

The initial analysis of the dataset produced several notable findings.

### 📉 Month-over-month performance

Sales **decreased by 10.8% compared with the previous month**.

This provides an immediate performance signal and demonstrates why period-over-period metrics are important alongside absolute sales figures.

### 🍫 Category contribution

The **Bars** category contributed **50.17% of total sales**, making it responsible for approximately half of the sales represented in the dataset.

### 🌏 Regional contribution

**APAC** generated **50.61% of total sales**, representing the largest regional contribution in the analyzed data.

### 🏆 Product concentration

The **top 5 products accounted for approximately 25% of total sales**, showing that sales are distributed across a broader product portfolio rather than being generated exclusively by a small number of products.

### 👤 Salesperson performance

**Kelci Walkden** was the highest-performing salesperson in the analysis, generating approximately **$1.52M in sales**.

> These findings describe the analyzed dataset and should be interpreted within the selected reporting period and filters.

---

# 🧠 Analytical Thinking Demonstrated

This project goes beyond creating charts by connecting technical implementation with business questions.

### From data to decision support

```text
Transactional Data
        ↓
Data Validation & Preparation
        ↓
Dimensional Data Model
        ↓
DAX Measures
        ↓
KPI Framework
        ↓
Interactive Dashboard
        ↓
Business Questions
        ↓
Sales Performance Insights
```

The project demonstrates how Power BI can be used to move from **raw transactional records to an analytical decision-support layer**.

---

# 🎨 Dashboard Design Approach

The dashboard was designed with an emphasis on:

- Clear visual hierarchy.
- KPI-first presentation.
- Consistent spacing and alignment.
- Minimal visual clutter.
- Business-oriented chart selection.
- Interactive filtering.
- Clear distinction between headline metrics and supporting analysis.
- Easy navigation from overall performance to sales drivers.

The intention is to make the report usable by someone who needs to understand the business quickly without having to inspect the underlying dataset.

---

# 🛠️ Tools & Technologies

### Microsoft Power BI
Used for:

- Data modeling
- DAX calculations
- Interactive visualizations
- Dashboard development
- Slicers and filtering
- Report layout and UX

### Power Query
Used for:

- Data preparation
- Data validation
- Type standardization
- Structural preparation
- Preparing analytical tables

### DAX
Used for:

- KPI calculations
- Profitability metrics
- Time intelligence
- Period comparisons
- Contribution analysis
- Ranking logic

### Microsoft Excel
Used as the source format for the project dataset.

---

# 📚 What I Learned

This project was created primarily as a hands-on learning exercise to understand how to build a professional sales report in Power BI and use it to evaluate how a business is performing.

Through the project, I practiced:

- Structuring an analytical data model.
- Working with fact and dimension tables.
- Building reusable DAX measures.
- Applying time-based analysis.
- Designing KPI frameworks.
- Creating interactive Power BI reports.
- Translating business questions into visual analysis.
- Presenting data in a way that supports business understanding.

The project helped bridge the gap between **learning Power BI features individually** and using them together to solve a business-oriented analytical problem.

---

# 🔮 Future Improvements

Planned extensions to the project include additional report pages such as:

### Sales Performance
A deeper analysis of salesperson, regional and period performance.

### Product Analysis
A dedicated view of product and category contribution, profitability and product-level trends.

Additional potential improvements include:

- Target vs. actual performance
- Drill-through analysis
- Tooltip pages
- More advanced time-intelligence comparisons
- Decomposition Tree analysis
- Automated insight generation
- Additional profitability analysis
- Improved report navigation and storytelling

---

# 💡 Why This Project Matters

A sales dashboard is useful only when it helps users understand **what happened, where it happened, and what is driving the result**.

This project demonstrates my approach to solving that problem:

> **I start with the business question, structure the data for analysis, build reusable calculations, and then design the report around the decisions the user needs to make.**

That approach is the foundation I am continuing to develop as I pursue an **entry-level Data Analyst** role.

---

# 👨‍💻 Project Role

**Role:** Data Analyst / Power BI Developer — Portfolio Project

**Responsibilities:**

- Data preparation and validation
- Data modeling
- Relationship design
- DAX measure development
- KPI development
- Dashboard design
- Data visualization
- Business analysis
- Insight generation

---

# 📌 Project Status

**Current version:** Sales Overview

**Development status:** Active portfolio project

**Next focus:** Sales Performance → Product Analysis

---

## ⭐ Skills Demonstrated

`Power BI` · `DAX` · `Power Query` · `Data Modeling` · `Star Schema` · `Time Intelligence` · `KPI Development` · `Data Visualization` · `Sales Analytics` · `Business Analysis` · `Dashboard Design` · `Data Storytelling`

---

### About the Author

**Entry-Level Data Analyst**

Building practical analytics projects focused on **Power BI, data modeling, DAX, business intelligence and data-driven decision support**.

