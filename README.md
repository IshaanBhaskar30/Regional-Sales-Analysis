# Regional Sales Analysis (XYZ Co.)
## Project summary

This notebook provides a thorough regional sales analysis across 2014–2018 for a retail company. It includes data ingestion from multi-sheet Excel, cleaning, time-series aggregation, seasonal analysis, top-N product/customer analysis, regional heatmaps, channel profitability assessment, and concrete business recommendations.

### Data sources (notebook)

    - Regional Sales Dataset.xlsx (multiple sheets: sales, budgets, state regions, etc.) — the notebook reads workbook sheets and assigns dataframes for each.

## Key steps & pipeline

### 1.Load & inspection

    - Read Excel workbook with sheet_name=None to import all sheets; assign them to meaningful DataFrame names.

    - Clean header rows (some sheets included header rows as data), standardize column names.

### 2.Preprocessing

    - Drop redundant/unnecessary columns, unify date formats, set appropriate numeric types, and handle missing values.

    - Aggregate daily/transactional sales to monthly and yearly levels as required.

### 3.Exploratory analyses

    - Monthly Sales Trend: track revenue over time to detect seasonality; notebook reports a monthly cycle in the ~24M–26M band and highlights an anomalous period (investigate 2017 anomaly).

    - Calendar month seasonality (all years combined): January tends to be strong, followed by a spring dip and mid-summer bump (consistent recurring pattern).

    - Top products by revenue: identify top-10 products driving most revenue — top product pulls away significantly (notebook shows the top product near ~118M in revenue).

    - Profit margin analysis: rank products by average profit margin; top products display notably higher margins, while margins cluster in a middle band (~18%–something); channel margin comparison shows Export with ~37.9% average margin, Distributor ~37.6%, Wholesale ~37.1%.

    - Regional performance: West region dominates total sales (~$360M in the analysis), with California leading (~$230M). Top states and their order counts are listed (NY/Indiana and others show characteristic figures in the notebook).

    - Top customers: top customers contribute multi-million revenues; example: ‘Aibox Company’ tops list with ~$12.5M.

### 4.Customer / Order analysis

    - Top/bottom customers by revenue, correlation between profit and revenue, order-volume vs revenue insights.

### 5.Visualizations & dashboards

    - Time series plots, month-over-month and year-over-year trends, top-N bar charts, heatmaps for regional insights, maps/pivot tables for quick dashboarding.

### 6.Recommendations & business actions (notebook)

    - Focus growth in Export channel due to high margins, investigate under-penetrated states, evaluate pricing/promotion for mid-margin products, and address seasonal planning (inventory/promotions around January and summer bump).

    - Propose outlier strategy for anomalous months, and deeper analysis of 2017 anomaly.

### Reproducibility

    - Run notebook cells sequentially; dataset is multi-sheet Excel — ensure openpyxl installed for pd.read_excel.

    - Notebook includes cleaning steps to normalize header rows and sheet-specific preprocessing.

### Suggested next steps

    - Build regional forecasting models (ARIMA / Prophet / XGBoost with date features) for monthly revenue per region.

    - Perform causal uplift or A/B-style analysis on promotions to measure incremental impact.

    - Inventory optimization for top SKUs and channel-specific profitability experiments.

    - Build an interactive dashboard (Power BI / Tableau / Streamlit) for operational stakeholders to explore regional & product-level KPIs.

### Tech stack

    - Python (pandas, numpy, matplotlib, seaborn), Jupyter Notebook, Excel (openpyxl).
