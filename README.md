# ADS-Assignment-2

# Smartphone Dataset Cleaning & Recommendation (Notebook)

This Jupyter Notebook demonstrates **data cleaning, preprocessing, and a simple product recommendation system** using a smartphone dataset (`smartphones.csv`).

---

## Features

### **1. Import Libraries**

* Imports **Pandas** for dataset handling and analysis.

### **2. Load Dataset**

* Loads raw data from `smartphones.csv`.
* Displays dataset shape and first few rows.

### **3. Explore Dataset**

* Prints dataset info (column names, data types, null counts).
* Generates descriptive statistics.
* Displays first 10 rows for inspection.

### **4. Handle Missing Values**

* **Price**: removes `₹` and commas, converts to float, fills missing with **median**.
* **Rating**: fills missing with **mean**.
* **Camera**: fills missing with **mode** (most frequent value).
* **Expandable Storage (card)**: missing values replaced with `"Not Specified"`.
* **Operating System (os)**: missing values replaced with `"Unknown"`.

### **5. Remove Duplicates**

* Identifies and removes duplicate records.

### **6. Correct Data Types**

* Extracts **numeric values** from text fields:

  * **RAM** → `"8 GB"` → `8`
  * **Battery** → `"5000 mAh"` → `5000`
  * **Display** → `"6.5 inches"` → `6.5`
* Converts **release_date** to proper datetime (if present).

### **7. Save Cleaned Dataset**

* Exports cleaned data as `smartphones_cleaned.csv`.

### **8. Product Recommendation Search**

* Function `recommend_products(keyword, df, column="model")`:

  * Performs **case-insensitive search**.
  * Returns matching products.
  * Example:

    ```python
    recommend_products("iPhone", df)
    ```

---

## 📂 Files

* **`smartphones.csv`** → Raw dataset (input).
* **`smartphones_cleaned.csv`** → Cleaned dataset (output).
* **`ADS.ipynb`** → Jupyter Notebook containing full pipeline.

---

## 🛠️ How to Run

1. Install dependencies:

   ```bash
   pip install pandas
   ```
2. Place your dataset as **`smartphones.csv`** in the same folder.
3. Open the notebook in JupyterLab / Jupyter Notebook / VS Code.
4. Run all cells sequentially.
5. The cleaned dataset will be saved as:

   ```
   smartphones_cleaned.csv
   ```
6. Use the `recommend_products` function inside the notebook to search for products.

---

## ✅ Example Output

**Search: `"Samsung"`**

```text
       model          price   rating  ram_gb  battery_mah  display_inches   os
0   Samsung Galaxy S21  69999.0     4.3     8.0        4000.0            6.2  Android
1   Samsung Galaxy A52  25999.0     4.1     6.0        4500.0            6.5  Android
```
