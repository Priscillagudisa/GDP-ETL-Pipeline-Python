# GDP ETL Pipeline Using Python

## Project Overview

This project demonstrates an Extract, Transform, Load (ETL) pipeline developed using Python to process historical country GDP data from Wikipedia's IMF estimates.

The pipeline extracts GDP information, transforms the data from millions to billions of USD, and loads the processed dataset into CSV and SQLite formats for analysis.

## Technologies Used

- Python
- Pandas
- BeautifulSoup
- Requests
- NumPy
- SQLite
- SQL
- Jupyter Notebook

## ETL Workflow

### 1. Extract
- Retrieve historical GDP information from Wikipedia using Requests.
- Parse HTML content using BeautifulSoup.
- Extract country names and IMF GDP estimates.

### 2. Transform
- Convert GDP values from strings into numeric values.
- Remove comma separators.
- Convert GDP figures from millions to billions of USD.
- Round GDP values to two decimal places.

### 3. Load
- Export transformed data to `Countries_by_GDP.csv`.
- Load data into the `Countries_by_GDP` table in `World_Economies.db`.

### 4. SQL Analysis
Execute a SQL query to identify countries with GDP greater than or equal to $100 billion.

```sql
SELECT *
FROM Countries_by_GDP
WHERE GDP_USD_billions >= 100;
```

### 5. Logging
Track pipeline execution using timestamped logs saved in `etl_project_log.txt`.

## Project Outputs

- `etl_project_gdp.py` — Python ETL script
- `Countries_by_GDP.csv` — Processed GDP dataset
- `World_Economies.db` — SQLite database generated during execution
- `etl_project_log.txt` — Execution log generated during execution

## How to Run

Install dependencies:

```bash
pip install pandas numpy requests beautifulsoup4
```

Run the ETL pipeline:

```bash
python etl_project_gdp.py
```

**Note:** The source uses a historical Wayback Machine snapshot. Execution may be affected by website availability or rate limits.

## Skills Demonstrated

Python programming, web scraping, ETL development, data transformation, SQL querying, relational database loading, and execution logging.

## Project Context

Developed as a hands-on learning project through the IBM Data Engineering Professional Certificate.
