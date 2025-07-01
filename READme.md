LAB 3  README FILE
# ETL Extract Lab - Shopping Trends Analysis

**Student Name**: Queen Esther  


## Project Description
This Jupyter notebook demonstrates ETL (Extract, Transform, Load) operations focusing on the extraction phase. It implements both full and incremental extraction methods using a shopping trends dataset.

## Tools Used
- Python 3
- pandas
- Jupyter Notebook

## Dataset
The dataset contains synthetic shopping trend data with the following columns:
- Customer ID
- Age
- Gender
- Category
- Purchase Amount (USD)
- Payment Method
- Review Rating
- Purchase Date

## How to Run
1. Ensure you have Python 3 and Jupyter installed
2. Install required packages: `pip install pandas numpy`
3. Run the notebook: `jupyter notebook etl_extract.ipynb`
4. Execute cells in order

## Implementation Details
- **Full Extraction**: Loads the entire dataset
- **Incremental Extraction**: Only loads records added/changed since last extraction
- **Timestamp Tracking**: Uses last_extraction.txt to track when the last extraction occurred
# 🧪 DSA 2040A - Lab 4: Transform in ETL (Shopping Trends)

LAB 4 README FILE
- **Name:** Queen Esther Kibegi   
- **Course:** DSA 2040A – Data Science & Analytics  
- **Lab:** Lab 4 – Transform in ETL  
- **Dataset Used:** `Shopping_Trends.csv`

## 📌 Objective
The goal of this lab is to **extend the ETL pipeline** from Lab 3 by applying various transformation techniques to prepare the data for analysis.

## 📂 Project Structure

ETL\_Extract\_QueenEstherKibegi\_<YourID>/
├── etl\_extract.ipynb
├── Shopping\_Trends.csv
├── transformed\_full.csv
├── transformed\_incremental.csv
├── last\_extraction.txt
├── .gitignore
├── README.md


## 🔄 Transformations Performed

### ✅ Cleaning
- Removed duplicate records from the dataset.
- Handled missing values using **forward fill** method.
- Dropped unnecessary columns like `Unnamed: 18` and `Unnamed: 20`.

### ✅ Enrichment
- Added a new calculated column `Loyalty_Score = Previous Purchases / Age`.
- Added a `Total_Price` column using `Purchase Amount (USD)` (assumed quantity = 1).

### ✅ Structural
- Converted `Order Date` to datetime format and restructured it to `YYYY-MM-DD` format for standardization.

### ✅ Categorization
- Created an `Age_Group` column by binning `Age` values into groups:
  - `<18`, `18–25`, `26–35`, `36–50`, `51–70`, `71+`

### ✅ Filtering
- Dropped irrelevant or empty columns (`Unnamed: 18`, `Unnamed: 20`) for cleaner analysis.

## 🧾 Files Generated

| File Name                  | Description                              |
|---------------------------|------------------------------------------|
| `transformed_full.csv`    | Cleaned and enriched full dataset        |
| `transformed_incremental.csv` | Transformed last 50 records (incremental) |

## 🧠 Notebook Sections

Your Jupyter Notebook `etl_extract.ipynb` now includes:
- **Section 1:** Introduction  
- **Section 2:** Load Data  
- **Section 3:** Data Preview  
- **Section 4:** Transform Full Data  
- **Section 5:** Transform Incremental Data  


## 🛠️ Tools Used
- **Language:** Python (Pandas)
- **IDE:** Jupyter Notebook
- **Environment:** Anaconda

# ETL Load Phase - Lab 5

## Project Description
This Python script implements the Load phase of an ETL (Extract, Transform, Load) pipeline. It loads transformed data from CSV files into both SQLite databases and Parquet files, with support for both full and incremental data loads.
## Features
-Functions
create_sqlite_table(): Creates a SQLite table with specified schema
save_to_parquet(): Saves DataFrame to Parquet format
verify_sqlite_data(): Verifies data in SQLite tables
verify_parquet_data(): Verifies data in Parquet files
validate_dates(): Validates and converts date columns

**Main Process**
Setup: Creates output directory and database connections
Full Data Load:
Reads transformed_full.csv
Validates and maps data
Loads to SQLite and saves as Parquet
Incremental Data Load:
Reads transformed_incremental.csv
Validates and maps data
Loads to SQLite and saves as Parquet
Verification: Checks data in all output formats

## 🧱 SQLite Schema Used

```sql
CREATE TABLE full_data (
    id INTEGER PRIMARY KEY,
    customer_name TEXT,
    product TEXT,
    quantity INTEGER,
    unit_price REAL,
    total_price REAL,
    order_date TEXT
);

**Data Mapping**
The script maps the following fields from source to target:
Customer ID → id
Default value → customer_name (set to 'Unknown')
Category → product
Default value → quantity (set to 1)
Purchase Amount (USD) → unit_price
Purchase Amount (USD) → total_price
Order Date → order_date

**Output Verification**
The script automatically verifies:
First 5 rows of each SQLite table
First 5 rows of each Parquet file


**Error Handling**
The script includes comprehensive error handling for:
File operations
Database operations
Data validation
Parquet file operations

**##Technologies Used**
Python 3.x
pandas
sqlite3
SQLAlchemy
pyarrow (for Parquet)
os, datetime


