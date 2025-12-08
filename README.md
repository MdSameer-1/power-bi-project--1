# 📊 Power BI Company Performance Analysis Dashboard

## 📌 Overview
This project presents a comprehensive Power BI dashboard designed to analyze company performance across **Profit, People, Products, Shipments, and Year-over-Year growth**.  
The dashboard provides data-driven insights that help leadership make informed business decisions.

---

## 🎯 Project Objectives
- Analyze business performance through **Profit, People, Product** metrics.
- Track **Shipment count** distribution **monthly and by employees**.
- Understand **Amount per box** trend **monthly and person-wise**.
- Identify the **Top most profitable employee**, both **team-wise and overall**.
- Compare business performance using **Amount Current Year vs Prior Year** analytics.

---

## 📁 Files Included
| File | Description |
|------|-------------|
| `Company Performance.pbix` | Power BI dashboard file |
| `SalesData.xlsx` | Dataset used for analysis |
| `Dashboard.png` | Dashboard preview image |
| `README.md` | Project documentation |

---

## 🔑 Key KPIs Used
- **Total Amount (Sales Revenue)**
- **Total Profit**
- **Profit %**
- **Total Boxes**
- **Shipment Count**
- **Amount CY vs PY**
- **Boxes CY vs PY**
- **Top 6 Salespersons Metrics**
- **Top Product Contribution Analysis**

---

## 📈 Insights & Findings
- **India and New Zealand** have the highest contribution to business revenue.
- **Ponnan** is the **top-performing salesperson** with the highest sales and profit contribution.
- **Organic Choco Syrup** is the **most profitable product**, while **85% Dark Bars** is performing poorly with negative profitability.
- **Shipment trends peak mid-year**, indicating seasonal demand.
- **CY vs PY revenue growth is positive**, indicating strong overall performance.
- The company maintains a **high profit margin (~57%+)**.
- **USA and UK markets are underperforming**, representing improvement opportunities.

---

## 💼 Business Value / Decision Making

### **Business Impact 1**
Focus on **high-performing regions (India & New Zealand)** and expand best-selling profitable products.

### **Business Impact 2**
Analyze and improve performance of **low-profit products and low-performing geographies (USA & UK)** by adjusting pricing/strategy.

---

## 🛠 Power BI Development Workflow

### **Power BI Desktop – Data Import & Setup**
- Imported dataset from Excel using **Get Data**.
- Performed cleanup and structure preparation using **Power Query**.

### **Power Query – Transformations Applied**
- Removed duplicates and filtered unnecessary rows.
- Changed data types for accuracy.
- Merged queries to create a single analytical model.
- Created calculated columns and handled errors.

### **Power Pivot – Data Modeling**
- Built a **Star Schema** model (1 Fact + 4 Dimension tables).
- Created **One-to-Many relationships** between dimension and fact tables.
- Added **DAX measures** for trend and KPI analysis.

---

## 📊 Visualizations Used

| Visual Type | Purpose |
|------------|---------|
| **Cards** | To show high-level KPIs clearly |
| **Bar Chart** | Compare employee performance side-by-side |
| **Line Chart** | Identify monthly business trend patterns |
| **Pie / Donut Chart** | Show % contribution by country |
| **Column Chart** | CY vs PY amount comparison |
| **Tree Map** | Product-wise contribution tracking |
| **Table / Matrix** | Employee-wise detailed comparison view |

---

## 🧠 DAX Measures Created (Sample)

```DAX
Total Amount = SUM(Shipments[Amount])

Total Profit = SUM(Shipments[Profit])

Profit % = DIVIDE([Total Profit], [Total Amount], 0)

Shipment Count = COUNTROWS(Shipments)

Amount CY = CALCULATE([Total Amount], YEAR(Shipments[ShipDate]) = YEAR(TODAY()))

Amount PY = CALCULATE([Total Amount], YEAR(Shipments[ShipDate]) = YEAR(TODAY()) - 1)

Amount Variance = [Amount CY] - [Amount PY]
