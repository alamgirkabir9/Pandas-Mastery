# 🌟 Pandas Mastery Roadmap

## 📌 1. Introduction to Pandas

### 🔹 What is Pandas?
Pandas is a powerful data analysis and manipulation library for Python, providing data structures like DataFrames and Series to efficiently handle structured data.

### 🔹 Installing Pandas
```bash
pip install pandas
```

---
## 📌 2. Pandas Data Structures

### 🔹 Series
```python
import pandas as pd
s = pd.Series([1, 2, 3, 4, 5])
print(s)
```

### 🔹 DataFrame
```python
data = {'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35]}
df = pd.DataFrame(data)
print(df)
```

---
## 📌 3. Loading Data

### 🔹 From CSV
```python
df = pd.read_csv('data.csv')
print(df.head())
```

### 🔹 From Excel
```python
df = pd.read_excel('data.xlsx')
print(df.head())
```

### 🔹 From JSON
```python
df = pd.read_json('data.json')
print(df.head())
```

---
## 📌 4. Data Exploration
```python
print(df.info())  # Summary of DataFrame
print(df.describe())  # Statistical summary
print(df.shape)  # Dimensions of DataFrame
print(df.columns)  # Column names
print(df.nunique())  # Unique values count per column
```

---
## 📌 5. Data Selection & Filtering
```python
print(df['Name'])  # Selecting a single column
print(df[['Name', 'Age']])  # Selecting multiple columns
print(df[df['Age'] > 30])  # Filtering rows based on condition
print(df.loc[0, 'Name'])  # Accessing specific row and column
print(df.iloc[0, 1])  # Accessing using index positions
```

---
## 📌 6. Handling Missing Data
```python
print(df.isnull().sum())  # Count missing values
print(df.dropna())  # Remove missing values
df.fillna(value=0, inplace=True)  # Replace missing values
```

---
## 📌 7. Data Transformation
```python
df['Age'] = df['Age'].apply(lambda x: x + 1)  # Apply function
print(df.rename(columns={'Age': 'Years'}))  # Rename columns
print(df.sort_values(by='Years', ascending=False))  # Sorting
df['Age Category'] = pd.cut(df['Years'], bins=[20, 30, 40], labels=['Young', 'Middle-aged'])  # Binning data
```

---
## 📌 8. Grouping & Aggregation
```python
print(df.groupby('Name').mean())  # Group by Name and compute mean
print(df.groupby('Age').sum())  # Group by Age and sum values
print(df.groupby('Age').agg({'Score': ['mean', 'max']}))  # Multiple aggregation functions
```

---
## 📌 9. Merging & Joining Data
```python
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Name': ['Alice', 'Bob', 'Charlie']})
df2 = pd.DataFrame({'ID': [1, 2, 3], 'Score': [90, 85, 88]})
merged_df = pd.merge(df1, df2, on='ID')
print(merged_df)
```

---
## 📌 10. Working with Time Series Data
```python
df['Date'] = pd.to_datetime(df['Date'])  # Convert to datetime format
print(df.set_index('Date').resample('M').mean())  # Resampling data by month
```

---
## 📌 11. Pivot Tables
```python
print(df.pivot_table(index='Name', columns='Age', values='Score', aggfunc='mean'))
```

---
## 📌 12. Performance Optimization
```python
import numpy as np
df['LargeNumbers'] = np.random.rand(1000000)
print(df.memory_usage(deep=True))  # Check memory usage
df_optimized = df.astype({'LargeNumbers': 'float32'})  # Reduce memory usage
```

---
## 📌 13. Saving Data
```python
df.to_csv('output.csv', index=False)  # Save as CSV
df.to_excel('output.xlsx', index=False)  # Save as Excel
df.to_json('output.json')  # Save as JSON
```

---
## 🎯 Conclusion
This roadmap provides a structured path to mastering Pandas. Practicing these concepts with real-world datasets will solidify your understanding! 🚀

