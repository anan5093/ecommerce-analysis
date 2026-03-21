# 🛒 E-Commerce Sales Analysis

A data analysis project focused on Amazon marketplace sales performance. This project cleans, processes, and analyzes Amazon sales data to surface actionable KPIs covering revenue, customer behaviour, discount effectiveness, and growth trends.

---

## 📋 Table of Contents

- [What the Project Does](#what-the-project-does)
- [Key Features](#key-features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Data Setup](#data-setup)
  - [Running the Analysis](#running-the-analysis)
- [KPIs Analysed](#kpis-analysed)
- [Where to Get Help](#where-to-get-help)
- [Contributing](#contributing)
- [Maintainers](#maintainers)

---

## What the Project Does

This project ingests raw Amazon sales export data (CSV), performs data cleaning, and computes a set of business KPIs through a Jupyter notebook and supporting Python scripts. The outputs give e-commerce analysts a clear picture of:

- Overall sales performance (revenue, order volume, AOV)
- Month-over-month revenue growth
- Promotional discount impact on order volume and basket depth
- Customer purchase frequency and retention signals

---

## Key Features

- **Data cleaning pipeline** — strips whitespace from column names, removes cancelled/returned/zero-revenue orders, and exports a clean processed CSV.
- **Core sales KPIs** — total revenue, total orders, and average order value (AOV).
- **Revenue growth rate** — month-over-month percentage change with a matplotlib trend chart.
- **Discount effectiveness analysis** — binary discount flag, order share, and revenue contribution by discount band.
- **Customer behaviour metrics** — repeat purchase rate, units per transaction, and purchase frequency.
- **Category revenue breakdown** — bar chart ranking product categories by revenue contribution.

---

## Project Structure

```
ecommerce-analysis/
├── notebooks/
│   └── Amazon_sales_report.ipynb   # Main analysis notebook
├── scripts/
│   └── kpi.py                      # Standalone KPI computation script
├── utils/                          # Shared utility helpers
├── models/                         # Saved models (future use)
├── dashboards/                     # Dashboard assets (future use)
├── reports/
│   └── project_report.md           # Written analytical report
└── datasets/                       # ⚠ Git-ignored — see Data Setup below
    ├── raw/
    │   └── Amazon Sale Report.csv
    └── processed/
        └── amazon_sales_cleaned.csv
```

---

## Getting Started

### Prerequisites

| Requirement | Version |
|-------------|---------|
| Python | 3.9 + |
| pip | latest |

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/anan5093/ecommerce-analysis.git
   cd ecommerce-analysis
   ```

2. **Create and activate a virtual environment** *(recommended)*

   ```bash
   python -m venv ecommerce-env
   source ecommerce-env/bin/activate   # Windows: ecommerce-env\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```

### Data Setup

The raw dataset is not tracked in this repository. Place the Amazon sales CSV at:

```
datasets/raw/Amazon Sale Report.csv
```

Create the output directory for cleaned data:

```bash
mkdir -p datasets/processed
```

### Running the Analysis

**Jupyter Notebook (recommended)**

```bash
jupyter notebook notebooks/Amazon_sales_report.ipynb
```

Run all cells in order. The notebook will:

1. Load and inspect the raw data.
2. Clean and filter the dataset (removes cancelled, returned, and zero-revenue records).
3. Compute and display all KPIs with supporting visualisations.
4. Export the cleaned dataset to `datasets/processed/amazon_sales_cleaned.csv`.

**KPI Script**

```bash
python scripts/kpi.py
```

---

## KPIs Analysed

| KPI | Description |
|-----|-------------|
| **Total Revenue** | Sum of all net-realised order amounts |
| **Total Orders** | Count of unique fulfilled order IDs |
| **Average Order Value (AOV)** | Revenue ÷ total orders |
| **Monthly Revenue Growth Rate** | Month-over-month % change in revenue |
| **Category Revenue Share** | Revenue contribution ranked by product category |
| **Discount Penetration** | Share of orders with a promotion applied |
| **Revenue by Discount Band** | Revenue split: discounted vs non-discounted orders |
| **Units per Transaction** | Average quantity of items per order |
| **Repeat Purchase Rate** | % of order IDs with more than one transaction |
| **Purchase Frequency** | Orders per unique shipping postal code |

---

## Where to Get Help

- **Analytical findings** — see [`reports/project_report.md`](reports/project_report.md) for written commentary on each KPI.
- **Notebook documentation** — each KPI section in [`notebooks/Amazon_sales_report.ipynb`](notebooks/Amazon_sales_report.ipynb) includes a markdown cell with business context and interpretation.
- **Issues** — open a [GitHub Issue](../../issues) to report bugs or request features.

---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository and create a feature branch.
2. Make your changes with clear, descriptive commit messages.
3. Open a pull request describing what you changed and why.

Please keep notebooks free of large cell outputs before committing (use *Kernel → Restart & Clear Output*).

---

## Maintainers

| Maintainer | GitHub |
|------------|--------|
| anan5093 | [@anan5093](https://github.com/anan5093) |
