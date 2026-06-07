# 📊 Data Visualization Labs — Power BI Portfolio

> A collection of hands-on **Power BI** labs covering data modeling, DAX, visual design, and dashboard storytelling — built as part of a Data Visualization course.

---

## 🗂️ Repository Structure

```
DV-Labs/
├── Lab1/   → Hospital Data Modeling & Relationships
├── Lab2/   → Data Cleaning & Multi-Source Merging
├── Lab3/   → DAX Fundamentals & Sales Analytics
├── Lab5/   → Star Schema Modeling & Time Intelligence
├── Lab6/   → Advanced Visual Analytics & Chart Selection
└── README.md
```

---

## 🧪 Labs Overview

### 🏥 Lab 1 — Hospital Data Modeling & Relationships
**Objective:** Build a relational data model in Power BI using hospital datasets.

**Datasets:**
- `Hospital_Master.xlsx` — Hospital metadata (IDs, names, locations)
- `Patients.xlsx` — Patient demographics and registration info
- `Visits.xlsx` — Visit records linking patients to hospitals

**Key Skills:**
- Creating table relationships (one-to-many, many-to-one)
- Star schema vs. flat file modeling
- Building basic visuals on top of a multi-table model
- Understanding primary and foreign keys in Power BI

---

### 🧹 Lab 2 — Data Cleaning & Multi-Source Merging
**Objective:** Ingest, clean, and merge sales data from three different channels using Power Query.

**Datasets:**
- `App_Sales.csv` — Mobile app orders (messy dates, inconsistent status labels)
- `Marketplace_Sales.csv` — Third-party marketplace orders
- `Web_Sales.csv` — Direct web channel orders

**Key Skills:**
- Power Query: removing duplicates, fixing data types, standardizing columns
- Appending tables from multiple sources
- Distinguishing **structured vs. unstructured data**
- Applying **Good vs. Bad visual** principles (see lab PDF reference)

---

### 📐 Lab 3 — DAX Fundamentals & PakTech Sales Analytics
**Objective:** Learn core DAX concepts and apply them to a Pakistani tech retail dataset.

**Dataset:**
- `PakTech_Sales_Data.csv` — Sales transactions (Lahore, Karachi, Islamabad) with product, customer, and payment info

**Key Skills:**
- **Calculated Columns** vs. **Measures** — when to use each
- Core aggregation functions: `SUM`, `AVERAGE`, `COUNT`, `COUNTA`
- `CALCULATE`, `FILTER`, `ALL` for context manipulation
- Building a date table with `CALENDAR()` and `CALENDARAUTO()`
- Time Intelligence: `TOTALYTD`, `SAMEPERIODLASTYEAR`, `DATEADD`

**DAX Concepts Covered:**

| Concept | Function |
|---|---|
| Aggregation | `SUM`, `AVERAGE`, `MIN`, `MAX` |
| Conditional | `IF`, `SWITCH` |
| Filter Context | `CALCULATE`, `FILTER`, `ALL` |
| Time Intelligence | `TOTALYTD`, `DATEADD`, `SAMEPERIODLASTYEAR` |
| Table Functions | `RELATED`, `LOOKUPVALUE` |

---

### 🌟 Lab 5 — Star Schema & Time Intelligence (FactSales Model)
**Objective:** Design a proper star schema with a clean date table, then apply Time Intelligence DAX.

**Dataset:** FactSales (2022–2025), DimCustomer, DimStore (internal to .pbix)

**Key Skills:**
- Building a **star schema** with Fact and Dimension tables
- `CALENDAR()` vs `CALENDARAUTO()` — choosing the right approach
- Why scoped date tables matter for YTD accuracy
- Relating DimDate to FactSales for time-based filtering

**Notable Decision:**
> `CALENDAR(MIN(FactSales[OrderDate]), MAX(FactSales[OrderDate]))` was used instead of `CALENDARAUTO()` because DimStore has dates back to 2017 and DimCustomer back to 2019 — which would create thousands of empty date rows outside the 2022–2025 sales window, degrading model performance and breaking YTD measures.

See [`Lab5/DAX_Calendar_Notes.txt`](Lab5/DAX_Calendar_Notes.txt) for full reasoning.

---

### 📈 Lab 6 — Advanced Visual Analytics & Chart Selection
**Objective:** Apply advanced Power BI visuals with proper chart selection principles for a global retail scenario.

**Dataset:**
- `data.csv` — TechMart global sales (USA, UK, India) across Electronics and Furniture categories

**Fields:** `OrderDate`, `Country`, `Region`, `Team`, `Product`, `Category`, `Salesperson`, `CustomerSegment`, `Shipments`, `UnitPrice`, `SalesAmount`, `Discount`, `Profit`

**Key Skills:**
- Selecting the **right chart type** for each business question:
  - Comparison → Bar/Column charts
  - Trend → Line charts
  - Composition → Pie/Donut/Treemap
  - Relationship → Scatter plots
  - Change over periods → Waterfall charts
- Applying **data storytelling**: titles, highlights, tooltips
- Identifying and correcting **wrong visual usage**
- Evaluating salesperson efficiency and regional performance

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Power BI Desktop** | All dashboards and data models |
| **Power Query (M Language)** | Data transformation and cleaning |
| **DAX** | Measures, calculated columns, time intelligence |
| **Excel / CSV** | Source data files |

---

## 🚀 Getting Started

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free) — Windows only
- Microsoft Excel (for `.xlsx` source files)

### Running a Lab
1. Clone or download this repository
2. Open the relevant lab folder
3. Open the `.pbix` file in Power BI Desktop
4. If prompted, update the data source path to point to the CSV/Excel files in the same folder
5. Click **Refresh** to reload data

> **Note:** `.pbix` files are binary and tracked in this repo for reference. For large files, Git LFS may be needed.

---

## 📚 Key Concepts Reference

### When to Use Which Chart

| Question Type | Best Visual |
|---|---|
| Compare categories | Bar / Column chart |
| Show trend over time | Line chart |
| Show part-to-whole | Pie / Donut / Treemap |
| Show correlation | Scatter plot |
| Show before/after change | Waterfall chart |
| Show geographic data | Map visual |
| Show KPIs at a glance | Card / KPI visual |

### DAX: Measure vs. Calculated Column

| | Measure | Calculated Column |
|---|---|---|
| Evaluated | At query time | At data refresh |
| Context | Filter context | Row context |
| Stored in model | ❌ No | ✅ Yes |
| Increases file size | ❌ No | ✅ Yes |
| Best for | Aggregations, KPIs | Per-row attributes |

---

## 📁 File Reference

| File | Lab | Type | Description |
|---|---|---|---|
| `Hospital_Master.xlsx` | Lab 1 | Excel | Hospital dimension data |
| `Patients.xlsx` | Lab 1 | Excel | Patient records |
| `Visits.xlsx` | Lab 1 | Excel | Visit transactions |
| `App_Sales.csv` | Lab 2 | CSV | App channel orders |
| `Marketplace_Sales.csv` | Lab 2 | CSV | Marketplace orders |
| `Web_Sales.csv` | Lab 2 | CSV | Web channel orders |
| `PakTech_Sales_Data.csv` | Lab 3 | CSV | Pakistani tech retailer sales |
| `DAX_Calendar_Notes.txt` | Lab 5 | Text | CALENDAR vs CALENDARAUTO reasoning |
| `data.csv` | Lab 6 | CSV | TechMart global retail sales |

---

## 👤 Author

MOHAMMAD DANIYAL USMAN
BS Data Science — Data Visualization Course

---

## 📄 License

This repository is for educational purposes. Datasets are synthetic/sample data created for lab exercises.
