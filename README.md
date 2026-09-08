# Madhav Ecommerce Sales Dashboard — Power BI Project

## 📌 Project Overview
This project is an **interactive Power BI dashboard** built to track and analyze online e-commerce sales data for "Madhav Ecommerce." The dashboard consolidates order-level and transaction-level data into a single, filterable view that highlights sales performance, profitability, customer behavior, and payment trends across regions and time.

## 📊 Dataset
Two source tables were connected and joined on `Order ID`:

| File | Rows | Key Columns |
|---|---|---|
| `Orders.csv` | 500 orders | Order ID, Order Date, CustomerName, State, City |
| `Details.csv` | 1500 line items | Order ID, Amount, Profit, Quantity, Category, Sub-Category, PaymentMode |

**Grain note:** `Details.csv` is at a finer grain than `Orders.csv` (multiple product lines per order), so a one-to-many join on `Order ID` was required to bring order-level attributes (state, customer, date) into the sales/profit analysis.

## 🎯 Dashboard Highlights
The final dashboard surfaces the following KPIs and views:

- **Top-line KPIs:** Sum of Amount (₹438K), Sum of Profit (₹37K), Sum of Quantity (5,615 units), and Average Order Value (₹121K AOV)
- **Sum of Amount by State** — bar chart showing Madhya Pradesh and Maharashtra as the top revenue-generating states
- **Count of Quantity by Category** — donut chart showing Clothing (63%) dominates unit volume over Electronics (21%) and Furniture (16%)
- **Sum of Amount by CustomerName** — top customers by revenue (Harivansh, Madhav, Madan Mohan, Shiva)
- **Count of Quantity by PaymentMode** — donut chart showing COD (46%) is the leading payment method, followed by UPI (22%)
- **Profit by Month** — line/column chart revealing seasonality, with a clear profit dip in May–June and a peak in November
- **Sum of Profit by Sub-Category** — Printers and Bookcases are the most profitable sub-categories, despite Clothing driving the most volume
- **Interactivity:** Quarter slicers (Qtr 1–Qtr 4) and a category dropdown filter allow drill-down into any time period or product segment

## 🛠️ What I Learned
- **Data modeling:** Connected two separate CSVs and built a relationship between `Orders` and `Details` on `Order ID`, understanding the difference between order-level and line-item-level grain.
- **DAX & calculations:** Created calculated fields and measures (e.g., Sum of Amount, Sum of Profit, Average Order Value) to summarize raw transactional data into meaningful KPIs.
- **Interactive filtering:** Implemented slicers (quarter buttons) and dropdown filters so users can dynamically drill down into specific time periods or categories without needing separate reports.
- **Visualization selection:** Practiced choosing the right chart type for the right question — donut charts for part-to-whole breakdowns (category, payment mode), bar charts for ranked comparisons (state, customer), and a column/line chart for trends over time (monthly profit).
- **Dashboard design:** Applied a consistent dark theme, KPI cards for at-a-glance metrics, and a logical layout (KPIs top, breakdowns middle, trends right) to make the report scannable in seconds.
- **End-to-end BI workflow:** Went through the full analyst workflow — import data → clean/join → model → visualize → add interactivity — the same process used in real business reporting.

## 💡 Impact / Business Value
This dashboard demonstrates how raw transactional exports can be turned into a decision-support tool:

- **Identifies where revenue concentrates** (Madhya Pradesh and Maharashtra), which could guide regional marketing or inventory allocation.
- **Flags a profitability gap** — Clothing drives the most volume, but Printers and Bookcases are more profitable per sale, suggesting a possible push toward higher-margin sub-categories.
- **Surfaces seasonality** in the Profit by Month view, useful for planning promotions ahead of low-profit months (May/June) and capitalizing on high-performing months (November).
- **Highlights payment behavior** (COD still leads at 46%), which is relevant for logistics and cash-flow planning versus digital payment adoption (UPI, Credit Card, EMI).
- Overall, the project simulates how a real analyst would turn multi-table transactional data into a **single source of truth** that stakeholders can filter and explore themselves, reducing repeated ad-hoc reporting requests.

## 🧰 Tools Used
- **Power BI** (Desktop) — data modeling, DAX measures, visualizations, slicers
- **CSV data sources** — `Orders.csv`, `Details.csv`

---
*Practice project built to strengthen Power BI and data analysis skills relevant to a Data Analyst role.*
