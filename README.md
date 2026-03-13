# Myntra Brand Performance & Risk Analyzer 📊✨

## 📌 Project Overview

The **Myntra Brand Performance & Risk Analyzer** is a data-driven analytics project designed to extract strategic insights from **over 1 million product records** on the Myntra platform. The objective of this project is to transform large-scale raw retail data into actionable intelligence for **vendor performance evaluation, brand risk detection, and customer satisfaction monitoring**.

This solution integrates **SQL-based data engineering** with **Power BI business intelligence dashboards** to identify high-performing brands, detect potential quality risks, and measure customer dissatisfaction trends.

By analyzing key indicators such as **product ratings, price distribution, discount patterns, and brand-level performance metrics**, the system classifies vendors into categories such as:

* 🏆 **Winning Brands** – High customer satisfaction with strong market performance
* ⚠️ **High-Risk Vendors** – High pricing combined with poor customer ratings
* 📉 **Customer Dissatisfaction Segments** – Price ranges or categories with higher negative feedback

The dashboard enables **data-driven decision-making for platform quality control and vendor management teams.**

---

# 🚀 Business Value Proposition

The **Brand Performance Analyzer** acts as a strategic decision-support system for e-commerce operations and quality assurance teams.

### 1️⃣ Strategic Quality Assurance

The system identifies brands that charge **premium prices but receive poor customer ratings**, signaling potential product quality issues. These vendors are flagged as **High-Risk Sellers** that may negatively impact the platform’s brand reputation.

### 2️⃣ Vendor Performance Benchmarking

Rather than relying on raw product counts, the system uses **normalized performance indicators** such as *Unsatisfied Rate %* to ensure fair comparison between:

* Large-scale brands with thousands of products
* Small niche vendors with limited product catalogs

This creates a **volume-independent evaluation framework**.

### 3️⃣ Customer Satisfaction (CSAT) Intelligence

The dashboard analyzes how **customer satisfaction varies across price segments**, helping business teams answer critical questions such as:

* Are expensive products receiving poor ratings?
* Which price segments generate the most dissatisfaction?
* Which brands consistently maintain high ratings?

This insight enables **targeted improvements in product categories and vendor partnerships.**

### 4️⃣ Operational Efficiency for Quality Teams

The system automatically generates a **“Top 10 Unsatisfied Brands” leaderboard**, allowing quality control teams to:

* Prioritize vendor audits
* Investigate product issues
* Improve platform reliability

This automation significantly **reduces manual analysis effort**.

---

# 🛠️ Technical Architecture & Workflow

The project follows a **structured data analytics pipeline**, ensuring reliable insights from raw datasets.

### Data Processing & Validation – SQL

SQL was used for **data engineering, validation, and preprocessing** of the large dataset before visualization.

Key responsibilities included:

* Cleaning corrupted values
* Validating rating logic
* Aggregating brand-level metrics
* Preparing analytical tables

---

### Business Intelligence Layer – Power BI

The cleaned dataset was then integrated into **Power BI**, where an interactive dashboard was developed featuring:

* Dynamic filters and slicers
* Brand-level comparison visuals
* Price vs Rating correlation charts
* Vendor risk analysis dashboards
* Customer dissatisfaction heatmaps

The dashboard allows stakeholders to **explore insights in real time**.

---

### Advanced Analytics – DAX

Custom **DAX measures** were implemented to ensure fair evaluation across **1 million records**.

These measures normalize metrics across brands of different sizes, ensuring accurate comparisons.

---

# 🔍 SQL Implementation (Data Engineering)

The backend SQL pipeline ensured **data reliability before visualization**.

### Data Sanitization

Several extreme outliers were identified and corrected during preprocessing.

Example:

* Discount values incorrectly recorded as **19,000%+** were corrected or filtered.

This prevented skewed analytics.

---

### Business Logic Validation

SQL was used to test the **Customer Satisfaction logic** across the full dataset:

* **Rating ≥ 3 → Satisfied**
* **Rating < 3 → Unsatisfied**

This classification was validated before implementing it inside Power BI.

---

### Brand-Level Aggregation

SQL queries were used to verify:

* Total products per brand
* Average ratings
* Brand performance consistency

This ensured the **Power BI dashboard matched backend aggregates exactly.**

---

# 🧠 Key Analytical DAX Measures

## 1️⃣ Unsatisfied Rate % (Volume-Fair Scoring)

Instead of measuring dissatisfaction using raw counts, this metric calculates the **ratio of dissatisfied products relative to total products of a brand**.

This ensures **fair comparison across brands of different sizes**.

For example:

| Brand      | Products | Unsatisfied | Unsatisfied % |
| ---------- | -------- | ----------- | ------------- |
| Roadster   | 5000     | 300         | 6%            |
| SmallBrand | 20       | 5           | 25%           |

Even though Roadster has more complaints in absolute terms, **SmallBrand actually performs worse proportionally**.

### DAX Implementation

```DAX
Unsatisfied % =
DIVIDE(
    CALCULATE(
        COUNT(ProductID),
        Status = "Unsatisfied"
    ),
    COUNT(ProductID),
    0
) * 100
```

---

# 📊 Key Insights Generated

The analysis produced several valuable insights:

✔ Identification of **High-Risk Vendors** with high price but poor ratings
✔ Detection of **brands with consistently strong customer satisfaction**
✔ Discovery of **price segments with higher dissatisfaction trends**
✔ Fair benchmarking across **large and small vendors**

---

# 🎯 Final Outcome

The **Myntra Brand Performance & Risk Analyzer** demonstrates how large-scale retail data can be transformed into **strategic business intelligence**.

This project showcases expertise in:

* **Data Engineering with SQL**
* **Business Intelligence with Power BI**
* **Advanced Analytics using DAX**
* **Large-scale dataset analysis (1M+ records)**

The solution provides a **scalable framework for e-commerce vendor monitoring, quality assurance, and customer satisfaction analysis.**

