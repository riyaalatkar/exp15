## Lab Report: Data Normalization and Data Type Conversion
**Student Name:** Riya Latkar
**PRN:** 25070123092
**Experiment No:** 15

### 1. Aim
To implement data normalization techniques, including Min-Max Scaling and Z-Score Normalization, and to perform data type conversion on a dataset using Python's `pandas` and `numpy` libraries.

### 2. Theory
Data preprocessing is a critical step in machine learning to ensure that numerical features contribute equally to model performance.
* **Min-Max Normalization (Scaling):** This technique transforms features to a fixed range, usually 0 to 1. It is sensitive to outliers but useful when the distribution is not Gaussian. * **Z-Score Normalization (Standardization):** This method scales data based on the mean and standard deviation, resulting in a distribution with a mean of 0 and a standard deviation of 1. It is more robust to outliers than Min-Max scaling. * **Data Type Conversion:** Involves changing the internal representation of data (e.g., from float to integer or object to category) to optimize memory or meet the requirements of specific algorithms.

### 3. Logic
The logic follows a structured data cleaning pipeline:
1.  **Initialize Data:** Create or load a dataset containing various numerical ranges (e.g., Price vs. Units Sold).
2.  **Range Transformation:** Apply the Min-Max formula to compress large values (like 55,000) into a 0–1 scale.
3.  **Statistical Transformation:** Apply the Z-score formula to observe how many standard deviations a data point is from the mean.
4.  **Formatting:** Convert data types to ensure consistency across the dataframe.

### 4. Algorithm
1.  **Import** necessary libraries: `pandas` as `pd` and `numpy` as `np`.
2.  **Define** a dictionary containing product data and convert it into a DataFrame.
3.  **Perform Min-Max Normalization** for a single column by subtracting the minimum value and dividing by the range (Max - Min).
4.  **Perform Multi-column Normalization** by applying the same formula across a subset of the DataFrame.
5.  **Perform Z-Score Normalization** by subtracting the mean of the column and dividing by its standard deviation.
6.  **Print and Verify** the results to ensure values are correctly scaled.


### One-Liner Explanations

**Libraries & Core Commands:**
* `import pandas as pd`: Imports the library used for data manipulation and analysis in tabular formats.
* `import numpy as np`: Imports the library for performing high-level mathematical functions on multi-dimensional arrays.
* `pd.DataFrame(data)`: Converts a Python dictionary into a structured table format for easier processing.

**Normalization Logic:**
* `df['Price'].min()` / `max()`: Identifies the lowest and highest values in the Price column to set scaling boundaries.
* `(df['Price'] - min_price) / (max_price - min_price)`: Computes the Min-Max scaled value to bring data into a 0 to 1 range.
* `df['Units_Sold'].mean()`: Calculates the average value of the column for Z-score centering.
* `df['Units_Sold'].std()`: Calculates the standard deviation to measure the dispersion of the data.
* `(df['Units_Sold'] - mean) / std`: Executes Z-score normalization to standardize the data around a mean of zero.

**Selection & Display:**
* `df[['Product', 'Price', 'Price_Normalized']]`: Selects specific columns from the DataFrame to display a subset of the data.
* `df[cols].min()`: Simultaneously finds the minimum values for multiple specified columns at once.


### 5. Conclusion
In this experiment, I successfully implemented data normalization and type conversion. I observed that Min-Max scaling is effective for bringing all features to the same 0-1 scale, while Z-score normalization provides a better understanding of data variance. These steps are essential for preparing high-quality data for predictive modeling.

---
