# Regional Sales Dashboard

**An end-to-end data analytics & business intelligence project** — from raw multi-sheet Excel data to a fully interactive Power BI dashboard, powered by a complete Python exploratory data analysis (EDA) pipeline.

Dataset coverage: Acme Co. USA Sales, **2014 – 2018** 


## Project Overview

This project analyzes five years of regional sales data for a fictional distribution company, **Acme Co.**, taking it through the complete analytics lifecycle:

1. **Phase 1 — Exploratory Data Analysis (Python / Jupyter Notebook):** loading, cleaning, merging six raw data sheets, feature engineering, and a structured EDA covering sales trends, product performance, customer behavior, channel mix, and profitability.
2. **Phase 2 — Interactive Power BI Dashboard:** a polished, 5-page, fully interactive report built on the cleaned dataset, with a custom navigation system, synchronized slicers, KPI cards, and drill-down visuals.

The goal is to demonstrate the same workflow used by data analysts and BI developers in industry: raw data → clean data → insight → a self-service dashboard a business stakeholder can explore without touching a line of code.



##  Problem Statement & Objective

**Problem Statement:** Organizations need to understand the factors influencing sales and profitability. This project analyzes historical sales data to identify key trends, performance drivers, and business opportunities across products, channels, customers, and regions.

**Objective:** Extract actionable insights from the sales data by:
- Identifying top-performing and under-performing products, customers, and regions.
- Analyzing monthly and yearly sales trends to detect seasonality and growth patterns.
- Understanding profitability drivers such as pricing, cost, and sales channel.
- Supporting data-driven decisions through visualization and an interactive reporting layer.



##  Tech Stack

| Category | Tools / Libraries |
|---|---|
| Programming Language | Python 3 |
| Data Handling | Pandas, NumPy |
| Data Visualization (EDA) | Matplotlib, Seaborn |
| Development Environment | Jupyter Notebook (via VS Code) |
| Source Data | Multi-sheet Excel workbook — `Regional Sales Dataset.xlsx` |
| Business Intelligence Tool | Power BI Desktop |
| Version Control | Git & GitHub |



##  Repository Structure

```
regional-sales-dashboard/
│
├── data/
│   ├── Regional Sales Dataset.xlsx        # Raw multi-sheet source workbook
│   └── Regional_Sales_Cleaned.csv         # Cleaned, merged, feature-engineered dataset
│
├── notebook/
│   └── Regional_Sales_Analysis.ipynb      # Full EDA notebook (cleaning, wrangling, charts)
│
├── powerbi/
│   └── Regional_Sales_Dashboard.pbix      # Power BI report file
│
├── screenshots/
│   ├── dashboard_home.png                 # Home / navigation page
│   ├── executive_overview.png             # Executive Overview of Sales Performance
│   ├── product_customer.png               # Product & Customer Analysis
│   ├── profitability.png                  # Profitability & Performance Analysis
│   ├── geographic.png                     # Geographic Performance
│   ├── menu_dropdown.png                  # In-canvas ☰ Menu navigation
│   └── slicers.png                        # Order Year / Region / Channel slicers
│
├── report/
│   └── Regional_Sales_Dashboard_Project_Report.docx   # Full written project report
│
└── README.md
```


### Feature Engineering
| Column | Formula | Purpose |
|---|---|---|
| `total_cost` | `order_quantity × total_unit_cost` | True cost of goods sold per order line |
| `profit` | `revenue − total_cost` | Absolute profit per order line |
| `profit_margin_%` | `(profit / revenue) × 100` | Profit as % of revenue |

### Exploratory Analysis Highlights
-  **Seasonality** — revenue peaks in January and again mid-year (May/August), with a consistent February trough.
-  **Top products** — Product 26 (₹117.29M) and Product 25 (₹109.47M) lead revenue; Product 18 leads on *average profit per order* (₹8,531) despite not being a top-10 revenue product.
-  **Channel mix** — Wholesale drives 54.1% of revenue, Distributor 31.3%, Export 14.6% — but all three channels convert to a similar ~37% average profit margin.
-  **Pricing vs. margin** — a regression plot shows unit price has almost no correlation with profit margin; cost structure matters more than price point.
-  **Geography** — California leads decisively (₹228.79M revenue, 12,000 orders), more than double the next state, Illinois.
-  **Customers** — a small set of top accounts (Aibox Company, State Ltd, Pixoboo Corp) drive disproportionate revenue versus the bottom-tier accounts.
-  **Correlation heatmap** — confirms revenue is strongly tied to unit price (r = 0.91) and cost (r = 0.85); profit margin is only weakly related to either (r ≈ -0.28 to 0.38).


### Pages

| Page | Description |
|---|---|
| **Home** | Landing page with navigation buttons to all four analytical pages |
| **Executive Overview of Sales Performance** | KPI cards (Revenue, Profit, Orders, Margin %, Revenue/Order), monthly trend, revenue by region, channel donut, top 10 products |
| **Product & Customer Analysis** | Top/Bottom 10 products & customers by revenue, revenue-by-state treemap |
| **Profitability & Performance Analysis** | Cost/Profit/Margin KPIs, revenue vs. cost by region, profit margin by region, orders by region |
| **Geographic Performance** | Top 10 states by revenue/orders, U.S. filled map, revenue vs. budget by state & product |

| Home | Executive Overview of Sales Performance |
|------|------------------------------------------|
| <img src="https://github.com/user-attachments/assets/e7da2ef3-3584-42ec-ac53-225958e16f0a" width="100%"> | <img src="https://github.com/user-attachments/assets/7f5f5359-d947-48a8-985e-d1af87ff2914" width="100%"> |

| Product & Customer Analysis | Profitability & Performance Analysis |
|------------------------------|--------------------------------------|
| <img src="https://github.com/user-attachments/assets/5df0dd8f-3054-4904-96eb-30db468c23ee" width="100%"> | <img src="https://github.com/user-attachments/assets/953346d0-6a4f-4cf5-8128-597edc4ec67c" width="100%"> |

| Geographic Performance |
|------------------------|
| <img src="https://github.com/user-attachments/assets/7c5d8835-93bb-4f7d-9b4a-9a4d6e4741c9" width="100%"> |


##  Key Insights

1. Sales are highly seasonal and repeatable — useful for inventory and staffing planning.
2. Revenue is concentrated in a handful of products and states, creating concentration risk worth monitoring.
3. The top revenue product is not the top profit product — both rankings should be tracked.
4. Wholesale is the volume channel, not necessarily the margin channel — all channels convert at a similar rate.
5. Price positioning is not the primary lever for profit margin — cost control matters more.
6. A tiered, key-account approach to customer management is supported by the wide revenue gap between top and bottom accounts.



##  How to Run This Project

**Python / Jupyter Notebook**
```bash
git clone https://github.com/<your-username>/regional-sales-dashboard.git
cd regional-sales-dashboard
pip install pandas numpy matplotlib seaborn openpyxl jupyter
jupyter notebook notebook/Regional_Sales_Analysis.ipynb
```

**Power BI Dashboard**
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows only).
2. Open `powerbi/Regional_Sales_Dashboard.pbix`.
3. If prompted, update the data source path to point to `data/Regional_Sales_Cleaned.csv` on your machine.
4. Explore the dashboard using the Home page navigation buttons and the Order Year / Region / Channel slicers.



##  Future Enhancements

- Extend the budget data to all five years for a full actual-vs-budget trend line.
- Add year-over-year / month-over-month growth measures using DAX time-intelligence.
- Add a dedicated customer segmentation (RFM) page.
- Publish to the Power BI Service and embed a live report link here.



## 👤 Author

**Rachabattuni Sai Sindhu**

If you found this project useful or interesting, feel free to ⭐ star the repo!
