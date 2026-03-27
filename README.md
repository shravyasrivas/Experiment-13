

---

# Experiment 13: Data Wrangling and Missing Value Preprocessing

---

### Aim: To perform preprocessing on a dataset and deal with missing values

---

### Theory

Data wrangling (or data preprocessing) is a critical step in the machine learning pipeline that involves cleaning and transforming raw data into a usable format. Real-world datasets often contain **NaN (Not a Number)** values, which represent missing data. 

This experiment demonstrates how to use the **Pandas** and **NumPy** libraries to identify, count, and resolve these missing entries. Techniques include dropping incomplete rows or columns and "imputation," where missing values are replaced with statistical measures like the **mean** or **median**. Additionally, the experiment covers fixing inconsistent text formatting and converting data types (such as strings to dates) to ensure the dataset is ready for algorithmic analysis.

---

### Command Descriptions

The following commands were used to perform data cleaning and preprocessing:

| Command | One-Line Description |
| :--- | :--- |
| `import numpy as np` | Imports the Numerical Python library to handle `np.nan` (Not a Number) values. |
| `df.isna()` | Returns a boolean table where `True` indicates a missing value and `False` indicates a value is present. |
| `df.notna()` | The opposite of `isna()`, showing `True` for valid entries and `False` for missing ones. |
| `df.isna().sum()` | Calculates the total number of missing (NaN) values for each column in the DataFrame. |
| `df.isna().sum(axis=1)` | Calculates the total number of missing values present in each individual row. |
| `df.dropna()` | Removes any row that contains at least one missing value from the dataset. |
| `df.dropna(axis=1)` | Removes any column that contains at least one missing value. |
| `df.fillna(value='X')` | Replaces all missing NaN values in the dataset with a specific default string or value. |
| `df.fillna(df.mean())` | Imputes missing entries by replacing them with the average value of that specific column. |
| `pd.to_numeric()` | Converts a column's data type to a numeric format, turning invalid entries like "-" into NaN. |
| `df["Col"].fillna()` | Targeted imputation used to fill missing values in a specific column using mean or median. |
| `.str.upper()` | Fixes inconsistent text by converting all string entries in a column to uppercase letters. |
| `pd.to_datetime()` | Converts string-based dates into a standard Python datetime format for time-based analysis. |

---

### Functions and Logic Used

#### Identification Logic
* **Missing Value Detection:** Using `.isna()` to pinpoint gaps in the data.
* **Axis Manipulation:** Using `axis=0` for column-wise operations and `axis=1` for row-wise operations.

#### Cleaning Logic
* **Data Imputation:** Replacing gaps with the **Mean** (average) for "Age" and **Median** (middle value) for "Marks" to maintain data distribution.
* **Inconsistency Handling:** Using `.str.upper()` to merge inconsistent entries like "CSE" and "cse" into a single category.
* **Error Coercion:** Using `errors='coerce'` in numeric conversion to force non-numeric symbols into NaN so they can be cleaned.

---

### Conclusion

Through this experiment, I successfully performed data preprocessing and handled missing values using Python. I learned how to identify NaN values and decide whether to delete them or replace them with statistical averages. Additionally, I practiced standardizing data formats, such as fixing text casing and date formats, which is essential for ensuring that machine learning models receive accurate and consistent input.

---

