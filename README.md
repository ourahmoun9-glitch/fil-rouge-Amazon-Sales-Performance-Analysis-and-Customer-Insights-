# Amazon Sales Performance & Customer Insights

**Simplon Maghreb — Data Analyst Capstone Project**

An end-to-end data analytics project covering the full data lifecycle — from raw e‑commerce order data to a decision-ready Power BI dashboard — built to demonstrate the core skills of a Data Analyst: data sourcing, cleaning, modeling, statistical analysis, and data storytelling.

---

## 📌 Project Context

This project is the *fil rouge* (capstone) of the Data Analyst training program. It mobilizes the full set of technical and analytical skills acquired during the training, applied to a real business need, and covers the entire data lifecycle — from understanding the business problem to delivering insights to decision-makers.

**Business framing:** Amazon Sales Performance Analysis & Customer Insights — understanding revenue drivers, order behavior, and customer value across regions, categories, and payment methods.

---

## 🎯 Objectives

- Mobilize technical and analytical skills through a complete, real-world data solution
- Build a reliable, automated, and reusable data pipeline
- Cover the full data lifecycle: sourcing → cleaning → modeling → analysis → visualization
- Deliver clear, actionable business insights through data storytelling

---

## 🗂️ Dataset

| | |
|---|---|
| **Source** | Kaggle (retrieved via `kagglehub`) |
| **File** | `amazon_clean.csv` |
| **Size** | 100,000 orders |
| **Fields** | OrderID, OrderDate, CustomerID, CustomerName, ProductID, ProductName, Category, Brand, Quantity, UnitPrice, Discount, Tax, ShippingCost, TotalAmount, PaymentMethod, OrderStatus, City, State, Country, SellerID, Year, Month |
| **Coverage** | 5 countries · 6 product categories · 2020–2024 |
| **Data quality** | 0 missing values, 0 duplicate rows, no invalid records detected |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** | Core language for the analysis pipeline |
| **Pandas** | Data loading, cleaning & transformation |
| **NumPy** | Numerical operations on arrays |
| **Matplotlib** | Exploratory charts & distributions |
| **Seaborn** | Statistical data visualization |
| **SciPy** | T-test, Chi² and correlation testing |
| **Kagglehub** | Dataset sourcing (Kaggle API) |
| **Jupyter Notebook** | Interactive analysis environment |
| **Power BI** | Interactive dashboard & reporting |

---

## 🔄 Project Pipeline

1. **Organisation & Piloting** — project management tool, task/milestone planning
2. **Business Framing** — problem reformulation, objectives, and 5+ actionable KPIs
3. **Data Sourcing** — dataset selection, quality checks, documentation
4. **Exploratory Data Analysis (EDA)** — descriptive statistics, distributions, anomaly detection, first insights
5. **Cleaning & Modeling** — missing values/duplicates handling, standardization, star-schema data model
6. **KPI Construction** — trend, segment, and correlation analysis
7. **Statistical Testing** — T-test, Chi², Pearson correlation with business interpretation
8. **Dashboard & Visualization** — summary + detail pages, interactive filters, clear navigation

---

## 🔍 Exploratory Data Analysis — Key Findings

- **Total amount** is right-skewed: most orders are low-to-medium value, with a few high-value outliers
- **Unit prices** and **order quantities** are evenly distributed across the catalog
- **Electronics** generates the highest revenue; **Home & Kitchen** the lowest — though all categories perform comparably
- **The United States** is the top-revenue country, followed by India
- Monthly revenue is **stable year-round**, peaking in **August** and lowest in **February**
- ~**75%** of orders are successfully delivered; cancellation and return rates are each around **3%**

---

## 🧹 Cleaning & Data Modeling

- **Missing values:** 0 found across all 22 columns — no imputation required
- **Duplicates:** 0 duplicate records — dataset already unique
- **Standardization:** Country & Category fields normalized to title case
- **Date parsing:** `OrderDate` converted to datetime; Year & Month extracted
- **Data model:** Star schema built for Power BI —
  - **Fact table:** `facte_sales`
  - **Dimension tables:** `dim_customers`, `dim_date`, `dim_products`, `dim_payment`, `dim_status`

---

## 📊 Statistical Analysis

| Test | Question | Result | Business Interpretation |
|---|---|---|---|
| **T-Test** | Delivered vs. Cancelled — average order value? | p = 0.058 (not significant) | Order amount does not influence delivery vs. cancellation |
| **Chi² Test** | Payment method vs. order status — is there a link? | p = 0.777 (not significant) | Payment method does not influence order status |
| **Pearson Correlation** | Discount vs. total order amount? | r = ‑0.108, p < 0.001 (significant) | Higher discounts are associated with lower order totals |

---

## 📈 Power BI Dashboard

The dashboard is built around a **3-page decision-oriented structure**:

1. **Cover Page** — navigation entry point
2. **Sales Performance** — Total Orders, Avg Order Value, Total Revenue, monthly trend, revenue by payment method, sales by category & brand, orders by status
3. **Customer Analytics** — Avg Orders per Customer, Unique Customers, One-Time Customers, Revenue per Customer, top revenue by city, revenue by customer, orders by category, revenue by customer location (map)

All pages include interactive slicers (Payment Method, Country, Year, Order Status) and cross-page navigation buttons.

**Key KPIs:**

| KPI | Value |
|---|---|
| Total Orders | 100,000 |
| Average Order Value | $918.26 |
| Total Revenue | $91.83M |
| Unique Customers | 43K |
| One-Time Customers | 14K |
| Revenue per Customer | $2.12K |
| Cancellation Rate | 3.03% |
| Return Rate | 3.05% |

---

## 📁 Project Structure

```
├── amazon_clean.csv              # Cleaned source dataset
├── test.ipynb                    # EDA, cleaning & statistical analysis notebook
├── dashboard.pbix                # Power BI dashboard (Sales Performance & Customer Analytics)
├── Amazon_Simplon_Presentation.pptx  # Project presentation
└── README.md                     # Project documentation
```

---

## 💡 Recommendations

- Investigate discount strategy: discounting is correlated with lower order totals — consider targeted discounts on high-margin categories rather than broad promotions
- Focus retention efforts on the **14K one-time customers**, who represent a third of the customer base
- Explore the **February revenue dip** for seasonal marketing opportunities, and reinforce what drives the **August peak**
- Delivery/cancellation and payment method show no statistically significant link to order outcomes — operational issues (e.g., stock, logistics) are more likely drivers of cancellations than order value or payment choice

---

## 👤 Author

Capstone project completed as part of the **Data Analyst training program** at **Simplon Maghreb**, in partnership with an **Amazon**-themed business case.
