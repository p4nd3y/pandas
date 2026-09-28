# 🐼 Pandas Complete Hands-on Guide & Cheat Sheet

A comprehensive, practical, and interactive Jupyter Notebook repository covering foundational to advanced data manipulation, transformation, and analysis techniques using **Python's `pandas` library**.

---

## 📁 Repository Contents

| File | Description |
| :--- | :--- |
| **[`pandas.ipynb`](./pandas.ipynb)** | Complete hands-on notebook containing code demonstrations, explanations, and outputs for all core Pandas features. |
| **[`README.md`](./README.md)** | Overview of concepts, topic breakdowns, syntax quick references, and getting started guide. |

---

## 📚 Topics Covered

### 1. 🔹 Pandas Series
* **Definition**: One-dimensional labeled array capable of holding any data type (integers, strings, floating point numbers, Python objects).
* **Creation**: Creating Series from Python lists, NumPy arrays, scalar values, and dictionaries.
* **Indexing & Slicing**: Default positional integer indices vs custom string labels.

### 2. 🔹 Pandas DataFrames
* **Definition**: Two-dimensional size-mutable, tabular data structure with labeled axes (rows and columns).
* **Creation**: Instantiating DataFrames from Python dictionaries, nested lists, and structured arrays.
* **Column Operations**: Adding new columns, modifying existing columns, renaming headers, and dropping columns.

### 3. 🔹 Data Selection & Subsetting (`loc` vs `iloc`)
* **`loc` (Label-Based)**: Accessing specific rows and columns by their labels/index names (e.g., `df.loc[[0, 1], ['City', 'Salary']]`).
* **`iloc` (Position-Based)**: Accessing rows and columns by integer positional indices.
* **Conditional Masking**: Filtering records based on boolean conditions and logical operators (`&`, `|`, `~`).

### 4. 🔹 Handling Missing & Null Data
* **Detection**: Finding null entries using `.isna()`, `.isnull()`, and `.sum()`.
* **Removal**: Dropping null rows or columns using `.dropna(axis=0/1, how='any'/'all')`.
* **Imputation**: Filling missing values using `.fillna(value)`, forward-filling, backward-filling, or column statistical averages.

### 5. 🔹 Combining Data (Merge, Join & Concatenation)
* **SQL-Style Merges (`pd.merge`)**:
  * `inner`: Intersection of keys.
  * `outer`: Full union of keys across datasets.
  * `left`: Retain all left keys with matched right records.
  * `right`: Retain all right keys with matched left records.
* **Concatenation (`pd.concat`)**:
  * Row-wise stacking (`axis=0`).
  * Column-wise joining (`axis=1`).

### 6. 🔹 GroupBy & Split-Apply-Combine Operations
* **Single & Multi-Column Grouping**: Grouping data points across categorical dimensions (e.g., `df.groupby(['Category', 'Store'])`).
* **Aggregation**: Calculating summary statistics (`.mean()`, `.sum()`, `.count()`, `.agg()`) per segment.

### 7. 🔹 Pivot Tables & Multi-Dimensional Reshaping
* **`pd.pivot_table`**: Reshaping and cross-tabulating data with custom indices, columns, and value aggregation functions (`aggfunc`).

### 8. 🔹 Element-Wise Transformations & Vectorization
* **Summary Statistics**: `.describe()`, `.info()`, `.value_counts()`.
* **Applying Custom Functions**: Transforming columns efficiently using `.apply()` with Python `lambda` functions and custom callables.

---

## 🚀 Quick Reference / Cheat Sheet

```python
import pandas as pd
import numpy as np

# 1. Create a DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'Salary': [50000, 60000, 75000]
})

# 2. Select columns & rows
subset = df.loc[df['Age'] > 28, ['Name', 'Salary']]

# 3. Handle Missing Data
clean_df = df.fillna({'Salary': df['Salary'].median()})

# 4. Merging
merged = pd.merge(df1, df2, on='key_id', how='left')

# 5. GroupBy & Aggregate
summary = df.groupby('Category')['Salary'].mean()

# 6. Apply Transformations
df['Salary_Taxed'] = df['Salary'].apply(lambda x: x * 0.8)
```

---

## 🛠️ Getting Started

### Prerequisites

Ensure Python 3.8+ and the following packages are installed:

```bash
pip install pandas numpy jupyter
```

### Running the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/p4nd3y/pandas.git
   cd pandas
   ```

2. Open the notebook:
   ```bash
   jupyter notebook pandas.ipynb
   ```

3. Run through each section interactively to explore Pandas functionalities with live outputs.

---

## 📄 License
This repository is open-source and created for learning, reference, and educational purposes.
