# Sales Time-Series Analysis with DuckDB

<img src= 'img\output1.png' alt="over all monthly sales" width='1000'>

A Python and SQL project that explores synthetic sales time-series data using DuckDB, Pandas, and Matplotlib. The notebook groups sales by month and product, compares product performance over time, visualizes trends, and exports analysis results as CSV files.

## Project Objectives

- Convert transaction dates into month, year, and month-start values for time-based analysis.
- Calculate monthly sales quantity for each product.
- Calculate average daily quantity per product per month, counting days without recorded sales as zero.
- Identify each product's month with the highest average daily quantity.
- Find the top three products by total quantity for each month.
- Calculate month-over-month percentage changes in average daily quantity.
- Visualize overall monthly sales and trends for the five highest-selling products.
- Export result tables to CSV for further analysis.

## Tech Stack

- **Python** — workflow and data handling
- **DuckDB** — SQL queries and aggregations
- **Pandas** — working with query results and exports
- **Matplotlib** — charts and visualizations
- **Jupyter Notebook** — interactive analysis

## Dataset

The project uses `synthetic_sales_time_series.csv`, which contains synthetic sales records with these fields:

| Column | Description |
|---|---|
| `date` | Date of the sales record |
| `product_id` | Product identifier |
| `quantity_sold` | Quantity sold in that record |

Because the dataset is synthetic, the results demonstrate analytical methods and should not be treated as evidence of real-world business performance.

## Getting Started

### 1. Clone or download the repository

Make sure the notebook and CSV file are in the same project folder.

### 2. Install dependencies

```bash
pip install pandas duckdb matplotlib jupyter
```

### 3. Open the notebook

```bash
jupyter notebook duckdb_sales.ipynb
```

### 4. Run the analysis

Run the notebook cells from top to bottom. The notebook reads `synthetic_sales_time_series.csv` from the working directory, performs the SQL analysis with DuckDB, displays tables and charts, and writes the result CSV files to the working directory.

## Analysis Outputs

When the export cell runs successfully, it creates these files:

- `monthly_product_totals.csv` — monthly quantity totals by product
- `average_daily_sales.csv` — average daily quantity and related monthly metrics by product
- `highest_average_month_per_product.csv` — month or months with the highest average daily quantity for each product
- `top_3_products_per_month.csv` — three highest-ranked products for each month
- `month_over_month_percentage_change.csv` — month-over-month changes in average daily quantity

The notebook also displays charts for total monthly sales quantity and the monthly trends of the five highest-selling products.

## Metric Note

The calendar-day average treats a product with no recorded transaction on a given date as having zero sales for that day. This differs from the average calculated only across days when that product had recorded sales. The notebook uses calendar-day averages for the main monthly comparison.

## Suggested Repository Structure

```text
data/
│    └──sales-time-series-analysis
│
targetdata/
│    └──average_daily_sales.csv
│    └──highest_average_month_per_product.csv
│    └──month_over_month_percentage_change.csv
│    └──monthly_product_total.csv
│    └──top_3_product_totals.csv
│
├── README.md
├── duckdb_sales.ipynb
├── requirements.txt
└── synthetic_sales_time_series.csv
```
