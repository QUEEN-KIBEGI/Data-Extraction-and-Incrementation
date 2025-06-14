
# 🧪 DSA 2040A - Lab 4: Transform in ETL (Shopping Trends)

## 👩🏽‍💻 Student Info
- **Name:** Queen Esther Kibegi  
- **Student ID:** [Insert Your Student ID Here]  
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
